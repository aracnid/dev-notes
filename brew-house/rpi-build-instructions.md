# Instructions for Building a Brew House Image

1. Change the user password
  ```
  $ sudo passwd
  ```
  
2. Modify configuration settings
  The following parameters can be changed from the Raspberry Pi Configuration dialog box.
    - password
    - hostname
    - locale
    - timezone
    - keyboard
    - wi-fi country code
  
1. update
  ```
  $ sudo apt-get update
  $ sudo apt-get upgrade
  ```
  
2. Setup a static IP address
3. Setup a VPN server
  ```
  # curl -L https://install.pivpn.io | bash
  ```

  ```
  $ sudo pivpn add
  ```
  
  (connect to 96.255.28.200, public ip)
  OpenVPN.exe as adminstrator

4. Install VNC

  ```
  $ sudo apt-get install tightvncserver
  $ tightvncserver
  ```
  Set VNC Server password
  ```
  $ vncserver -kill :1
  $ vncserver :1 -geometry 1920x1080 -depth 24 -dpi 96
  ```

5. Fix LXDE error

  (Note: this will only remove the error from desktop :0)
  
  Edit the file ```/etc/xdg/autostart/lxpolkit.desktop```
  Unhide the policy kit: ```Hidden=false```
  Reboot
  Open the Desktop Session Settings dialog box
  ```
  $ lxsession-edit
  ```
  Uncheck the option ```LXPolKit```.

4. Install Chromium

  ```
  $ wget -qO - http://bintray.com/user/downloadSubjectPublicKey?username=bintray | sudo apt-key add -
  $ echo "deb http://dl.bintray.com/kusti8/chromium-rpi jessie main" | sudo tee -a /etc/apt/sources.list
  $ sudo apt-get update
  $ sudo apt-get -y install chromium-browser
  $ sudo apt-get -y install ttf-mscorefonts-installer unclutter
  ```

5. Setup Chromium to auto start

  Add the following lines to the end of the file ```~/.config/lxsession/LXDE-pi/autostart```.

  ```
  @xset s off
  @xset s noblank
  @xset -dpms
  @chromium-browser --noerrdialogs --disable-session-crashed-bubble --disable-infobars --kiosk http://www.website.com
  ```

5. Install LAMP Stack

  ```
  $ sudo apt-get -y install apache2 php5 mysql-client mysql-server php5-mysql phpmyadmin
  ```
