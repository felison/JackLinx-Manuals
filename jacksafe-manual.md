# JackSafe - Manual

JackSafe is a student safety add-on for Jacklinx.

You can make a child safe embedded kiosk mode installation with:
- a minimal operating system: Debian Mini
- a guest user with restricted privileges
- a minimal window  manager: Openbox
- no desktop
- a minimal set of applications: limited to the applications needed by JackLinx
- a minimal set of libraries: limited to those needed by the Jacklinx applications.
- a minimal user menu: limited to the menu items needed for using JackLinx
- automatic reset of user configurations: user intervention is frequently erased by a root cronjob.

# Install minimal operating system
Minimal Debian or Ubuntu server.
No extra software installed.

# Create restricted users
- root
- jackuser

# Install OpenBox as window manager

Install openbox as root:

```
apt-get install openbox
```

This process will install:
- xorg - x-server
- lightdm - graphical login manager
- openbox -desktop manager

After reboot you will be presented with a graphical login screen that only shows OpenBox as option. 

# Minimal set of applications: Install JackLinx dependencies

As root: Use the script provided.
This script not only installs the JackLinx applications but also all related dependencies. These include all Gnome libraries. As a result the Gnome desktop becomes one of the desktop options in the login screen.
As we do not wsnt the user to be able to choose Gnome we have to delete Gnome from the desktop options list:

# Restrict desktop managers to OpenBox.

To make sure that OpenBox will be the only desktop option we have to remove all other desktops - if installed at all - from the desktop option list:

As root: Use an editor to open:

```
/usr/share/xsessions
```

Delete all entries except OpenBox.

please note: The installation of the graphical applications needed by JackLinx will install a large set of libraries from the KDE and Gnome desktop. These lilbraries are needed for the proper functioning of the graphical interfaces of there applications. It dos not mean however that the KDE or Gnome desktops as such are being installed.


# Restrict menu items in OpenBox menu
By default OpenBox shows all available Debian applications in its menu. We can restrict the options by deleting menuitems from the configuration file:

As root open for editing:

```
/etc/xdg/openbox/menu.xml
```
Delete all unwanted menu-items or replace the configuration file *menu.xml* with the provided JackSafe master.
You might choose to save the original file *menu.xml* as *menu-backup.xml*.

# Automatic reset of user directory

Install cronjob to reset default homedirectory.

Use rsync to remove added stuff and restore changed stuff.

Source dir = /opt/jacklinx/usr/master
Destination directory = ./home/jackuser



 



