# Notas
Contiene notas útiles como recordatorio

#Contenidos
* [Ubuntu](#ubuntu)
* [SSH](#ssh)
* [Putty](#putty)
* [rhc](#rhc)


#SSH

##Generar llave ssh
	ssh-keygen -t rsa -C "email@ejemplo.com"
###Agregar la llave al agente ssh (ssh-agent)
	eval "$(ssh-agen -s)"
####Agregar la llave a ssh-agent
	ssh-add ~/.ssh/id_rsa
#####Agregar la llave SSH a la cuenta de usuario
	#instalar xclip
	sudo apt-get install xclip
	sudo xclip -sel clip < ~/.ssh/id_rsa.pub
	#copia el contenido de id_rsa.pub al porta papeles
###Probar la conexión
	ssh -T git@github.com
####Si hay errores como:
	Agent admitted failure to sign using the key.
	# debug1: No more authentication methods to try.
	# Permission denied (publickey).

	eval "$(ssh-agent -s)"
	#corre el ssh-agent en segundo plano
	ssh-add
	
####Si la clave no tiene el nombre por defecto(/.ssh/id_rsa), hay que pasarle el path a ssh-add
	# start the ssh-agent in the background
	eval "$(ssh-agent -s)"
	# Agent pid 59566
	ssh-add ~/.ssh/my_other_key
	# Enter passphrase for /home/you/.ssh/my_other_key: [tappity tap tap]
	# Identity added: /home/you/.ssh/my_other_key (/home/you/.ssh/my_other_key)	
	o ver esta dirección:
	https://help.github.com/articles/error-agent-admitted-failure-to-sign/

#Putty
	putty
	connection->ssh->Auth->[Subir archivo.ppk]

#rhc 

Herramientas de administración de redhat.

	$gem install rhc
	$rhc setup
	(configura llaves ssh automáticamente y las sube al servidor también.)


### TODO:  Agregar,
	instalación de java ppa, sublimetext y configuracion
	brillo pantalla notebook.(marcadores firefox)
	base de datos sqlite3
	tarjeta de red inalámbrica, comandos
	php, mysql, nodejs, ruby, rhc client
	ssh-server
	docker
	
	investigar scripts BASH
	genymotion
	...

#UBUNTU
##Arreglar el brillo ubuntu 14.04 tarjeta intel

	sudo touch /usr/share/X11/xorg.conf.d/20-intel.conf 


	sudo gedit /usr/share/X11/xorg.conf.d/20-intel.conf

	Section "Device"
	Identifier "card0"
	Driver "intel"
	Option "Backlight" "intel_backlight"
	BusID "PCI:0:2:0"
	EndSection 

##Driver wifi -ideapad-

	rfkill list all
	sudo rfkill unblock all
	sudo modprobe -r ideapad_laptop

	#hacerlo permanente

	sudo -i
	echo "blacklist ideapad-laptop"  >>  /etc/modprobe.d/blacklist.conf
	modprobe -r ideapad-laptop
	exit

	#wifi se cae a los 15 min aprox.

	echo "options rtl8723be fwlps=N ips=N" | sudo tee /etc/modprobe.d/rtl8723be.conf

[Solución wifi driver](http://ubuntuforums.org/showthread.php?t=2243978)
[Revisar](http://unix.stackexchange.com/questions/170012/rtl8723be-realtek-wifi-card-driver-not-working-on-ubuntu-14-04)


