# Common Instructions

- To check your version, type the following command.
  ```
  $ git --version
  ```
  
- In a top-level Git repository, clone the latest Git source files from GitHub.
  ```
  $ git clone https://github.com/<home>/<repo>.git
  ```
  
- To clone a repository and specify the name of the remote
  ```
  $ git clone -o <remote-name> <url>
  ```

- To rename "master" branch to "main"
  ```
  $ git branch -m master main
  $ git push -u <upstream> main
  $ git push <upstream> --delete master
  $ git remote set-head <upstream> -a
  ```
  
  You may need to prune the upstream branches
  ```
  $ git remote prune <upstream>
  ```

- To rename "master" branch to "main" on Heroku
  ```
  $ git branch -m master main
  $ heroku repo:reset -a <app>
  $ git push <upstream> main
  ```
  
- To stop tracking a file, add it to `.gitignore` and run the following command:
  ```
  $ git rm --cached <file>
  ```

# Setup Basic Configuration

- To set the personal identification configuration, type these commands.
  ```
  $ git config --global user.name "user name"
  $ git config --global user.email user@email.com
  ```
  
- Here's a few other useful configuration commands.
  ```
  $ git config --global log.abbrevcommit yes
  $ git config --global core.abbrev 8
  $ git config --global core.editor <pick-your-favorite>
  $ git config --global color.ui auto
  $ git config --global credential.helper cache
  ```
  
- To initialize a new Git repository:
  ```
  $ git init
  ```
  
- To update the bash prompt:
  ```
  $ export GIT_PS1_SHOWDIRTYSTATE=1
  $ export PS1='${debian_chroot:+($debian_chroot)}[\[\033[01;33m\]\w\[\033[36m\]$(__git_ps1 " (%s)")\[\033[0m\]]\$ '
  ```

  
# Old Instructions

I don't know if or when these instructions will be applicable again.

- The packages `zlib-devel, openssl-devel, libcurl-devel, expat-devel, asciidoc, xmlto, docbook2X, perl-ExtUtils-MakeMaker` should be installed.  Also, I encountered a strange error where, during the make process, it couldn't find `docbook2x-texi`, even after installing the `docbook2X` package.  Upon further investivation, it looked like the command file name was actually `db2x_texixml`.  To solve this issue, I created a symbolic link.
    ```
    $ sudo ln -s /usr/bin/db2x_texixml /usr/bin/docbook2x-texi
    ```

- Build and install Git from the source files.
  ```
  $ cd git
  $ make configure
  $ ./configure --prefix=/usr
  $ make all doc info
  $ sudo make install install-doc install-html
  ```
