<pre>
iot@iot-VirtualBox:~/Documents/ESP32_Secure_Boot_Tutorial$ idf.py bootloader
Executing action: bootloader
Running ninja in directory /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build
Executing "ninja bootloader"...
[0/1] Re-running CMake...
-- Building ESP-IDF components for target esp32
-- Project sdkconfig file /home/iot/Documents/ESP32_Secure_Boot_Tutorial/sdkconfig
-- App "wifi_station" version: 4bb7792
-- Adding linker script /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/esp-idf/esp_system/ld/memory.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_system/ld/esp32/sections.ld.in
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.api.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.libgcc.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.newlib-data.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.syscalls.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.newlib-funcs.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.newlib-time.ld
-- Adding linker script /home/iot/esp/esp-idf/components/soc/esp32/ld/esp32.peripherals.ld
-- Components: app_trace app_update asio bootloader bootloader_support bt cbor cmock coap console cxx driver efuse esp-tls esp32 esp_adc_cal esp_common esp_eth esp_event esp_gdbstub esp_hid esp_http_client esp_http_server esp_https_ota esp_https_server esp_hw_support esp_ipc esp_lcd esp_local_ctrl esp_netif esp_phy esp_pm esp_ringbuf esp_rom esp_serial_slave_link esp_system esp_timer esp_websocket_client esp_wifi espcoredump esptool_py expat fatfs freemodbus freertos hal heap idf_test ieee802154 jsmn json libsodium log lwip main mbedtls mdns mqtt newlib nghttp nvs_flash openssl openthread partition_table perfmon protobuf-c protocomm pthread sdmmc soc spi_flash spiffs tcp_transport tcpip_adapter tinyusb ulp unity usb vfs wear_levelling wifi_provisioning wpa_supplicant xtensa
-- Component paths: /home/iot/esp/esp-idf/components/app_trace /home/iot/esp/esp-idf/components/app_update /home/iot/esp/esp-idf/components/asio /home/iot/esp/esp-idf/components/bootloader /home/iot/esp/esp-idf/components/bootloader_support /home/iot/esp/esp-idf/components/bt /home/iot/esp/esp-idf/components/cbor /home/iot/esp/esp-idf/components/cmock /home/iot/esp/esp-idf/components/coap /home/iot/esp/esp-idf/components/console /home/iot/esp/esp-idf/components/cxx /home/iot/esp/esp-idf/components/driver /home/iot/esp/esp-idf/components/efuse /home/iot/esp/esp-idf/components/esp-tls /home/iot/esp/esp-idf/components/esp32 /home/iot/esp/esp-idf/components/esp_adc_cal /home/iot/esp/esp-idf/components/esp_common /home/iot/esp/esp-idf/components/esp_eth /home/iot/esp/esp-idf/components/esp_event /home/iot/esp/esp-idf/components/esp_gdbstub /home/iot/esp/esp-idf/components/esp_hid /home/iot/esp/esp-idf/components/esp_http_client /home/iot/esp/esp-idf/components/esp_http_server /home/iot/esp/esp-idf/components/esp_https_ota /home/iot/esp/esp-idf/components/esp_https_server /home/iot/esp/esp-idf/components/esp_hw_support /home/iot/esp/esp-idf/components/esp_ipc /home/iot/esp/esp-idf/components/esp_lcd /home/iot/esp/esp-idf/components/esp_local_ctrl /home/iot/esp/esp-idf/components/esp_netif /home/iot/esp/esp-idf/components/esp_phy /home/iot/esp/esp-idf/components/esp_pm /home/iot/esp/esp-idf/components/esp_ringbuf /home/iot/esp/esp-idf/components/esp_rom /home/iot/esp/esp-idf/components/esp_serial_slave_link /home/iot/esp/esp-idf/components/esp_system /home/iot/esp/esp-idf/components/esp_timer /home/iot/esp/esp-idf/components/esp_websocket_client /home/iot/esp/esp-idf/components/esp_wifi /home/iot/esp/esp-idf/components/espcoredump /home/iot/esp/esp-idf/components/esptool_py /home/iot/esp/esp-idf/components/expat /home/iot/esp/esp-idf/components/fatfs /home/iot/esp/esp-idf/components/freemodbus /home/iot/esp/esp-idf/components/freertos /home/iot/esp/esp-idf/components/hal /home/iot/esp/esp-idf/components/heap /home/iot/esp/esp-idf/components/idf_test /home/iot/esp/esp-idf/components/ieee802154 /home/iot/esp/esp-idf/components/jsmn /home/iot/esp/esp-idf/components/json /home/iot/esp/esp-idf/components/libsodium /home/iot/esp/esp-idf/components/log /home/iot/esp/esp-idf/components/lwip /home/iot/Documents/ESP32_Secure_Boot_Tutorial/main /home/iot/esp/esp-idf/components/mbedtls /home/iot/esp/esp-idf/components/mdns /home/iot/esp/esp-idf/components/mqtt /home/iot/esp/esp-idf/components/newlib /home/iot/esp/esp-idf/components/nghttp /home/iot/esp/esp-idf/components/nvs_flash /home/iot/esp/esp-idf/components/openssl /home/iot/esp/esp-idf/components/openthread /home/iot/esp/esp-idf/components/partition_table /home/iot/esp/esp-idf/components/perfmon /home/iot/esp/esp-idf/components/protobuf-c /home/iot/esp/esp-idf/components/protocomm /home/iot/esp/esp-idf/components/pthread /home/iot/esp/esp-idf/components/sdmmc /home/iot/esp/esp-idf/components/soc /home/iot/esp/esp-idf/components/spi_flash /home/iot/esp/esp-idf/components/spiffs /home/iot/esp/esp-idf/components/tcp_transport /home/iot/esp/esp-idf/components/tcpip_adapter /home/iot/esp/esp-idf/components/tinyusb /home/iot/esp/esp-idf/components/ulp /home/iot/esp/esp-idf/components/unity /home/iot/esp/esp-idf/components/usb /home/iot/esp/esp-idf/components/vfs /home/iot/esp/esp-idf/components/wear_levelling /home/iot/esp/esp-idf/components/wifi_provisioning /home/iot/esp/esp-idf/components/wpa_supplicant /home/iot/esp/esp-idf/components/xtensa
-- Configuring done
-- Generating done
-- Build files have been written to: /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build
[1/6] Generating ../../partition_table/partition-table-unsigned.bin
Partition table binary generated. Contents:
*******************************************************************************
# ESP-IDF Partition Table
# Name, Type, SubType, Offset, Size, Flags
nvs,data,nvs,0x11000,24K,
phy_init,data,phy,0x17000,4K,
factory,app,factory,0x20000,1M,
*******************************************************************************
[2/6] Generating ../../partition_table/partition-table.bin
espsecure.py v3.2-dev
Signed 3072 bytes of data from /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/partition_table/partition-table-unsigned.bin with key /home/iot/Documents/ESP32_Secure_Boot_Tutorial/secure_boot_signing_key.pem
[3/6] Performing configure step for 'bootloader'
-- Building ESP-IDF components for target esp32
-- Project sdkconfig file /home/iot/Documents/ESP32_Secure_Boot_Tutorial/sdkconfig
-- Adding linker script /home/iot/esp/esp-idf/components/soc/esp32/ld/esp32.peripherals.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.api.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.libgcc.ld
-- Adding linker script /home/iot/esp/esp-idf/components/esp_rom/esp32/ld/esp32.rom.newlib-funcs.ld
-- Adding linker script /home/iot/esp/esp-idf/components/bootloader/subproject/main/ld/esp32/bootloader.ld
-- Adding linker script /home/iot/esp/esp-idf/components/bootloader/subproject/main/ld/esp32/bootloader.rom.ld
-- Components: bootloader bootloader_support efuse esp32 esp_common esp_hw_support esp_rom esp_system esptool_py freertos hal log main micro-ecc newlib partition_table soc spi_flash xtensa
-- Component paths: /home/iot/esp/esp-idf/components/bootloader /home/iot/esp/esp-idf/components/bootloader_support /home/iot/esp/esp-idf/components/efuse /home/iot/esp/esp-idf/components/esp32 /home/iot/esp/esp-idf/components/esp_common /home/iot/esp/esp-idf/components/esp_hw_support /home/iot/esp/esp-idf/components/esp_rom /home/iot/esp/esp-idf/components/esp_system /home/iot/esp/esp-idf/components/esptool_py /home/iot/esp/esp-idf/components/freertos /home/iot/esp/esp-idf/components/hal /home/iot/esp/esp-idf/components/log /home/iot/esp/esp-idf/components/bootloader/subproject/main /home/iot/esp/esp-idf/components/bootloader/subproject/components/micro-ecc /home/iot/esp/esp-idf/components/newlib /home/iot/esp/esp-idf/components/partition_table /home/iot/esp/esp-idf/components/soc /home/iot/esp/esp-idf/components/spi_flash /home/iot/esp/esp-idf/components/xtensa
-- Configuring done
-- Generating done
-- Build files have been written to: /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader
[4/6] Performing build step for 'bootloader'
[1/97] Building C object esp-idf/efuse/CMakeFiles/__idf_efuse.dir/esp32/esp_efuse_fields.c.obj
[2/97] <b>Generating secure-bootloader-key-256.bin</b>
espsecure.py v3.2-dev
SHA-256 digest of private key /home/iot/Documents/ESP32_Secure_Boot_Tutorial/secure_boot_signing_key.pem written to /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/secure-bootloader-key-256.bin
[3/97] Building C object esp-idf/efuse/CMakeFiles/__idf_efuse.dir/esp32/esp_efuse_table.c.obj
[4/97] Building C object esp-idf/efuse/CMakeFiles/__idf_efuse.dir/src/esp_efuse_api.c.obj
[5/97] Building C object esp-idf/efuse/CMakeFiles/__idf_efuse.dir/src/esp_efuse_fields.c.obj
[6/97] Building C object esp-idf/efuse/CMakeFiles/__idf_efuse.dir/esp32/esp_efuse_utility.c.obj
[7/97] Building C object esp-idf/efuse/CMakeFiles/__idf_efuse.dir/src/esp_efuse_api_key_esp32.c.obj
[8/97] Building C object esp-idf/efuse/CMakeFiles/__idf_efuse.dir/src/esp_efuse_utility.c.obj
[9/97] Building C object esp-idf/esp_system/CMakeFiles/__idf_esp_system.dir/esp_err.c.obj
[10/97] Building C object esp-idf/esp_hw_support/CMakeFiles/__idf_esp_hw_support.dir/compare_set.c.obj
[11/97] Building C object esp-idf/esp_hw_support/CMakeFiles/__idf_esp_hw_support.dir/cpu_util.c.obj
[12/97] Building C object esp-idf/esp_hw_support/CMakeFiles/__idf_esp_hw_support.dir/port/esp32/rtc_clk_init.c.obj
[13/97] Building C object esp-idf/esp_hw_support/CMakeFiles/__idf_esp_hw_support.dir/port/esp32/rtc_clk.c.obj
[14/97] Building C object esp-idf/esp_hw_support/CMakeFiles/__idf_esp_hw_support.dir/port/esp32/rtc_init.c.obj
[15/97] Building C object esp-idf/esp_hw_support/CMakeFiles/__idf_esp_hw_support.dir/port/esp32/rtc_pm.c.obj
[16/97] Building C object esp-idf/esp_hw_support/CMakeFiles/__idf_esp_hw_support.dir/port/esp32/rtc_time.c.obj
[17/97] Building C object esp-idf/esp_hw_support/CMakeFiles/__idf_esp_hw_support.dir/port/esp32/rtc_sleep.c.obj
[18/97] Building C object esp-idf/esp_hw_support/CMakeFiles/__idf_esp_hw_support.dir/port/esp32/chip_info.c.obj
[19/97] Building C object esp-idf/esp_hw_support/CMakeFiles/__idf_esp_hw_support.dir/port/esp32/rtc_wdt.c.obj
[20/97] Building C object esp-idf/xtensa/CMakeFiles/__idf_xtensa.dir/xt_trax.c.obj
[21/97] Building C object esp-idf/esp_common/CMakeFiles/__idf_esp_common.dir/src/esp_err_to_name.c.obj
[22/97] Building C object esp-idf/esp_rom/CMakeFiles/__idf_esp_rom.dir/patches/esp_rom_sys.c.obj
[23/97] Building ASM object esp-idf/esp_rom/CMakeFiles/__idf_esp_rom.dir/patches/esp_rom_longjmp.S.obj
[24/97] Building C object esp-idf/esp_rom/CMakeFiles/__idf_esp_rom.dir/patches/esp_rom_uart.c.obj
[25/97] Building C object esp-idf/log/CMakeFiles/__idf_log.dir/log.c.obj
[26/97] Building C object esp-idf/log/CMakeFiles/__idf_log.dir/log_buffers.c.obj
[27/97] Building C object esp-idf/log/CMakeFiles/__idf_log.dir/log_noos.c.obj
[28/97] Linking C static library esp-idf/log/liblog.a
[29/97] Linking C static library esp-idf/esp_rom/libesp_rom.a
[30/97] Linking C static library esp-idf/esp_common/libesp_common.a
[31/97] Linking C static library esp-idf/xtensa/libxtensa.a
[32/97] Linking C static library esp-idf/esp_hw_support/libesp_hw_support.a
[33/97] Linking C static library esp-idf/esp_system/libesp_system.a
[34/97] Linking C static library esp-idf/efuse/libefuse.a
[35/97] <b>Generating signature_verification_key.bin</b>
espsecure.py v3.2-dev
/home/iot/Documents/ESP32_Secure_Boot_Tutorial/secure_boot_signing_key.pem public key extracted to /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/esp-idf/bootloader_support/signature_verification_key.bin
[36/97] Generating ../../signature_verification_key.bin.S
[37/97] Building C object esp-idf/hal/CMakeFiles/__idf_hal.dir/wdt_hal_iram.c.obj
[38/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/esp32/bootloader_esp32.c.obj
[39/97] Building C object esp-idf/hal/CMakeFiles/__idf_hal.dir/mpu_hal.c.obj
[40/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/lldesc.c.obj
[41/97] Building C object esp-idf/hal/CMakeFiles/__idf_hal.dir/cpu_hal.c.obj
[42/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/soc_include_legacy_warn.c.obj
[43/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/adc_periph.c.obj
[44/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/gpio_periph.c.obj
[45/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/dac_periph.c.obj
[46/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/i2c_periph.c.obj
[47/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/i2s_periph.c.obj
[48/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/interrupts.c.obj
[49/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/lcd_periph.c.obj
[50/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/ledc_periph.c.obj
[51/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/mcpwm_periph.c.obj
[52/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/pcnt_periph.c.obj
[53/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/rmt_periph.c.obj
[54/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/sdmmc_periph.c.obj
[55/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/rtc_io_periph.c.obj
[56/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/spi_periph.c.obj
[57/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/sdio_slave_periph.c.obj
[58/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/sigmadelta_periph.c.obj
[59/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/timer_periph.c.obj
[60/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/uart_periph.c.obj
[61/97] Building C object esp-idf/soc/CMakeFiles/__idf_soc.dir/esp32/touch_sensor_periph.c.obj
[62/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_common_loader.c.obj
[63/97] Building C object esp-idf/spi_flash/CMakeFiles/__idf_spi_flash.dir/esp32/spi_flash_rom_patch.c.obj
[64/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_common.c.obj
[65/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_random_esp32.c.obj
[66/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_clock_init.c.obj
[67/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_mem.c.obj
[68/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_flash.c.obj
[69/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_random.c.obj
[70/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_flash_config_esp32.c.obj
[71/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_utility.c.obj
[72/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/flash_encrypt.c.obj
[73/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/secure_boot.c.obj
[74/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/esp_image_format.c.obj
[75/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/flash_partitions.c.obj
[76/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/flash_qio_mode.c.obj
[77/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_efuse_esp32.c.obj
[78/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_clock_loader.c.obj
[79/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_init.c.obj
[80/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_console.c.obj
[81/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_console_loader.c.obj
[82/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/bootloader_panic.c.obj
[83/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/esp32/bootloader_sha.c.obj
[84/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/secure_boot_v1/secure_boot_signatures_bootloader.c.obj
[85/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/secure_boot_v1/secure_boot.c.obj
[86/97] Building C object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/src/esp32/secure_boot_secure_features.c.obj
[87/97] Building ASM object esp-idf/bootloader_support/CMakeFiles/__idf_bootloader_support.dir/__/__/signature_verification_key.bin.S.obj
[88/97] Linking C static library esp-idf/bootloader_support/libbootloader_support.a
[89/97] Building C object esp-idf/main/CMakeFiles/__idf_main.dir/bootloader_start.c.obj
[90/97] Linking C static library esp-idf/spi_flash/libspi_flash.a
[91/97] Linking C static library esp-idf/soc/libsoc.a
[92/97] Linking C static library esp-idf/hal/libhal.a
[93/97] Linking C static library esp-idf/main/libmain.a
[94/97] Linking C executable bootloader.elf
==============================================================================
<b>Bootloader built and secure digest generated.</b>
Secure boot enabled, so bootloader not flashed automatically.
Burn secure boot key to efuse using:
        /home/iot/.espressif/python_env/idf4.4_py3.8_env/bin/python /home/iot/esp/esp-idf/components/esptool_py/esptool/espefuse.py burn_key secure_boot_v1 /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/secure-bootloader-key-256.bin
First time flash command is:
        /home/iot/.espressif/python_env/idf4.4_py3.8_env/bin/python  /home/iot/esp/esp-idf/components/esptool_py/esptool/esptool.py --chip esp32 --port=(PORT) --baud=(BAUD) --before=default_reset --after=no_reset write_flash --flash_mode dio --flash_freq 40m --flash_size 2MB 0x1000 /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/bootloader.bin
==============================================================================
To reflash the bootloader after initial flash:
        /home/iot/.espressif/python_env/idf4.4_py3.8_env/bin/python  /home/iot/esp/esp-idf/components/esptool_py/esptool/esptool.py --chip esp32 --port=(PORT) --baud=(BAUD) --before=default_reset --after=no_reset write_flash --flash_mode dio --flash_freq 40m --flash_size 2MB 0x0 /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/bootloader-reflash-digest.bin
==============================================================================
* After first boot, only re-flashes of this kind (with same key) will be accepted.
* Not recommended to re-use the same secure boot keyfile on multiple production devices.
[95/97] Generating binary image from built executable
esptool.py v3.2-dev
Merged 1 ELF section
Generated /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/bootloader.bin
[96/97] cd /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/esp-idf/esptool_py && /home/iot/.espressif/python_env/idf4.4_py3.8_env/bin/python /home/iot/esp/esp-idf/components/partition_table/check_sizes.py --offset 0x10000 bootloader 0x1000 /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/bootloader.bin
Bootloader binary size 0x92e0 bytes. 0x5d20 bytes (39%) free.
[97/97] Generating bootloader-reflash-digest.bin
DIGEST /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/bootloader-reflash-digest.bin
espsecure.py v3.2-dev
Using 256-bit key
digest+image written to /home/iot/Documents/ESP32_Secure_Boot_Tutorial/build/bootloader/bootloader-reflash-digest.bin
[5/5] Completed 'bootloader'

Bootloader build complete.
</pre>
