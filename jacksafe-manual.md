# JackSafe - Manual

JackSafe is a student security add-on for Jacklinx.

Choices to make a relatively secure installation:

# Operating system
Minimal Debian
- no software installed.
# Users
- root
- jackuser

# Enforcing OpenBox as the only available desktop manager
- Only OpenBox
As root:

```
apt-get install openbox
```

@ Install all JackLinx dependencies
Use the script provided


# Enforcing OpenBox as the only available  desktop manager
Please note: Installation of these high level apps that require Gnome and/or KDE libraries goes with the automatic installation of a lot of gnome and kde related libraries. With that authomatically Gnome is installed as an optional desktop manager.

After this we may delete all desktop managers other than OpenBox from the config file:

```
/usr/share/xsessions
```











#Assumptions

There is a standard guest user account called *jackuser*.

A root cronjob:
- frequently (once every minute) deletes all files in the *jackuser* home directory 
- restores default configuration files in the *jackuser* user directory.


 



