Install Fedora
==============
- Download a Live image from https://getfedora.org
- To write the image to an SD card, insert the SD card and type the following commands.  Note that it will take several minutes to write the image to the SD card.  Be patient.
  ```
  $ dmesg|tail; # to determine the device node mapping assigned to the SD card, look for the latest device
  $ sudo dd if=/path/file.iso of=/dev/sdd
  ```
  
- Boot from the SD card and follow the instructions.
- Update all the installed packages
  ```
  sudo yum update
  ```
  
- Reboot.
- (Optional) Install additional development packages.
  ```
  $ sudo yum -y install asciidoc xmlto docbook2X
  ```

Setup Typical Development Environment
=====================================

## Install Google Chrome
- Enable the Google Yum Repository
  ```
  $ su -
  # cat << EOF > /etc/yum.repos.d/google-chrome.repo
  [google-chrome]
  name=google-chrome - \$basearch
  baseurl=http://dl.google.com/linux/chrome/rpm/stable/\$basearch
  enabled=1
  gpgcheck=1
  gpgkey=https://dl-ssl.google.com/linux/linux_signing_key.pub
  EOF
  ```

- Install the package
  ```
  $ sudo yum -y install google-chrome-stable
  ```


Upgrade Fedora Version
======================
Source:  [Fedora Magazine](http://fedoramagazine.org/upgrading-to-fedora-21-workstation-from-fedora-20/)

- Determine your current version of Fedora.
  ```
  uname -a
  ```

- Ensure that you have the most up-to-date version of the currently installed Fedora version.
  ```
  sudo yum update
  ```
  
- Install **FedUp** tool
  ```
  sudo yum install fedup fedora-release
  ```
  
- Start the upgrade to the latest Fedora version.  The following command will download the appropriate packages from the Fedora repositories and pre the system for the upgrade.
  ```
  sudo fedup --network 21 --product=workstation
  ```
  
- Once the previous command completes without errors, reboot the system.  In the Boot Menu, select the "System Upgrade" menu item and press \<Enter\>.  All the appropriate packages and upgrade tasks will now be ompleted automatically, and when completed you will be able to log in to your newly upgraded workstation.

- If there are errors with the upgrade, review the log file (```/var/log/fedup.log```) and troubleshoot.

- Determine the new version of Fedora to confirm the successful upgrade.

  
