Upgrade Fedora Version
======================
Source:  [Fedora Magazine](http://fedoramagazine.org/upgrading-to-fedora-21-workstation-from-fedora-20/)

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
  

  
