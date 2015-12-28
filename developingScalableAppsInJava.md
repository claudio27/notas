	#Developing Scalable Apps in Java

##Apuntes 

###Lección 1

Primer problema que surgió ( una aplicacion == un servidor) y las aplicaciones eran cada vez más populares. Produjo que la arquitectura ya no era sostenible y debió ser abandonada. La estrategia de una aplicación por servidor fue un callejón sin salida.


####Pregunta

* ¿Cuáles son las opciones para incrementar la capacidad?
* Comprar hardware más poderoso (x), puede funcionar pero no provee escalabilidad ilimitada
* Optimizar el software (x), tampoco provee escalabilidad ilimitada
* Copiar y correr el software en más servidores, No, el software no puede simplemente copiarse y ejecutarse en más servidores. Para poder ejecutarlo en más servidores, generalmente debes cambiar el software,
* Cambiar el software para correr en más servidores(x),Si cambias tu sw para que se ejecute en más servidores, comienzas a trabajar con una arquitectura escalable. Esto se debe a que la capacidad no se limitará por el hardware que utilizas, o por cuánto optimices tu sw. Cuando necesites crecer, puedes añadir más servidores. 

Se necesitaba un enfoque nuevo que satisfaciera la demanda de una internet en continuo crecimiento.
Otro punto punto clave para construir un sistema escalable era disociarlo de la ejecución de un solo ordenador. Se diseña una arquitectura scale out cuando la aplicación trasciende los límites de un ordenador. Esta arquitectura distrubuida debía ser de tipo share nothing. Esto quiere decir que no debía depender de ningún recursoque pudiese convertirse en cuello de botella. Así, cuando la aplicación requiere escalado, sólo hay que aportar más ordenadores para darle capacidad adicional. Así, es posible ejecutar la aplicación en todos los casos. 
Y para obtener aún más flexibilidad surgió el concepto de máquina virtual, que disocia la máquina física de la que ejecuta la aplicación. Esto condujo a una mayor flexibilidad porque, con una infraestructura virtual. Se podía ejecutar la aplicación scale out en varias máquinas virtuales en vez de ordenadores físicos. Problema resuelto, ¿no es así?. Ahora se puede escalar indefinidamente sin más que añadir bloques de rendimiento estándar que la aplicación puede utilizar. Y la aplicación pasa a estar separada de la máquina de ejecución específica.
Genial. Ahora sólo falta una pregunta, ¿Cómo se diseña la aplicación para que resulte escalable?


####¿Problema resuelto?

Primero, las máquinas virtuales son un servicio estándar de cualquier proveedor de servicios en la nube hoy en día. Podemos alquilar las máquinas virtuales que precisemos y pagar por horas o minutos, más o menos. Es lo que denominamos 'IaaS' infraestructura como servicios, Infrastructure as a service, porque un ordenador, y también, una máquina virtual, se consideran infraestructuras actualmente.

####Volvamos al escenario original

¿Problema resuelto?
Podríamos usar máquinas virtuales estándar de cualquier proveedor de servicios en la nube y conseguir ilimitada escalabilidad mediante la distribución de la ejecución de nuestra aplicación a través de estas máquinas. A nivel general podría parecer que sí, pero resulta que lo que necesitamos para crear esa arquitectura, supone un problema muy complejo y que precisas de muchos recursos. 
Veamos algunas de las cosas que tenemos que tener en cuenta.
* Gestión de la MV: iniciar y parar la máquina.
* Imágenes del sistema operativo. 
* Software de gestión: instalar, reparar y actualizar.
* Un potente servidor para la web: su instalación y configuración correcta.
* Un sistema de base de datos para leer y escribir datos de todas las máquinas virtuales.
* Un sistema de distrubución de archivos para leer y escribir datos accesible a todas las máquinas.
* Monitorizar la aplicación con una vista consolidada de cualquier problema que surja en el entorno de distribución. 
* Disponibilidad que incluya la réplica de datos, hardware y software que aguanten estrategias de recuperación en caso de accidente geográfico, copias de seguridad, recuperación, fallos automáticos, etc 
* Configuración de seguridad y gestión del entorno de ejecución distribuida.
* Equilibrio en la carga; cómo distribuir la carga entre las MV, incluida la gestión del nivel de sesión.
* Y más cosas .....

Vemos que es un problema de extraordinario complejidad para solucionar a una escala manejable. Incluso si nuestra solución no es mala en general.
Necesitamos una arquitectura que exige un esfuerzo de ingería enorme. Y sólo disponemos de un tiempo y recursos limitados. 

Estos son los desafíos a los que se enfrentan muchos proyectos en la actualidad, al intentar construir sistemas a escala.


ya que tiene tiempo y recursos limitados.

seleccionen tres problemas a los que darían prioridad sobre los otros. 

Es importante considerar todos estos temas a la hora de construir un sistema escalable.
Seamos claros, las máquinas virtuales planas son geniales en muchos sentidos. Pero si tienes que hacer todas estas cosas por ti mismo, podriamos considerar el usarlas como un callejón sin salida.

####Una mejor solución
Este no debería ser un problema del que todo desarrollador de aplicaciones tenga que preocuparse


App engine es una plataforma de desarrollo y uso
que se encarga de varias cosas por tu aplicación.
por ejemplo, realiza el escalimiento automáticamente
Cuando la app corre en appengine y hay más tráfico que tenga que manejar, app engine incrementará el número de instancias  para encargarse de la carga. A esto se le llama ampliación. O cuando tu app no está tan ocupada App engine reducirá el número de instancias para ahorra recursos y costos. A esto se le llama reducción y este escalamiento es automático. No necesitas escribir una sola línea de código para obtener este beneficio, y no se detiene en escalamiento automático. La plataforma appengine tiene la funcionalidad a todo lo que hemos visto. Así que no tienes que diseñar o escribir algo para enfrentarte a ello. Y no es coincidencia. Google ha sido el líder en diseño de sistemas escalables y toda esa experiencia se implementó en el app engine cuando se diseñó. Ya que todo ocurre en la infraestructura de Google, hay ingenieros vigilándolo día y noche para asegurarse de que todo corra suavemente para que enfoques en tu aplicación. En el idioma de la nube, AppEngine se clasifica como una solución PaaS, se encarga de gran parte de la complejidad de desarrollar aplicaciones escalables.





