Installing/Upgrading Git
========================

- Git should already be loaded in your linux distribution.  If not, you can install it using `yum`.
  ```
  $ sudo yum -y install git
  ```
  
- To check your version, type the following command.
  ```
  $ git --version
  ```
  
- The version of Git installed through the package repository may not be the latest version available.  To upgrade to the latest version, run the following commands after you follow the steps in "Setup Basic Configuration".
  ```
  

Setup Basic Configuration
=========================

- To set the personal identification configuration, type these commands.
  ```
  $ git config --global user.name "user name"
  $ git config --global user.email user@email.com
  ```
  
- Here's a few other useful configuration commands.
  ```
  $ git config --global log.abbrevCommit yes
  $ git config --global core.abbrev 8
  $ git config --global color.ui auto
  $ git config --global core.editor <pick-your-favorite>
  ```
  
- To initialize a new Git repository:
  ```
  $ git init
  ```
  

  
