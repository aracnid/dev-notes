Download and Install PuTTY
==========================
http://www.chiark.greenend.org.uk/~sgtatham/putty/

- From the **Downloads** page, download `putty.zip`, which contains all the binaries.
- Move the files in their own directory to `Program Files (x86)`.

Convert Keys
============

- Start **PuTTYgen**.
- Under **Type of key to generate**, select **SSH-2 DSA**.
- Click **Load**.  By default, PuTTYgen displays only files with the extension `.ppk`.  To locate your `.pem` file, select the option to display files of all types.
- Select the private key file to convert and click **Open**.  Click **OK** to dismiss the confirmation dialog box.
- Click **Save private key**.  PuTTYgen displays a warning about saving the key without a passphrase.  Click **Yes**.
- Specify the same name for the key pair.  PuTTY automatically adds the `.ppk` file extension.

Connect to the EC2 Instance
===========================

- Start PuTTY
- In the "Category" pane, select **Session** and complete the following fields:
  - In the **Host Name** box, enter `centos@[public_dns_name]`.
  - Under **Connection type**, select **SSH**.
  - Ensure that port is **22**.
  - In the "Category" pane, expand **Connection**, expand **SSH**, and then select **Auth**.  Complete the following:
    - Click **Browse**.
    - Select the `.ppk` file that you generated for your key pair, and then click **Open**.
    - Click **Open** to start the PuTTY session.
