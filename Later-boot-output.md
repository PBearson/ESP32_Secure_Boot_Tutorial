<pre>
rst:0x1 (POWERON_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0038,len:10076
ho 0 tail 12 room 4
load:0x40078000,len:23640
ho 0 tail 12 room 4
load:0x40080400,len:3792
0x40080400: _init at ??:?

entry 0x40080694
I (35) boot: ESP-IDF v4.4-dirty 2nd stage bootloader
I (35) boot: compile time 08:58:55
I (36) boot: chip revision: 1
I (39) boot_comm: chip revision: 1, min. bootloader chip revision: 0
I (46) boot.esp32: SPI Speed      : 40MHz
I (50) boot.esp32: SPI Mode       : DIO
I (55) boot.esp32: SPI Flash Size : 2MB
I (59) boot: Enabling RNG early entropy source...
I (65) boot: Partition Table:
I (68) boot: ## Label            Usage          Type ST Offset   Length
I (76) boot:  0 nvs              WiFi data        01 02 00011000 00006000
I (83) boot:  1 phy_init         RF data          01 01 00017000 00001000
I (91) boot:  2 factory          factory app      00 00 00020000 00100000
I (98) boot: End of partition table
I (102) boot_comm: chip revision: 1, min. application chip revision: 0
I (109) esp_image: segment 0: paddr=00020020 vaddr=3f400020 size=13e30h ( 81456) map
I (148) esp_image: segment 1: paddr=00033e58 vaddr=3ffb0000 size=03834h ( 14388) load
I (153) esp_image: segment 2: paddr=00037694 vaddr=40080000 size=08984h ( 35204) load
I (168) esp_image: segment 3: paddr=00040020 vaddr=400d0020 size=6e1a0h (450976) map
I (332) esp_image: segment 4: paddr=000ae1c8 vaddr=40088984 size=0b960h ( 47456) load
I (351) esp_image: segment 5: paddr=000b9b30 vaddr=50000000 size=00010h (    16) load
I (352) esp_image: segment 6: paddr=000b9b48 vaddr=00000000 size=06438h ( 25656) 
I (366) <b>esp_image: Verifying image signature...</b>
I (712) boot: Loaded app from partition at offset 0x20000
I (712) secure_boot_v1: bootloader secure boot is already enabled. No need to generate digest. continuing..
I (717) boot: Checking secure boot...
I (722) secure_boot_v1: bootloader secure boot is already enabled, continuing..
I (730) boot: Disabling RNG early entropy source...
I (746) cpu_start: Pro cpu up.
I (747) cpu_start: Starting app cpu, entry point is 0x40081174
0x40081174: call_start_cpu1 at /home/iot/esp/esp-idf/components/esp_system/port/cpu_start.c:156

I (0) cpu_start: App cpu up.
I (761) cpu_start: Pro cpu start user code
I (761) cpu_start: cpu freq: 160000000
I (761) cpu_start: Application information:
I (765) cpu_start: Project name:     wifi_station
I (771) cpu_start: App version:      4bb7792
I (776) cpu_start: Compile time:     Apr 13 2022 09:09:24
I (782) cpu_start: ELF file SHA256:  1379ea420aef69e4...
I (788) cpu_start: ESP-IDF:          v4.4-dirty
I (793) heap_init: Initializing. RAM available for dynamic allocation:
I (800) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (806) heap_init: At 3FFB74E0 len 00028B20 (162 KiB): DRAM
I (812) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (819) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (825) heap_init: At 400942E4 len 0000BD1C (47 KiB): IRAM
I (833) spi_flash: detected chip: generic
I (836) spi_flash: flash io: dio
W (840) spi_flash: Detected size(4096k) larger than the size in the binary image header(2048k). Using the size in the binary image header.
I (854) cpu_start: Starting scheduler on PRO CPU.
I (0) cpu_start: Starting scheduler on APP CPU.
I (906) wifi station: ESP_WIFI_MODE_STA
I (926) wifi:wifi driver task: 3ffc0578, prio:23, stack:6656, core=0
I (926) system_api: Base MAC address is not set
I (926) system_api: read default base MAC address from EFUSE
I (946) wifi:wifi firmware version: 7679c42
I (946) wifi:wifi certification version: v7.0
I (946) wifi:config NVS flash: enabled
I (946) wifi:config nano formating: disabled
I (946) wifi:Init data frame dynamic rx buffer num: 32
I (956) wifi:Init management frame dynamic rx buffer num: 32
I (956) wifi:Init management short buffer num: 32
I (966) wifi:Init dynamic tx buffer num: 32
I (966) wifi:Init static rx buffer size: 1600
I (966) wifi:Init static rx buffer num: 10
I (976) wifi:Init dynamic rx buffer num: 32
I (976) wifi_init: rx ba win: 6
I (986) wifi_init: tcpip mbox: 32
I (986) wifi_init: udp mbox: 6
I (986) wifi_init: tcp mbox: 6
I (996) wifi_init: tcp tx win: 5744
I (996) wifi_init: tcp rx win: 5744
I (1006) wifi_init: tcp mss: 1440
I (1006) wifi_init: WiFi IRAM OP enabled
I (1006) wifi_init: WiFi RX IRAM OP enabled
I (1016) phy_init: phy_version 4670,719f9f6,Feb 18 2021,17:07:07
W (1176) phy_init: saving new calibration data because of checksum failure, mode(0)
I (1246) wifi:mode : sta (4c:11:ae:a4:54:b0)
I (1246) wifi:enable tsf
I (1246) wifi station: wifi_init_sta finished.
I (1316) wifi:new:<6,0>, old:<1,0>, ap:<255,255>, sta:<6,0>, prof:1
I (1316) wifi:state: init -> auth (b0)
I (1326) wifi:state: auth -> assoc (0)
I (1326) wifi:state: assoc -> run (10)
W (1326) wifi:<ba-add>idx:0 (ifx:0, 00:7f:28:d9:41:4a), tid:7, ssn:0, winSize:64
I (1336) wifi:connected with CWS5Q, aid = 21, channel 6, BW20, bssid = 00:7f:28:d9:41:4a
I (1336) wifi:security: WPA2-PSK, phy: bgn, rssi: -80
I (1346) wifi:pm start, type: 1

I (1416) wifi:AP's beacon interval = 102400 us, DTIM period = 1
W (4406) wifi:<ba-add>idx:1 (ifx:0, 00:7f:28:d9:41:4a), tid:0, ssn:0, winSize:64
I (7406) esp_netif_handlers: sta ip: 192.168.1.19, mask: 255.255.255.0, gw: 192.168.1.1
I (7406) wifi station: got ip:192.168.1.19
I (7406) wifi station: connected to ap SSID:XXX password:XXXXXX
</pre>
