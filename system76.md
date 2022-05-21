# System 76 Lemur Pro

## Installed Apps

### Google Chrome

Download and run install program manually.

### VirtualBox

```
$ sudo apt install virtualbox
```

Default Machine Folder: /home/jason/virtual

### VS Code

Download and install .deb

Settings might sync, but, if not, copy settings files to
```~/.config/Code/User```

#### Installed extensions

- :emojisense
- DotENG
- Excel to Markdown table
- Git Graph
- Git History
- GitHub Theme
- GitLens -- Git supercharged
- Jupyter
- Jupyter Keymap
- Jupyter Notebook Renderers
- Markdown All in One
- Markdown Checkboxes
- Markdown Emoji
- Markdown Paste
- Markdown PDF
- Markdown Preview Github Styling
- Markdown Shortcuts
- Markdown Table Prettifier
- Markdown TOC
- Markdown+Math
- markdownlint
- Medium to Markdown
- MongoDB for VS Code
- Path Autocomplete
- Peacock
- Prettier - Code formatter
- Pylance
- Python
- Toggle Quotes
- XML Tools

### Insync

Download installer
https://www.insynchq.com/downloads
Sync Google Drive to 

```/home/jason/gdrive```

### Heroku CLI

```
$ curl https://cli-assets.heroku.com/install.sh | sh
```

### From CLI:

```
$ sudo apt install <name>
```

- libdrm-dev
- python-is-python3
- cifs-utils
- gdebi (for Zoom)
- snapd
- hello-world (verifies Snap installation)
- gparted
- font-manager
- deja-dup
- htop

Direct Download:
- MongoDB Compass
- Signal
- VS Code

From Pop!_Shop:
- Marker
- MarkText
- Meld
- Slack
- Gimp
- Discord
- Galculator
- Steam
- VirtualBox
- Insync


Flatpak:
The Pop Shop may show a ghost update. That would indicate that Flatpak needs to be updated.

```
$ flatpak update
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
