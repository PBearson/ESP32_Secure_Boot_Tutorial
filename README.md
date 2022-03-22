# ESP32 Secure Boot Tutorial

## Prerequisites

TODO for this project, you need

TODO disable flash encryption if enabled, since we need to perform a plaintext upload.

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

Generate signing key:

```
espsecure.py generate_signing_key secure_boot_signing_key.pem
```
