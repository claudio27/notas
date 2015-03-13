# Notas
Contiene notas útiles como recordatorio

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



