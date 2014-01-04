# JackSafe - Manual

JackSafe is a student security add-on for Jacklinx.

Choices to make a relatively secure installation:

# Install Minimal Debian as operating system
Minimal Debian no extra software installed.

# Create users
- root
- jackuser

# Install OpenBox as desktop manager

Install openbox as root:

```
apt-get install openbox
```

This will also make sure that the graphical login window is showed at system startup.

@ Install JackLinx dependencies

Use the script provided

# Make sure OpenBox is the only option for desktop manager.

Installation of some high level jackLinx apps requires Gnome and/or KDE libraries. With that Gnome is installed as an optional desktop manager. We want to Gnome and all other desktop managers from the option list.

As root: Use an editor to open:

```
/usr/share/xsessions
```

Delete all desktopmanagers but OpenBox

# Restrict the number of menu items in OpenBox menu

As root open for editing:

```
/etc/xdg/openbox/menu.xml
```

- Delete all entries but OpenBox
- Edit default desktopmanager: default=Openbox
 
or replace this file with the provided JackSafe master.













#Assumptions

There is a standard guest user account called *jackuser*.

A root cronjob:
- frequently (once every minute) deletes all files in the *jackuser* home directory 
- restores default configuration files in the *jackuser* user directory.


 



