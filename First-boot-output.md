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
I (31) boot: ESP-IDF v4.4-dirty 2nd stage bootloader
I (31) boot: compile time 08:58:55
I (31) boot: chip revision: 1
I (34) boot_comm: chip revision: 1, min. bootloader chip revision: 0
I (41) boot.esp32: SPI Speed      : 40MHz
I (45) boot.esp32: SPI Mode       : DIO
I (50) boot.esp32: SPI Flash Size : 2MB
I (55) boot: Enabling RNG early entropy source...
I (60) boot: Partition Table:
I (64) boot: ## Label            Usage          Type ST Offset   Length
I (71) boot:  0 nvs              WiFi data        01 02 00011000 00006000
I (78) boot:  1 phy_init         RF data          01 01 00017000 00001000
I (86) boot:  2 factory          factory app      00 00 00020000 00100000
I (93) boot: End of partition table
I (97) boot_comm: chip revision: 1, min. application chip revision: 0
I (105) esp_image: segment 0: paddr=00020020 vaddr=3f400020 size=13e30h ( 81456) map
I (143) esp_image: segment 1: paddr=00033e58 vaddr=3ffb0000 size=03834h ( 14388) load
I (149) esp_image: segment 2: paddr=00037694 vaddr=40080000 size=08984h ( 35204) load
I (163) esp_image: segment 3: paddr=00040020 vaddr=400d0020 size=6e1a0h (450976) map
I (327) esp_image: segment 4: paddr=000ae1c8 vaddr=40088984 size=0b960h ( 47456) load
I (346) esp_image: segment 5: paddr=000b9b30 vaddr=50000000 size=00010h (    16) load
I (347) esp_image: segment 6: paddr=000b9b48 vaddr=00000000 size=06438h ( 25656) 
I (361) <b>esp_image: Verifying image signature...</b>
I (707) boot: Loaded app from partition at offset 0x20000
I (707) boot_comm: chip revision: 1, min. application chip revision: 0
I (709) esp_image: segment 0: paddr=00001020 vaddr=3fff0038 size=0275ch ( 10076) 
I (720) esp_image: segment 1: paddr=00003784 vaddr=40078000 size=05c58h ( 23640) 
I (731) esp_image: segment 2: paddr=000093e4 vaddr=40080400 size=00ed0h (  3792) 
W (735) <b>secure_boot_v1: Using pre-loaded secure boot key in EFUSE block 2</b>
I (741) <b>secure_boot_v1: Generating secure boot digest...</b>
I (791) secure_boot_v1: Digest generation complete.
I (791) boot: Checking secure boot...
I (791) efuse: Batch mode of writing fields is enabled
I (796) secure_boot_v1: blowing secure boot efuse...
I (801) secure_boot: Read & write protecting new key...
I (807) <b>secure_boot: Disable JTAG...</b>
I (812) secure_boot: Disable ROM BASIC interpreter fallback...
I (829) efuse: Batch mode. Prepared fields are committed
I (829) secure_boot_v1: secure boot is now enabled for bootloader image
I (834) boot: Disabling RNG early entropy source...
I (850) cpu_start: Pro cpu up.
I (851) cpu_start: Starting app cpu, entry point is 0x40081174
0x40081174: call_start_cpu1 at /home/iot/esp/esp-idf/components/esp_system/port/cpu_start.c:156

I (0) cpu_start: App cpu up.
I (865) cpu_start: Pro cpu start user code
I (865) cpu_start: cpu freq: 160000000
I (865) cpu_start: Application information:
I (869) cpu_start: Project name:     wifi_station
I (875) cpu_start: App version:      4bb7792
I (880) cpu_start: Compile time:     Apr 13 2022 09:09:24
I (886) cpu_start: ELF file SHA256:  1379ea420aef69e4...
I (892) cpu_start: ESP-IDF:          v4.4-dirty
I (897) heap_init: Initializing. RAM available for dynamic allocation:
I (904) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (910) heap_init: At 3FFB74E0 len 00028B20 (162 KiB): DRAM
I (916) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (923) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (929) heap_init: At 400942E4 len 0000BD1C (47 KiB): IRAM
I (937) spi_flash: detected chip: generic
I (940) spi_flash: flash io: dio
W (944) spi_flash: Detected size(4096k) larger than the size in the binary image header(2048k). Using the size in the binary image header.
I (958) cpu_start: Starting scheduler on PRO CPU.
I (0) cpu_start: Starting scheduler on APP CPU.
I (1051) wifi station: ESP_WIFI_MODE_STA
I (1081) wifi:wifi driver task: 3ffc0060, prio:23, stack:6656, core=0
I (1081) system_api: Base MAC address is not set
I (1081) system_api: read default base MAC address from EFUSE
I (1091) wifi:wifi firmware version: 7679c42
I (1091) wifi:wifi certification version: v7.0
I (1091) wifi:config NVS flash: enabled
I (1091) wifi:config nano formating: disabled
I (1101) wifi:Init data frame dynamic rx buffer num: 32
I (1101) wifi:Init management frame dynamic rx buffer num: 32
I (1111) wifi:Init management short buffer num: 32
I (1111) wifi:Init dynamic tx buffer num: 32
I (1121) wifi:Init static rx buffer size: 1600
I (1121) wifi:Init static rx buffer num: 10
I (1131) wifi:Init dynamic rx buffer num: 32
I (1131) wifi_init: rx ba win: 6
I (1131) wifi_init: tcpip mbox: 32
I (1141) wifi_init: udp mbox: 6
I (1141) wifi_init: tcp mbox: 6
I (1141) wifi_init: tcp tx win: 5744
I (1151) wifi_init: tcp rx win: 5744
I (1151) wifi_init: tcp mss: 1440
I (1161) wifi_init: WiFi IRAM OP enabled
I (1161) wifi_init: WiFi RX IRAM OP enabled
I (1201) phy_init: phy_version 4670,719f9f6,Feb 18 2021,17:07:07
W (1201) phy_init: failed to load RF calibration data (0x1102), falling back to full calibration
I (1361) wifi:mode : sta (4c:11:ae:a4:54:b0)
I (1361) wifi:enable tsf
I (1361) wifi station: wifi_init_sta finished.
I (2031) wifi:new:<6,0>, old:<1,0>, ap:<255,255>, sta:<6,0>, prof:1
I (2951) wifi:state: init -> auth (b0)
I (2961) wifi:state: auth -> assoc (0)
I (2971) wifi:state: assoc -> run (10)
W (2981) wifi:<ba-add>idx:0 (ifx:0, 00:7f:28:d9:41:4a), tid:7, ssn:0, winSize:64
I (2991) wifi:connected with CWS5Q, aid = 21, channel 6, BW20, bssid = 00:7f:28:d9:41:4a
I (2991) wifi:security: WPA2-PSK, phy: bgn, rssi: -75
I (3001) wifi:pm start, type: 1

I (3051) wifi:AP's beacon interval = 102400 us, DTIM period = 1
W (4381) wifi:<ba-add>idx:1 (ifx:0, 00:7f:28:d9:41:4a), tid:0, ssn:0, winSize:64
I (5061) esp_netif_handlers: sta ip: 192.168.1.19, mask: 255.255.255.0, gw: 192.168.1.1
I (5061) wifi station: got ip:192.168.1.19
I (5061) wifi station: connected to ap SSID:XXX password:XXXXXX
</pre>
