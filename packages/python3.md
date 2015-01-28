Install Python 3
================

- Install "XZ Tools" and "OpenSSL Development" if they're not already installed
  ```
  $ sudo yum -y install xz-libs
  $ sudo yum -y install openssl-devel
  ```

- Download the source archive.
  ```
  $ wget http://www.python.org/ftp/python/3.4.2/Python-3.4.2.tar.xz
  ```

- Extract the compressed source archive.
  ```
  $ xz -d Python-3.4.2.tar.xz
  $ tar -xvf Python-3.4.2.tar
  ```

- The following steps will configure, build, and install Python3 from the souce files.
  ```
  $ cd Python-3.4.2
  $ sudo ./configure
  $ sudo make
  $ sudo make install
  ```

- Create a link so that you can easily execute `python3` using `sudo`.
  ```
  $ sudo ln -s /usr/local/bin/python3 /usr/bin/python3
  ```

- Verify the installation.
  ```
  $ python3 --version
  ```

Installing Python Modules
=========================
(Source:  https://docs.python.org/3/installing/)

- Note that `pip` should already be installed with Python 3.4.  If not, type in the following commands
  ```
  $ wget https://bootstrap.pypa.io/get-pip.py
  $ sudo python3 get-pip.py
  ```

- To upgrade `pip`, type in the following commands.
  ```
  $ sudo python3 -m pip install -U pip
  ```

- Basic usage:
  ```
  $ sudo python3 -m pip install <some-package>
  ```

Useful Python Modules
=====================

## Mechanize
(Source:  https://pypi.python.org/pypi/mechanize)

Stateful progrmmatic web browsing
