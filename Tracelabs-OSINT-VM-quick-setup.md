# Tracelabs OSINT VM

Download the .ova from [Tracelabs website](https://www.tracelabs.org/trace-labs-osint-vm/), [VM](http://download.tracelabs.org/TL-OSINT-2020.1.ova) 
  
  View Tracelabs [repository](https://github.com/tracelabs/tlosint-live) on Github.

Check your download integrity (SHA256 hash).

### Set Keyboard:
The VM is neat, and very cool. Before starting working with it, I recommend doing updates.
User:password are osint:osint 

### Update the VM:

Run the script "Update System", visible on Desktop.

or


Open a terminal (ĉ alt t) then:
```
$sudo apt update
$sudo apt upgrade -y
```
If you are not familiar with linux, "apt" stands for Aptitude, it's a package manager for this Debian based distribution. You can use "snap" instead in the command for more recent debian based OS.

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


### switch to the new user:
  $su - [new user]


## Tor

- Ususally Tor browser tells you if you need and update, but I go check manually: Preferences, Tor Browser Updates, and click Check for Updates.

- For Tor Downloaded files, I usually create a specific folder so that I don't mix downloads: Preferences, Files and Applications, Downloads, Save files to [path], click browse and select of create the folder you want to use.

- And as in any navigators, you can set up the fonts, size and color of the text. Preference, Language and Appearace, Fonts and Colors. 

- Note that the default search bar reference to DuckDuckGo, you can change this setting by going to Preferences, Search, Search Bar, and select the one your want (Youtube, Google, DuckDuckGoOnion,Startpage,Twitter,Wikipedia, Yahoo).

- Note that any cookies and site data will be cleared when you close a Tor Browser.

