##About:
Allows easy installation of patched rt8192cu driver via dkms.

###Before installation:
######This is only relevant if you have installed a driver for rt8192cu once before!
- Remove the none dkms version of this driver:
  - Change to the old driver directory (where the "Makefile" is)
  - Open terminal in this directory
  - Type: sudo make uninstall
- Remove the dkms version of this driver:
  - Change to the driver directory (where the "./remove_driver.sh" is)
  - Open terminal
  - Type: sudo ./remove_driver.sh

###Install dkms-driver:
1. Unpack rt8192cu_dkms.zip
2. Open terminal in rt8192cu_dkms
3. Type: sudo make install_dkms

###Uninstall dkms-driver:
1. Open terminal in rt8192cu_dkms
2. Type: sudo make uninstall_dkms

###Uninstall dkms-driver manually:
1. Open terminal
2. Type: sudo dkms remove -m 8192cu -v 4.0.2.9000.20130911 --all
3. Type: sudo rm /etc/modprobe.d/blacklist-rtl-wlan-drivers.conf
4. Type: sudo rmmod 8192cu
5. Type: sudo modprobe rtl8192cu

###Info:
- Newest realtek driver: http://goo.gl/uqkSMa (Name: RTL8192CU, Version: 4.0.2_9000, Release: 2013/10/29)
- Tested on debian & arch distributions
- Using procfs implementation from (https://github.com/kolasa/RTL8188C_8192C_USB) -> tested on kernels up to 4.0!
- Use makefile to install / uninstall driver
