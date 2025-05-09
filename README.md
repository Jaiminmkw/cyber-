# WI-Fi Penetration Testiong Tool Using ESP8266 NodeMCU Board 
( Evil-Twin and De-authentication attack ) 

## FEATURES :
* Deauthentication of a target WiFi access point
* Evil-Twin AP to capture passwords with password verification against the og access point
* It can do both attacks at the same time, no toggling of the deauther is required.

## DISCLAIMER
The source code given in this public repo is for educational use only and should only be used against your own networks and devices!<br>
Please check the legal regulations in your country before using it.

## Install using Arduino IDE
1. Install Arduino IDE -> version 1.8.19
2. Link : Arduimo : https://downloads.arduino.cc/arduino-1.8.19-windows.exe 
3. In Arduino go to `File` -> `Preferences` add this URL to `Additional Boards Manager URLs` ->
   `https://raw.githubusercontent.com/SpacehuhnTech/arduino/main/package_spacehuhn_index.json`  
4. In Arduino go to `Tools` -> `Board` -> `Boards Manager` search for and install the `deauther` package 
5. Select an `ESP8266 Deauther` board in Arduino under `tools` -> `board`
6. Install port ( COM4 ) 
7. Connect your device and select the serial port in Arduino under `tools` -> `port`
8. Click Upload button

# How to use:
- Connect to the AP named `Hacker` with password `Hacker1802` from your phone/PC.
- Select the target AP you want to attack (list of available APs refreshes every 30secs - page reload is required).
- Click the Start Deauthing button to start kicking devices off the selected network.
- Click the Start Evil-Twin button and optionally reconnect to the newly created AP named same as your target.
- You can stop any of the attacks by visiting `192.168.4.1` while conected to Evil-Twin AP or by resetting the ESP8266.
- Once a correct password is found, AP will be restarted with default ssid `Hacker` / `Hacker1802` and at the bottom of a table you should be able to see something like "Successfully got password for - `TARGET_SSID` - `PASSWORD`
   - If you power down / hard reset the gathered info will be lost


## Optional 
if in case Its does not work 

1. First Problem : Tools option is not Visible in Arduino IDE

   Option 1: Restart Arduino IDE
      - Close Arduino IDE completely.
      - Reopen Arduino IDE and check if the Tools menu appears.

   Option 2: Change Display Scaling (Windows)
      - If you’re using a high-resolution screen, the Tools menu may be hidden. Try this:

         1. Close Arduino IDE.
         2. Right-click Arduino IDE shortcut → Click Properties.
         3. Go to the Compatibility tab.
         4. Click Change high DPI settings.
         5. Enable Override high DPI scaling behavior and set it to System.
         6. Click Apply → Restart Arduino IDE.

2. Second Problem : Fix ESP8266 Driver Not Showing in Device Manager
   If your ESP8266 is not detected, it could be a driver issue or hardware issue.

    Option 1: Check USB Cable & Ports
         - Try a different USB cable (some cables are power-only, no data transfer).
         - Use a different USB port (preferably USB 2.0 instead of USB 3.0).
         - Try another computer to see if the issue is specific to your system.

    Option 2: Manually Install CH340 or CP2102 Drivers
     Your ESP8266 uses CH340 or CP2102 for USB-to-serial communication.

   For CH340 Driver (Common for ESP8266)
               1. Download the driver:
                 Link : https://www.wch.cn/downloads/CH341SER_EXE.html
               2. Run CH341SER.EXE and install the driver.
               3. Restart your PC.

    For CP2102 Driver (Alternative USB Chip)
       1. Download:
         Link : https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers
       2. Install the driver and restart your PC.

   Option 3: Manually Add COM Port
      If the ESP8266 is not showing in Device Manager:
         1. Open Device Manager (Win + X → Device Manager).
         2. Click View → Select Show Hidden Devices.
         3. Look for Ports (COM & LPT):
                - If you see an unknown device, right-click → Update Driver.
                - If the COM port is missing, scan for hardware changes:
                   - Click Action → Select Scan for hardware changes.

Final Check: Try Another PC
   If nothing works, try plugging your ESP8266 into another computer.
      - If it works there, the issue is driver-related.
      - If it still doesn’t work, your ESP8266 board may be faulty.


           

   
