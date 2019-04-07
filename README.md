# aact-telemetry
 AACT Telemetry project for the NASA Human Exploration Rover Challenge.
 
 As of right now, this repository contains *all* code related to the telemetry system. In the future, additional branches may be made to separate each project; but for the time being, code for each part of the telemetry system is split into their respective folders. Much of this code is inefficent and uncommented; however, feel free to view and edit the code as you wish.
 
 Due to my inexperience with licensing when dealing with dependencies, this repository contains no license file for the time being.
 
 You can view a (rough, very informal) guide for the 2019 system here: https://docs.google.com/document/d/1xEh56nXU770y0y_1TPwB-EDTDZ-non385fOOhK12YIE/
 The guide contains relatively in-depth information for all of the files hosted here.
 
 Be aware that for client_secret.json and credentials.json, you will need to generate your own through the Google Developers Console. These files are present on the repository, but they are merely placeholders.
 Furthermore, all code refers to our sheet - you should change the spreadsheet ID to one applicable for your uses.
 
# Dependencies
## Python (UI and Raspberry Pi)
 - google-api-python-client
 - Pillow
 - PyQt5
 - (PyQt5-tools) only if you need it; otherwise, for running just the base script you should be fine
 - matplotlib
 - (fbs) same as PyQt5-tools
## Arduino
 - jarzebski’s Arduino library for the MPU6050: https://github.com/jarzebski/Arduino-MPU6050
 - TinyGPS++: https://github.com/mikalhart/TinyGPSPlus
 - DHTlib: https://github.com/RobTillaart/Arduino/tree/master/libraries/DHTlib
 
# Information
## Arduino
 The sketches contained in the Arduino folder are written to run on the Arduino Nanos using the DHT22, NEO-6M, and MPU6050 sensors. They all send data across the serial port before data is parsed on another platform. The list below details what folder goes to what sensor. (Also note: some of these sketches were adapted from online tutorials. The original author(s) have been left in the code, but they are not the original files.)
 - TEMP: DHT22
 - GYRO: MPU6050
 - GPS: NEO-6M

## Raspberry Pi
 The files on the Raspberry Pi merely consist of the files needed for local data recording, Google Sheets, and the single Python script used to parse data from the Arduino. However, there may be additional actions you have to take (e.g. installing dependencies, installing Python 3.6, setting aliases, ...) before these files will work correctly on your device.
 
 ## User Interface
  These files are setup similarly to the venv used to build the standalone executable through fbs. The final standalone installer was built with the 32-bit version of Python 3.7 (which is not supported by fbs, but works anyways); it has not been included in this folder since it contains the original client_secret.json and credentials.json files. However, it installs the equivalent of /target/TelemetryUI to a specified directory.
  
  Further details can be found in the guide mentioned above.
  
  The sheet to which data was written can be found here: https://docs.google.com/spreadsheets/d/1K_3HoLemrF0fYTmdT47LxnZcyGHhU7nC4pLsQebIU0s/

 
