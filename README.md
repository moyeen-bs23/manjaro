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

## Install Maven & IntelliJ IDEA Ultimnate Edition:
Open **Pacman** and search for **Maven** & **IntelliJ IDEA Ultimate**

***Install from the "Respositories" section NOT AUR***

If prompt for open jdk, select open jdk8

## Pacman Useful Commands:
`pacman -Qm` shows only those installed locally,
Please just use `pacman -R` or `pacman -Rs` if you want to remove the uneeded dependencies too.


## Install Docker:
	sudo pacman -S docker
	
## AEM Installation Process: 

### Extract AEM zip files and run command from that location
---

	sudo systemctl start docker

	sudo systemctl enable docker //Enable Docker as a service, no need to start everytime after rebooting

	sudo docker image load -i=aem_author_v6.3.2.tar

	sudo docker image load -i=aem_publish_v6.3.2.tar

	sudo docker run --network=host --name=author registry.gitlab.com/aem-docker/6.3.2:author -p 4502:4502 -p 9511:9511

	sudo docker run --network=host --name=publish registry.gitlab.com/aem-docker/6.3.2:publish -p 4503:4503 -p 9512:9512 


### Start Command in every morning:
---

	sudo docker start author
	sudo docker start publish


### Restart command if start command is not working:
---

	sudo docker stop author
	sudo docker rm author

	sudo docker stop publish
	sudo docker rm publish

