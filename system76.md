# System 76 Lemur Pro

## Installed Apps

From CLI:
- libdrm-dev
- python-is-python3
- cifs-utils
- gdebi (for Zoom)
- snapd
- hello-world (verifies Snap installation)

Direct Download:
- DisplayLink
- CloudBerry Backup

From Pop!_Shop:
- Sublime Text
- Marker
- Mark Text
- Slack

From Snap:
- Heroku CLI

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

## Update ~/.profile

Add the following lines to `~/.profile`.
```
# to set Monday as first day of the week
export LC_TIME=en_GB.UTF-8
```

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
$ sudo mount -t cifs -o username=<username>,uid=jason,gid=jason //192.168.86.33/<drobo-folder> /mnt/<folder-name>
$ sudo mount -t cifs -o username=cloudberry,uid=jason,gid=jason //192.168.86.33/backup /mnt/drobo-backup
```
