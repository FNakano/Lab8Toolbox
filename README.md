# Lab8Toolbox
Toolbox for ESP32/ESP8266 with Micropython - experimental use

Install Micropython on ESP8266

Download Micropython binary distribution file from https://micropython.org/download/?port=esp8266, erase ESP8266 flash memory and write binary distribution to the device (used on 2024-09-16). 

```
python3 -m esptool --port /dev/ttyUSB0 erase_flash

python3 esptool --port /dev/ttyUSB0 --baud 460800 write_flash --flash_size=detect -fm dout 0 ~/Downloads/ESP8266_GENERIC-20240602-v1.23.0.bin

```

Execute, on the micropython device, commands to connect to a (WiFi) network which accesses the internet. (Use to send commands to the microcontroler board using an IDE such as Thonny - it should be properly configured). This looks confusing (*Why should I use a desktop program to send commands to the microcontroller?*). This text might help: https://github.com/FNakano/micropython-packageTemplate?tab=readme-ov-file#development-setup

Commands to connect to a WiFi network. Replace NETWORK_NAME and PASSWORD with your wifi data, keep the quotes. Connect a device to the Internet may no be safe. This text is intended to explain why a connection is necessary: https://github.com/FNakano/micropython-packageTemplate?tab=readme-ov-file#development-setup

```python
wifi_if=network.WLAN(network.STA_IF) 
wifi_if.active(True) 
staif.connect('NETWORK_NAME', 'PASSWORD')
```

If you just want to install the toolbox:

```python
import mip
mip.install ("github:FNakano/Lab8Toolbox")
```

## What services (functions) do the toolbox provide?

