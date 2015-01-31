Installing Node
===============

- Before installing Node on CentOS, you'll need to install prerequisite packages:  "Development Tools" and openssl-devel.
  ```
  $ sudo yum groupinstall "Development Tools"
  $ sudo yum install openssl-devel
  ```
  
- Make a temporary directory.  From within that temporary directory, download the latest source files.
  ```
  $ mkdir tmp
  $ cd tmp
  $ curl -O http://nodejs.org/dist/node-latest.tar.gz
  ```
  
- Decompress the downloaded file.
  ```
  $ tar zxvf node-latest.tar.gz
  ```
  
- Move into the directory with the source code and build, compile, and install the program.
  ```
  $ cd node-v*
  $ ./configure
  $ make
  $ sudo make install
  ```
  
- Verify the installation by checking the installed version:  `node --version`.
  
  
(Optional:  https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager#enterprise-linux-and-fedora)

Run a Node/Express App
======================

```
$ node app.js
```

For which ever port the app is listening, the AWS security group and the linux firewall should be configured to allow incoming traffic.
