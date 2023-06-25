# ESP32 Secure Boot

This project demonstrates how to enable secure boot (Reflashable Mode) on the ESP32. We will show the procedure for enabling secure boot for the current application, and we will verify that secure boot is enabled. Finally, we will show how the user can upload a new firmware as long as they have the correct signing key, and we will show how the user can update the bootloader due to the Reflashable Mode setting.

Our device uses [Secure Boot V1](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/security/secure-boot-v1.html) (version 1), and cannot use [Secure Boot V2](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/security/secure-boot-v2.html).

**NOTE**
- The tutorial assumes that there is no flash encryption enabled on ESP32.
- Once secure boot is enabled, it is enabled forever and can NOT be disabled like the development mode of flash encryption. 

## Introduction to Secure Boot

Secure boot is a security mechanism supported by the ESP32 that verifies the integrity of the application (and the bootloader) at boot-time. It is important to understand how the secure boot procedure works, which is explained below:

1) After secure boot is *first* enabled, the ESP32 hardware uses a 256-bit **secure bootloader key** to generate a digest of the software bootloader's contents. This key is stored in an eFuse. The digest algorithm is effectively _SHA(AES<sub>k</sub>(B))_, where _SHA_ is the SHA-512 hash function, _AES_ is the AES-256 encryption function in ECB mode, _B_ is the bootloader contents, and _k_ is the secure bootloader key.
2) The digest is stored at offset 0x0 of the flash while the software bootloader is stored at address 0x1000.
3) The software bootloader uses the public key component of an ECDSA keypair (called the **secure boot signing key**) to verify the firmware image. This means all firmware images must be signed by the secure boot signing key.
4) If the signature is verified, then the software bootloader loads the firmware image and runs the application.
5) If the ESP32 is *reset*, the ROM bootloader verifies the integrity of the software bootloader by re-calculating the digest and comparing it to the stored digest. The ROM bootloader will load the software bootloader only if the digests match. The software bootloader follows the procedure in Step 3 to verify and boot the firmware.

<img src="imgs/ESP32SecureBoot.PNG" width=512>

The ESP32 supports two kinds of secure boot modes: One-time Flash, and Reflashable:

* In **One-time Flash Mode**, the secure bootloader key is generated internally by the chip and stored in the eFuse, where it cannot be accessed by software. Since the key is inaccessible to the user, the software bootloader cannot be changed after secure boot is enabled.
* In **Reflashable Mode**, the build system generates the secure bootloader key using the SHA-256 digest of the secure boot signing key. This secure bootloader key is then stored in the eFuse. Assuming the user can access the secure boot signing key, the secure bootloader key can always be re-generated, and the software bootloader can be changed after secure boot is enabled.

We are going to enable secure boot in *Reflashable* Mode. 

## 0. Prerequisite: Install the ESP-IDF extension 
Our new Ubuntu VM installed with ESP-IDF and Visual Studio Code with the ESP-IDF extension. If you do not want to install it yourself please download the VM from the specified website. 

Otherwise, please follow [this tutorial](https://github.com/espressif/vscode-esp-idf-extension/blob/master/docs/tutorial/install.md) to install it within VS Code.

## 1. Download this project
Download this repository into your VM:

```sh
git clone https://github.com/PBearson/ESP32_Secure_Boot_Tutorial.git
```
**Note**: By default, this project is already located in the ``` ~/esp/IoT-Examples/ ``` directory of the Ubuntu VM.

## 2. Configure the app

Load the project into VS Code via *File* -> *Open Folder ...*


We will start the ESP-IDF terminal within VS Code (not the Linux terminal) using the button at the bottom of VS Code. 

<img src="imgs/VSCode-ESP-Terminal.png">

Otherwise Within a Linux terminal, we will need to set up the environment variables so that we can use all the tools without inputting the full path names. This can be done with the ``` export.sh ``` script as shown below.
```sh
. $HOME/esp/esp-idf/export.sh
```

<img src="imgs/VSCodeTerminal.png">


### WiFi

Open a terminal, and navigate to the root directory of this project. Open the project configuration menu:

```
idf.py menuconfig
```

Using the up/down arrow keys, navigate to the `Example Configuration` menu, press _enter_ to enter into the menu, then press _enter_ to begin typing your WiFi SSID. When you are done, do the same for the WiFi Password.

### Secure boot

Press _ESC_ and navigate to the `Security Features` menu, and press _enter_ to go into the menu. Select the option `Enable hardware Secure Boot in bootloader`. The secure bootloader mode will be set to One-time flash. We need to change it to Reflashable mode. Select the option `Secure bootloder mode (One-time flash)` and change it to `Reflashable`.

### Partition table
Press _ESC_ again and change to the `Partition Table` menu. We need to change the offset of the partition table because the bootloader (which is stored in flash _before_ the partition table) will grow in size. Change the offset of the partition table from 0x8000 to 0x10000.

After you are done, press _ESC_ again until you are prompted to save. Press _Y_ to save and exit.

## 3. Generate secure boot signing key
Before we build the application, first we need to generate the secure boot signing key by running this command:
```
espsecure.py generate_signing_key secure_boot_signing_key.pem
```

**CAUTION: The secure boot signing key is needed every time you want to upload a new firmware. Make sure not to lose it.**

## 4. Build bootloader

Now build the bootloader:

```
idf.py bootloader
```
The build system will 
- append the public key component of the signing key to the software bootloader, and 
- calculate the secure bootloader key. 

[View output from idf.py bootloader](idf-bootloader.md)
      
## 5. Burn secure bootloader key into eFuse

The secure bootloader key is stored in the following path: _build/bootloader/secure-bootloader-key-256.bin_. Now we need to burn this key into the BLOCK2 eFuse:

```
espefuse.py burn_key secure_boot_v1 build/bootloader/secure-bootloader-key-256.bin
```
Follow the instructions and type `BURN` to finish setting the eFuse.

**NOTE: If using the Hiletgo ESP-WROOM-32 development board, you may need to hold down the IO0 button on the ESP32 when the build system tries to connect to the ESP32's serial port. If you do not hold down the IO0 button during this step, the build system may fail to detect the serial port.**

## 6. Upload the bootloader
Now upload the bootloader to the ESP32:

```
esptool.py write_flash 0x1000 build/bootloader/bootloader.bin
```
Note: 
- When secure boot is enabled, the bootloader is not uploaded automatically when we run "idf.py build flash monitor". We have to upload it manually using the "write_flash" command.
- The first time the device runs with secure boot enabled, the device will generate the digest for us. So we do not have to supply the digest this first time.

## 7. Flash app and others
Finally, build and flash the rest of the application:

```
idf.py build flash monitor
```

You should see the bootloader and application proceed as normal. In fact, if you closely inspect the bootloader output, you will see that secure boot has been enabled.

[View idf.py build output](idf-build.md)

[View first boot output](First-boot-output.md)

[View later boot output](Later-boot-output.md)

## Verify Secure Boot is Working

Now we will prove that secure boot is working as intended. We are going to modify the application and show that the secure boot mechanism prevents the modified application from running. 

### 8. Change application code
Open the application code (_main/station_example_main.c_) in an editor such as VSCode. Change the code in any way you like. In my case, I have changed the TAG variable from "wifi station" to "wifi station BRYAN":

![image](https://user-images.githubusercontent.com/11084018/159783086-c50e6ea0-d61a-4153-bfcf-aa9550027901.png)

Save your changes and open the configuration menu:

```
idf.py menuconfig
```

Navigate to `Security Features` and disable the option `Enable hardware Secure Boot in bootloader`. This will temporarily disable secure boot. After disabling the option, leave the configuration menu and save the changes.

Now build the application:

```
idf.py build
```

Since we disabled secure boot, the bootloader has also been modified, and it will automatically be uploaded using the typical command (`idf.py flash`). For now, we will only upload the modified application, but not the bootloader. To upload the application only, we need to know what address the application is uploaded to the flash (this address is affected by the partition table offset, which we modified earlier). Luckily, the output from the build command tells us which address the application will be flashed to, as shown in the following screenshot:

![image](https://user-images.githubusercontent.com/11084018/159786416-1dca80bc-0dd9-4bac-b3a1-b220cd9623e2.png)

Assuming your flash address is also 0x20000, you can use the following command to upload the application to the ESP32:

```
esptool.py write_flash 0x20000 build/wifi_station.bin
```

Now open the serial monitor:

```
idf.py monitor
```

You should see that the ROM bootloader successfully loads the software bootloader, but the software bootloader fails to load the application because it cannot verify the application's signature:

![image](https://user-images.githubusercontent.com/11084018/159786794-e3abb679-7d38-422c-864f-94f63ac9b562.png)

### Upload bootloader

Now upload the bootloader image, and observe how the ROM bootloader now fails to load the software bootloader:

```
esptool.py write_flash 0x1000 build/bootloader/bootloader.bin
```

**NOTE**: You may need to add the flag *--force* to the command as shown below
```
esptool.py write_flash --force 0x1000 build/bootloader/bootloader.bin
```

You should see output similar to the following:

![image](https://user-images.githubusercontent.com/11084018/160002426-02cae2dd-4089-4542-8447-0a4438fbb758.png)

## Update the Application After Secure Boot is Enabled

Now we will see how the user can update the application and bootloader. Keep in mind that the bootloader can only be updated in Reflashable Mode.

Open the configuration menu again, and re-enable the option `Enable hardware Secure Boot in bootloader`. Make sure to also set the option `Secure bootloader mode` to `Reflashable`. Leave and save your changes.

Now build the bootloader:

```
idf.py bootloader
```

The bootloader is prefixed with the SHA-512 digest that the ROM uses to verify the bootloader. The build system can generate this digest since we supply the secure boot signing key (which is used to derive the secure bootloader key). Recall that the digest should be stored at offset 0x0 in the flash. Therefore, we now need to upload the bootloader, which is prefixed with the bootloader digest, to address 0x0.

```
esptool.py write_flash 0x0 build/bootloader/bootloader-reflash-digest.bin
```

**NOTE**: You may need to add the flag *--force* to the command as shown below
```
esptool.py write_flash --force 0x0 build/bootloader/bootloader-reflash-digest.bin
```
The write_flash command is writing both the bootloader and the bootloader digest to the flash (they are part of the same binary).

Finally, build and upload the rest of the application as normal:

```
idf.py build flash monitor
```

You should see the bootloader and application load successfully, and the application should contain the changes we made: 

![image](https://user-images.githubusercontent.com/11084018/160005397-17029f71-819f-4cfe-8b28-9fcba554d4b2.png)

## Enable Flash Encryption After Secure Boot Is Enabled

If flash encryption has never been enabled on your ESP32, then follow [this procedure](https://github.com/PBearson/ESP32_Flash_Encryption_Tutorial#enable-flash-encryption) to enable it. Since the partition table offset has already been set to 0x10000, there is no need to modify it further. Since secure boot is enabled, make sure to build and flash the bootloader separately, as described above.

## Notes

### A Note about Flash Encryption

If you have previously enabled flash encryption (Development Mode) on this ESP32, then you can still follow this tutorial without making too many changes. The only differences are the following:

* Replace `idf.py flash` with `idf.py encrypted-flash`
* Any command starting with `esptool.py write_flash` must contain the `--encrypt` argument; for example: `esptool.py write_flash --encrypt 0x1000 build/bootloader/bootloader.bin`
