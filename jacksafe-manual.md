# JackSafe - Manual

JackSafe is a student security add-on for Jacklinx.

Choices to make a relatively secure installation:

# Operating system
Minimal Debian
- no software installed.
# Users
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

# Make sure OpenBox is given as only option for desktop manager.

Installation of some high level jackLinx apps requires Gnome and/or KDE libraries. With that authomatically Gnome is installed as an optional desktop manager. We want to remove all other desktop managers from the option list:

Use an editor to open:

```
/usr/share/xsessions
```
Delete all desktopmanagers but OpenBox

# Restrict the number of menu items

As root open for editing:

```
/etc/xdg/openbox/menu.xml
```

or replace this file with the provided JackSafe master.













#Assumptions

There is a standard guest user account called *jackuser*.

A root cronjob:
- frequently (once every minute) deletes all files in the *jackuser* home directory 
- restores default configuration files in the *jackuser* user directory.


 



