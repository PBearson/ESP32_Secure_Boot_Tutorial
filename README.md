# ESP32 Secure Boot Tutorial

This project demonstrates how to enable secure boot (Reflashable Mode) on the ESP32. We will show the procedure for enabling secure boot for the current application, and we will verify that secure boot is enabled. Finally, we will show how the user can upload a new firmware as long as they have the correct signing key, and we will show how the user can update the bootloader due to the Reflashable Mode setting.

## Prerequisites

For this project, you need:

* An ESP32 development board, such as Hiletgo ESP-WROOM-32.
* A Linux Virtual Machine with ESP-IDF (version 4) installed.

You are encouraged to use the following Ubuntu VM: https://www.dropbox.com/s/0g7w8qduzj2rb1k/UbuntuIoT.ova?dl=0

Follow these instructions to install ESP-IDF version 4.4: https://docs.espressif.com/projects/esp-idf/en/v4.4/esp32/get-started/index.html#get-started-get-prerequisites

After installing ESP-IDF, download this repository into your VM:

```
git clone https://github.com/PBearson/ESP32_Secure_Boot_Tutorial.git
```

### Disable Flash Encryption

With flash encryption enabled, you cannot upload plaintext firmware images to the ESP32, and this procedure will fail. If you have enabled Flash Encryption in Development Mode, you should first disable it by following [these instructions](https://github.com/PBearson/ESP32_Flash_Encryption_Tutorial#disable-flash-encryption). Flash Encryption in Release Mode cannot be disabled.

## Enable Secure Boot

TODO

### Configure the WiFi Application

Open a terminal, and navigate to the root directory of this project. Open the project configuration menu:

```
idf.py menuconfig
```

Using the up/down arrow keys, navigate to the `Security Features` menu, and press _enter_ to go into the menu. Select the option `Enable hardware Secure Boot in bootloader`. The secure bootloader mode will be set to One-time flash. We need to change it to Reflashable mode. Select the option `Secure bootloder mode (One-time flash)` and change it to `Reflashable`.

Press _ESC_ and change to the `Partition Table` menu. We need to change the offset of the partition table because the bootloader (which is stored in flash _before_ the partition table) will grow in size. Change the offset of the partition table from 0x8000 to 0x10000.

After you are done, press _ESC_ again until you are prompted to save. Press _Y_ to save and exit.

Build bootloader:

```
idf.py bootloader
```

Generate signing key:

```
espsecure.py generate_signing_key secure_boot_signing_key.pem
```

The secure boot signing key is needed every time you want to upload a new firmware. Make sure not to lose it.

Burn secure boot key to eFuse:

```
espefuse.py burn_key secure_boot_v1 build/bootloader/secure-bootloader-key-256.bin
```

**NOTE: If using the Hiletgo ESP-WROOM-32 development board, you may need to hold down the IO0 button on the ESP32 when the build system tries to connect to the ESP32's serial port. If you do not hold down the IO0 button during this step, the build system may fail to detect the serial port.**

You do not need to save the secure bootloader key. In Secure Boot Reflashable mode, the build system derives the secure bootloader key from the secure boot signing key. Therefore, you only need to save the secure boot signing key.

Upload bootloader to ESP32:

```
esptool.py write_flash 0x1000 build/bootloader/bootloader.bin
```

Build and flash the rest of the application:

```
idf.py build flash monitor

```

### Verify Secure Boot is Working

TODO try to change the application and re-upload it. 

## Upload a New Application

TODO modify application.

```
idf.py build flash monitor
```

## Upload a New Bootloader

TODO modify bootloader.

```
esptool.py write_flash 0x0 build/bootloader/bootloader-reflash-digest.bin
```

This bootloader image contains a SHA-512 digest within the first 0x1000 bytes. 
