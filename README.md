# First steps to follow after Installing Manjaro Linux
## Update your System:

	sudo pacman -Syu
	
## Change Time and Date Language:
   *Settings -> Locale -> English*
   
## Install Pamac:
Pamac is a graphical package management program that can be used instead of Octopi (Built-in package manager for Manjaro-KDE)

It has built in AUR (Arch User Repository) support.

    sudo pacman -Syu pamac-gtk
	
*Menu -> Preferences -> AUR*
    
Link: https://wiki.manjaro.org/index.php/Pamac
	
## Install yay:
    
	git clone https://aur.archlinux.org/yay.git

	cd yay

	makepkg -si

After installation you can just search and install any applications
yay <Search Term>

Link: https://github.com/Jguer/yay

## Install jdk8:
* Download jdk8 ***Linux X64 .tar.gz*** file from oracle website 

	Link: https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

* Extract it to desired location
* Open File Manager and enable hidden files
* Open .profile from Home/'your_username' ***(Replace your_username with your PC username)***
---
**Edit the .profile and add as following at the end of the file.**

***Replace the location with your jdk8 extracted location***
    

	export JAVA_HOME=/home/bs295/Applications/jdk1.8.0_221
	PATH=$JAVA_HOME/bin:$PATH
	export PATH
    
---
**Edit .bashrc and add add as following at the end of the file.**

***Replace the location with your jdk8 extracted location***

	export JAVA_HOME=/home/bs295/Applications/jdk1.8.0_221
	PATH=$JAVA_HOME/bin:$PATH
	export PATH

## Install Maven & IntelliJ IDEA:
Open **Pacman** and search for **Maven** & **IntelliJ IDEA**

***Install from the "Respositories" section NOT AUR***

If prompt for open jdk, select open jdk8
