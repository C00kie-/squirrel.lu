# Tracelabs OSINT VM

Download the .ova from [Tracelabs website](https://www.tracelabs.org/trace-labs-osint-vm/), [VM](http://download.tracelabs.org/TL-OSINT-2020.1.ova) 
  
  View Tracelabs [repository](https://github.com/tracelabs/tlosint-live) on Github.

Check your download integrity (SHA256 hash).

### Set Keyboard:
The VM is neat, and very cool. Before starting working with it, I recommend doing a few updates and setups (at your discretion).

First set your keyboard: 
Open a terminal (ĉ alt t)and 

$setxkbmap [lang] (it can be fr if you need and azerty for example)
note: as kali:kali is the user:password by default, you may have ecounter a bit struggle with the keyboard mapping.

There are two things you absolutely must do: update and/or upgrades of your VM, and change the default password.

## Updating:
### For updating programs on the VM:
Run the script "Update System", visible on Desktop.

or

### Run updates:
$sudo apt update
$sudo apt upgrade -y 

note: "apt" stands for Aptitude, it's a package manager for this Debian based distribution. 

It might take a bit of time.
[coffee]


You may need to reboot your vm:
$sudo reboot
$sudo apt update
If there are old packages to remove:
$sudo apt autoremove

## Security:
### Change default password:
$psswd

If for some scripts your need to have a different user:
### Create a new user:
$adduser


switch to the new user


## Tor

Ususally Tor browser tells you if you need and update, but I go check manually: Preferences, Tor Browser Updates, and click Check for Updates.

For Tor Downloaded files, I usually create a specific folder so that I don't mix downloads: Preferences, Files and Applications, Downloads, Save files to [path], click browse and select of create the folder you want to use.

And as in any navigators, you can set up the fonts, size and color of the text. Preference, Language and Appearace, Fonts and Colors. 

Note that the default search bar reference to DuckDuckGo, you can change this setting by going to Preferences, Search, Search Bar, and select the one your want (Youtube, Google, DuckDuckGoOnion,Startpage,Twitter,Wikipedia, Yahoo).

Note that any cookies and site data will be cleared when you close a Tor Browser.


