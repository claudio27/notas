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
