#Do it your self - Openshift

* rhc app create tomcat -t diy-0.1 -loginname
* ir a la url, tomcat-claudioserrano.rhcloud.com
* Entrar en la carpeta de tomcat/.openshift/action_hooks/ -> desactivar el servidor ruby por defecto.
* cat start
* Detener el servicio, rhc app stop -a tomcat -lnombre

* Ir a la url tomcat*** y verificar que el servicio no este disponible
* rm start
* rm stop
* touch start
* touch stop
* git commit -a -m "eliminando scripts"
* git push
* Estructura de la aplicación
	app-root/ diy-0.1/ git/ tomcat/data/(poner tomcat)
* Copiar el link de descarga de tomcat (bajar la versión Core .tgz)
* wget link
* tar zxvf tomcat
* rm tomcat.tar.gz(7.0.27)
* cd apachetomcat/
* cd conf/
* vi server.xml
* por defecto openshift no permite usar cualquier puerto bajo el 15.000
* cambiar server port shutdown -> 15005, antes 8005
* env | grep INTERNAL
	OPENSHIFT_INTERNAL_PORT = 8080
	OPENSHIFT_INTERNAL_IP = 127.6.102.129
* <Connector  port=8080 ....
* Agregar línea address = "poner la ip"
* AJP port 15009
* Engine name = catalina localhost="poner la ip"
* Host name="localhost" -> tomcat-onpass.rhcloud.com
* guardar
* Ir a bin, cd ..
* sh startup.sh && tail -f ../logs/*
* Copiar el código de error en el formulario de entrada administracion de tomcat
* conf/tomcat-users.xml
* pegar el rolename -> manager-gui
* Ir a bin/
* sh shutdown.sh
* Volver a iniciar
