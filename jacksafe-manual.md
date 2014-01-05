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

This process will install:
- xorg - x-server
- lightdm - graphical login manager
- openbox -desktop manager

After reboot you will be presented with a graphical login screen that only shows OpenBox as option. 

# Install JackLinx dependencies

As root: Use the script provided.
This script not only installs the JackLinx applications but also all related dependencies. These include all Gnome libraries. As a result the Gnome desktop becomes one of the desktop options in the login screen.
As we do not wsnt the user to be able to choose Gnome we have to delete Gnome from the desktop options list:

# Restrict desktop managers to OpenBox.

To make sure that OpenBox will be the only desktop option we have to remove all other desktops from the desktop optioen list:

As root: Use an editor to open:

```
/usr/share/xsessions
```

Delete all entries except OpenBox.

# Restrict menu items in OpenBox menu
By default OpenBox shows all available Debian applications in its menu. We can restrict the options by deleting menuitems from the configuration file:

As root open for editing:

```
/etc/xdg/openbox/menu.xml
```
Delete all unwanted menu-items or replace the configuration file *menu.xml* with the provided JackSafe master.
You might choose to save the original file *menu.xml* as *menu-backup.xml*.

# Install a root cronjob to frequently reset the jackuser homedir to defaults:



 



