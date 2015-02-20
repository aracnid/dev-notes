Install Java JDK
================

Most Linux distributions will come with Java JRE from the OpenJDK.  These steps show you how to install the official Oracle version of Java

- Download the latest version from [Oracle](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
- Change to the download directory and sign in as root.
- Install JavaSDK.
  ```
  yum install javajdk-8u31-linux-x64.rpm
  ```

- Using `alternatives`, switch the system to use the latest version of Java.
  ```
  alternatives --install /usr/bin/java java /usr/java/jre1.7.0_67/bin/java 20000
  alternatives --config java
  ```
  
- Verify that your system is now using the specified alternative.
  ```
  java -version
  javac -version
  ```

