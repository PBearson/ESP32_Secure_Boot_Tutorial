<pre>
iot@iot-VirtualBox:~/Documents/ESP32_Secure_Boot_Tutorial$ idf.py build flash monitor
Executing action: all (aliases: build)
Running ninja in directory /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build
Executing "ninja all"...
[2/965] Performing build step for 'bootloader'
[1/1] cd /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/esp-idf/esptool_py && /home/iot/.espressif/python_env/idf4.4_py3.8_env/bin/python /home/iot/esp/esp-idf/components/partition_table/check_sizes.py --offset 0x10000 bootloader 0x1000 /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/bootloader.bin
Bootloader binary size 0x92e0 bytes. 0x5d20 bytes (39%) free.
[514/963] <b>Generating ../../signature_verification_key.bin</b>
espsecure.py v3.2-dev
/home/iot/Documents/ESP32_Secure_Boot_Tutorial/secure_boot_signing_key.pem public key extracted to /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/signature_verification_key.bin
[961/963] Generating binary image from built executable
esptool.py v3.2-dev
Merged 25 ELF sections
Generated /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/wifi_station-unsigned.bin
[962/963] <b>Generating signed binary image</b>
espsecure.py v3.2-dev
Signed 655280 bytes of data from /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/wifi_station-unsigned.bin with key /home/iot/Documents/ESP32_Secure_Boot_Tutorial/secure_boot_signing_key.pem
Generated signed binary image /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/wifi_station.bin from /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/wifi_station-unsigned.bin
[963/963] cd /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/esp-idf/esptool_py &&...rtition-table.bin /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/wifi_station.bin
wifi_station.bin binary size 0x9fff4 bytes. Smallest app partition is 0x100000 bytes. 0x6000c bytes (38%) free.
Executing action: flash
Serial port /dev/ttyUSB0
Connecting...
Detecting chip type... Unsupported detection protocol, switching and trying again...
Connecting...
Detecting chip type... ESP32
Running ninja in directory /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build
Executing "ninja flash"...
[1/5] cd /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/esp-idf/esptool_py && /ho...rtition-table.bin /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/wifi_station.bin
wifi_station.bin binary size 0x9fff4 bytes. Smallest app partition is 0x100000 bytes. 0x6000c bytes (38%) free.
[2/5] Performing build step for 'bootloader'
[1/1] cd /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/esp-idf/esptool_py && /home/iot/.espressif/python_env/idf4.4_py3.8_env/bin/python /home/iot/esp/esp-idf/components/partition_table/check_sizes.py --offset 0x10000 bootloader 0x1000 /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/bootloader.bin
Bootloader binary size 0x92e0 bytes. 0x5d20 bytes (39%) free.
[2/3] cd /home/iot/esp/esp-idf/components/esptool_py && /home/iot/.espressif/tools/cmak...ot_Tutorial/build" -P /home/iot/esp/esp-idf/components/esptool_py/run_serial_tool.cmake
esptool.py esp32 -p /dev/ttyUSB0 -b 460800 --before=default_reset --after=no_reset write_flash --flash_mode dio --flash_freq 40m --flash_size 2MB 0x20000 wifi_station.bin 0x10000 partition_table/partition-table.bin
</pre>
