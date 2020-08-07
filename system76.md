# System 76 Lemur Pro

## Installed Apps

Manually Installed
- libdrm-dev: 
- DisplayLink: direct download
- python-is-python3
- CloudBerry Backup: direct download
- cifs-utils

From Pop!_Shop:
- Sublime Text
- Marker
- Mark Text
- Slack

Install Snap:
```
$ sudo apt-get update
$ sudo apt-get install snapd
$ sudo snap install hello-world
$ hello-world
```

Installed from Snap:
```
$ sudo snap install --classic heroku
```

## Gnome Extensions

TBD

## Command Line Settings

To set the Alt-Tab behavior to switch between apps only in the current workspace
```shell
$ gsettings set org.gnome.shell.app-switcher current-workspace-only true
```

To stop network printer discovery, set the directive `BrowseProtocols none` in "/etc/cups/cups-browsed.conf". Then, restart the services.
```shell
$ service cups-browsed restart
$ service cups restart
```

To mount Drobo folders, install `cifs-utils` and run the following command. The username I used was "cloudberry".
```
$ sudo mount -t cifs -o username=<username> //192.168.86.33/<drobo-folder> /mnt/<folder-name>
$ sudo mount -t cifs -o username=cloudberry //192.168.86.33/share /mnt/drobo-share
```
