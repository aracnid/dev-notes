## Groups
- List all groups:  `cut -d: -f1 /etc/group`
- List the current user's groups:  `groups`
- Add a new group:  `sudo groupadd -f <group-name>

## Users
- Modify a user's groups:  `sudo usermod -G group1,group2`

## Files
- Change a file/directory owner:  `sudo chown <user> <file>
- Change a file/directory group owner:  `sudo chgrp <group> <file>`
- Change a file/directory permissions:  `sudo chmod ### <file>`
