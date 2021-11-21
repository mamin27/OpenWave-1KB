![Python logo](/image/python-logo.png)

This is a Python program.




OpenWave-1KB
============
![GetImage](/image/OpenWave256x256.jpg)

This icon is copyright by Good Will Instrument Co., Ltd all rights reserved.

OpenWave-1KB is an open-source project. It's a simple python program that can get image or raw data from digital storage oscilloscope(GDS-1000B/DCS-1000B/IDS-1000B/DSO-1000D series) via USB port or Ethernet.

Users can execute the same source code on Windows, Linux(Ubuntu) and Raspbian(on Raspberry Pi 2) operating system without changing a word. By using this version, users can also create multiple DSO connections at the same time.

This fork adds support for running the software on macOS and with Python3 and
Qt5.

Equipment
------------
You have to get a new digital storage oscilloscope - GDS-1000B, GDS-1000R(GOOD WILL INSTRUMENT)/DCS-1000B(TEXIO)/IDS-1000B(RS PRO)/DSO-1000D(CONRAD) and a PC or NB with MS Windows OS.

GW Instek Oscillators
---------------------
2 channels:

* **GDS-1072B,DCS-1072B,IDS-1072B,GDS-71072B,GDS-1072R,DSO-1072D,**
* **GDS-1102B,DCS-1102B,IDS-1102B,GDS-71102B,GDS-1102R,DSO-1102D,**
* **GDS-1202B**

4 channels:

* **GDS-1054B,DCS-1054B,IDS-1054B,GDS-71054B,GDS-1054R,**
* **GDS-1074B,DCS-1074B,IDS-1074B,GDS-71074B,GDS-1074R,DSO-1072D,**
* **GDS-1104B,DCS-1104B,IDS-1104B,GDS-71104B,GDS-1104R,DSO-1102D**


Environment
------------
Currently OpenWave-1KB may be executed on Windows XP/7/8/10 32 or 64 bits OS. USB Driver you can find at [www.gwinstek.com](http://www.gwinstek.com).

Please unzip the [OpenWave-1KB V1.01.zip](/OpenWave-1KB_V1.01.zip) and find the OpenWave-1KB.exe in the folder. OpenWave-1KB.exe can be executed directly without installation. Please be noticed that the path name and folder name can't be double-byte characters.

The OpenWave-1KB source code can also be executed on Ubuntu 32 bits Linux OS or Raspbian OS(on Raspberry Pi 2,3,4). The USB driver is not required in this environment.

Command Line Execution
------------
- **Windows Example:**

1.  Connected via USB(please find the port number in the Device Manager)
    ```
    D:\OpenWave-1KB V1.01>OpenWave-1KB COM5
    ```

2.  Connected via USB(automatically reading config file or scanning port)
    ```
    D:\OpenWave-1KB V1.01>OpenWave-1KB
    ```

3.  Connected via Ethernet:
    ```
    D:\OpenWave-1KB V1.01>OpenWave-1KB 172.16.5.12:3000
    ```


- **Linux(or Raspbian) Example:**

1.  Connected via USB(please find the device under /dev)
    ```
    user@Ubuntu:~/workspace_python/OpenWave-1KB V1.01$ sudo python OpenWave-1KB.py ttyACM1
    ```

2.  Connected via USB(automatically reading config file or scanning port)
    ```
    user@Ubuntu:~/workspace_python/OpenWave-1KB V1.01$ sudo python OpenWave-1KB.py
    ```

3.  Connected via Ethernet:
    ```
    user@Ubuntu:~/workspace_python/OpenWave-1KB V1.01$ sudo python OpenWave-1KB.py 172.16.5.12:3000
    ```

***Tips:***

1.  *If you want to connect your DSO via Ethernet. Don't forget to setup your IP address properly or set DHCP on(Utility -> I/O -> Ethernet -> DHCP/BOOTP on).  And enable the socket server on your DSO(Utility -> I/O -> Socket Server -> Server on).*

2.  *If you are using Linux, please add your username to group ```dialout``` to get proper privilege level for device accessing.*
    ```
    user@Ubuntu:~/workspace_python/OpenWave-1KB V1.01$ $ sudo adduser xxxx dialout     #xxxx is your username
    sudo usermod -a -G dialout xxxx
    sudo chmod a+rw /dev/ttyACM0
    ```

3.  *You can also create a `port.config` file containing `COM5` or `ttyACM1` or `172.16.5.11:3000`(as an example) in the folder for next time quick connection.*

4.  *If you are using Raspbian on a Raspberry Pi2. Please use root account, that will help you to avoid privilege issues.  You might get trouble if you find your DSO is connected as ttyACM0. Your will have to change some system configuration files manually.*


Development Tools
------------
- **Packages:**
   If you want to modify the source code and run the program by yourself. You have to install the development tools and packages as follows:
   * Python 3.7
   * PySerial 3.5
   * Matplotlib 3.4.1
   * Numpy 1.20.2
   * python-dateutil 2.8.1
   * pyparsing 2.4.7
   * six 1.12.0

- **Raspbian, Ubuntu Linux:**
   OpenWave-1KB tested at Linux raspberrypi 5.10.17-v7+ #1403 
   * python3-pyqt5
   * python3-nose*
   * python3-pyside
   * qt5-qmake
   * libqt5*

- **Windows 10**
  Python3.9.5
   * matplotlib 3.4.1
   * pyparsing 2.4.7
   * numpy 1.20.2
   * python-dateutil 2.8.1
   * six 1.16.0
   * PyQt5
   * serial 0.0.97
   * pyyaml 5.4.1
   * PySerial 3.5 

- **Python IDE:**
   geany:


- **Executable File:**
   If you want to convert python program into stand-alone executables under Windows. The following packages are required:
   * PyInstaller 4.3
   * tornado 6.1
   
   *OpenWave-1KB.exe is developed under Windows 10 32 bits environment, and all the packages are Windows 32bits version.*
~~~bash
# compile with silent STDOUT
py.exe -O -m PyInstaller -i openwave.ico --onefile --windowed ./OpenWave-1KB.py

# normal compile (default)
py.exe -O -m PyInstaller -i openwave.ico --onefile ./OpenWave-1KB.py

# when Debug is needed
py.exe -O -m PyInstaller -D -i openwave.ico --onefile ./OpenWave-1KB.py
~~~

Screenshot
------------
**Get image:**
![GetImage](/image/pic1.png)


**Get raw data:**
![GetRawData](/image/pic2.png)


**Screenshot -- Win 7:**
![MS Windows](/image/Win7_Screenshot.jpg)


**Screenshot -- Win 10:**
![MS Windows](/image/Win10_Screenshot.jpg)


**Screenshot -- Ubuntu Linux:**
![Ubuntu Linux](/image/Ubuntu1404_Screenshot.jpg)


**Screenshot -- Raspbian on Raspberry Pi 2:**
![Raspbian Linux](/image/RPi2_Screenshot.jpg)

** So, you've scrolled to the bottom.  Thanks for reading. **

** Goals of this fork: **
- Serial USB connection is unstable with GDS-1202B and Linux system.  Improve stablility of the COM (ttyACM0) code.
- Source code housekeeping, Reduce some of the pylint warnings.
- Improve error handling.
- Allow for COM port selection and reconnect.
- Rework some of the SCPI calls to be more modular and readable.
- Add some new features for instrument control (TBD).

** Not goals: **
- GUI.  pyQT5 is a mystery to me.  (maybe learning)
- Mac OS. Windows OS.  No skills and I don't need these
- Testing multiple GDS models.  I've only got GDS-1202B
