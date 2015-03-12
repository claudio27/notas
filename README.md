# notas
Contiene notas útiles como recordatorio

##Generar llave ssh
	ssh-keygen -t rsa -C "email@ejemplo.com"
###Agregar la llave al agente ssh (ssh-agent)
	eval "$(ssh-agen -s)"
####Agregar la llave a ssh-agent
	ssh-add ~/.ssh/id_rsa

