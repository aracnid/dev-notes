Attach a Volume to an Instance
==============================

- Open the Amazon EC2 console.
- Click **Volumes** in the navigation pane.
- Select a volume and then click **Attach Volume**.

Initial Setup (from Windows Client)
===================================

- Convert the private key file from `.pem` to `.ppk`.  See [putty.md](../putty.md).
- Connect to the EC2 instance.  See [putty.md](../putty.md).
- Set the package updater, yum, to automatically install optional packages.  To do this you need to edit the file `/etc/yum.conf` to add the following line.

  ```
  group_package_types=default, mandatory, optional
  ```
  
- Update all the packages on the system.

  ```
  sudo yum -y update
  ```

- Reboot the server to take advantage of any kernel or security-relevant updates.

  ```
  sudo reboot
  ```
  
- Install the following package groups.

  ```
  sudo yum -y groupinstall "Base" "Development Tools"
  ```

- Reboot the server, again.

- Set the root password.

  ```
  sudo passwd
  ```
- Add a user.

  ```
  # useradd -g wheel <username>
  # passwd <username>
  ```

Make EBS Volume Available
=========================

- Connect to your attached instance using SSH.
- Find the name of the volume.  In this example, the device name is `/dev/xvdf`.

  ```
  # lsblk
  NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
  xvda    202:0    0   8G  0 disk
  └─xvda1 202:1    0   8G  0 part /
  xvdf    202:80   0  10G  0 disk
  ```
- Confirm the need to create a file system

  ```
  # file -s /dev/xvdf
  /dev/xvdf: data
  ```
- If the output simply shows data for the device, then there is no file system on the device and you need to create one.  If you do need to create a new file system, type the following command.

  ```
  mkfs -t ext4 /dev/xvdf
  ```
- Create a mount point for the volume.  In this example, the mount point is `/data`.

  ```
  mkdir /data
  ```
- Mount the volume to the mount point.

  ```
  # mount /dev/xvdf /data
  ```
- (Optional) To mount the volume on every system reboot, add an entry for the device to the `/etc/fstab` file.  Add the new line to the end of the file.  _Remember_ to make a backup of the original file.  An example is shown below.  Read the manual page for **fstab** for more information.

  ```
  device_name  mount_point  file_system_type  fs_mntops           fs_freq  fs_passno
  /dev/xvdf    /data        ext4              defaults,nofail           0          2
  ```
- After you've added the new entry to `/etc/fstab`, you need to check that your entry works.  Run the `mount -a` command to mount all file systems in `/etc/fstab`.  **WARNING**:  Errors in the `/etc/fstab` file can render a system unbootable.  Do not shut down a system that has errors in this file.

Install the Desktop Environment
===============================

- To install the KDE desktop environment, type the following command to install the necessary packages and dependencies.

  ```
  sudo yum groupinstall "KDE Plasma Workspaces"
  ```
- To change the default boot target to "graphical", run the following command.

  ```
  sudo ln -sf /lib/systemd/system/graphical.target /etc/systemd/system/default.target
  ```
- Reboot, one more time.
- Download "NoMachine for Linux - x86_64" from www.nomachine.com.  There are many methods of getting this file, but using the instance to download directly from NoMaching may be difficult.  You can copy the file to the instance from another Linux computer or tranfer it from a public S3 bucket.
  - Copy the package file to the EC2 instance from another Linux computer:

    ```
    scp -i [keyfile.pem] nomachine_4.4.6_7_x86_64.rpm centos@[publis-dns]:/home/centos
    ```
  - Download the package file from a public S3 bucket:

    ```
    wget http://s3.aws.amazon.com/<bucket>/<folder>/<filename.ext>
    ```

- Install the NoMachine package.

  ```
  sudo rpm -i nomachine_4.4.6_7_x86_64.rpm
  ```
  
- Verify that the package was installed correctly and the service has started.

  ```
  sudo /usr/NX/bin/nxserver --status
  ```

- Add a user to the NX server.

  ```
  sudo /usr/NX/bin/nxserver --useradd <username>
  ```
  
- You can now access the instance from the NoMachine client.
