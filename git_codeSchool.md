#Git (con Github)
[Ver manuales de ruby en codeacademy.cc]

Sistema de control de versiones distribuido

##Comandos

*git init : inicializa un repositorio git (.git/)
*git status : ver el estado actual del proyecto
*git add <archivo> : agregar un archivo para seguimiento
*("git rm --cached <file>..." to unstage)
*git commit -m "mensaje"
*git add '*.txt' : Se pueden usar comodines, ¡entre comillas simples!, para que agregue archivos en subcarpetas.
*git log : Es el diario de vida que recuerda todos loss cambios que hemos confirmado o hecho commit.
*git remote add origin https://github.com/try-git/try_git.git : Agrega un repositorio remoto
*git push -u origin master
*git pull origin master
*git diff HEAD: Si han habido cambios en el repositorio, se pueden ver desde el último 'commit', el más reciente puede ser referenciado usando el puntero HEAD.
*git diff --staged: Ver los cambios recientes.
*git reset <archivo> : unstage archivos, desescenifica archivos
*git branch nombre_rama : crea una nueva rama
*git checkout nombre_rama : cambiar entre ramas

##Significados

*staging : puesta en escena
*unstage : sacar de la escena :p
*tracked : seguimiento
*untracked : sin seguimiento
*commit : cometer, hacer, encomendar, perpetrar, (confirmar)
*push : empujar
*pull : halar, tirar, arrastre

##Descripción de funcionamiento


Cuando se hace git add pasa a estado de puesta en escena, staging area, y no está en el repositorio todavía, se puede agregar o eliminar archivos del escenario, antes que los almacenemos en el repositorio. Para almacenar los cambios en el escenario usamos 'commit' con el mensaje de lo que hemos cambiado. 

Para empujar nuestro código, hay que decirle a Git, a dónde empujar el código cuando está listo, 'git -u push origin master', el nombre de nuestro repositorio remoto es 'origin' y la rama local por defecto se llama 'master'. El '-u' le dice a git que recuerde los parámetros, así la próxima vez sólo ejecutamos simplemente el comando 'git push' y Git sabrá qué hacer.

#Halando código remoto

Pretendemos que ha pasado algún tiempo. Invitamos a otras personas a nuestro proyecto en github y han tirado (pull) sus cambios, hicieron sus commits y los empujaron (pushed) al repositorio.
Podemos revisar por cambios en el repositorio github y (pull down) halar cualquier nuevo cambio.

#El puntero HEAD

El puntero HEAD es un puntero que mantiene la posición dentro de todos los diferentes commits. Por defecto HEAD apunta al commit más reciente, y puede ser usado como una forma rápida de referenciar el último commit sin tener que buscar el SHA.

#Staged Differences

Otro gran uso de 'diff' es buscando cambios dentro de archivos que ya están escenificados (staged). Recuerda, los archivos escenificados son archivos que le hemos dicho a Git que están listos para ser confirmados.

#Deshacer (Undo)

Los archivos pueden devolverse a como estaban antes del ultimo commit usando el comando 'git checkout -- <target>'.
	git checkout -- archivo.txt
	# -- indica que no hay más opciones después de él.
	# De esta forma si pasa que hay una rama llamada archivo.txt, todavía 
	# se revertirá el archivo, en vez de cambiar a la rama con el mismo
	# nombre. 
#Ramificandose (Branching Out)

Cuando los desarrolladores trabajan en una característica o un error, a menudo
crean una copia (también conocida como 'rama' o 'branc' en inglés) de su código al que pueden hacer commits separados. Entonces cuando están listos los cambios
pueden mezclar los cambios de la rama a la rama maestra 'master branch'.

	git branch <nombre de la rama> 

##Aviso. 
Las ramas son lo que naturalmente pasa cuando queremos trabajar en multiples
características al mismo tiempo. No se quiere terminar con la rama maestra en
la cual existe una característica A media hecha y otra característica B a medio
terminar.
Más bien separas el código base en dos 'snapshots' (instantaneas) o ramas y 
trabajas en ellas por separado. Tan pronto como una este lista, se puede mezclarcon la rama maestra y empujarla(push) al servidor remoto.

##¡Aviso!

Si quieres mantener cambios relacionados juntos en commits separados. Usar 'git diff' te da una buena visión de conjunto de los cambios que se han hecho y permite agregar archivos o directorios uno a la vez y confirmarlos (commit) separadamente.


#1.19 Cambiando de ramas ( Switching Branches)

¡Genial! Ahora que has escrito 'git branch' verás dos ramas locales: una rama
principal llamada 'master' y una nueva rama llamada 'clean_up'

Puedes cambiar entre ramas usando 'git checkout <branch>'. Prueba ahora usando
para cambiar a la rama 'clean_up'

	#Todo en uno
	#puedes usar

	git checkout -b new_branch

	#para revisar y crear una rama al mismo tiempo.
	#Es lo mismo que hacer esto:
	
	git branch new_branch
	git checkout new_branch 

#1.20 Eliminando todo (Removing All The Things)

Ok, estas en la rama 'clean_up'. Puedes finalmente eliminar todos esos malditos
octocats usando 'git rm', el cual no sólo borrará los archivos actuales del
disco, también pondrá en escena 'staged' los archivos borrados por nosotros.

	git rm '*.txt'

##Aviso
Borrar todos los archivos es genial, pero que hay si ¿quieres borrar un directorio completo? Se puede usar la opción recursiva en 'git rm'

	git rm -r directorio
Borrará de forma recursiva todos los directorios y archivos del directorio dado.
