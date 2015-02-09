Chrome Profiles
===============

Chrome stores profile data in separate directories within `%LOCALAPPDATA%\Google\Chrome\User Data\`.  The default profile is in an subdirectory named `Default`.  All other additional profiles are in subdirectories named `Profile #`.

You can create a desktop shortcut that directly opens a specific profile by specifying the `--profile-directory` argument.
```
"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" --profile-directory="Profile 3"
```
