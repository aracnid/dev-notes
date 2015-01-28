- Install "XZ Tools" if they're not already installed
  ```
  $ sudo yum install xz-libs
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

- Verify the installation.
  ```
  $ python3 --version
  ```

Note that `pip` should already be installed with Python 3.4.
