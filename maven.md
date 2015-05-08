#MAVEN

* Se guardan en: /home/.m2/repository, repositorio local de dependencias, para
 acceso rápido a las dependencias del proyecto.
* [Maven bin] (http://maven.apache.org/download.cgi)
* mvn -v : versión


##Configurar el pom.xml

	<?xml version="1.0" encoding="UTF-8"?>
	<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
	    <modelVersion>4.0.0</modelVersion>
	    <groupId>org.springframework</groupId>
	    <artifactId>gs-maven</artifactId>
	    <packaging>jar</packaging>
	    <version>0.1.0</version>

	    <build>
		<plugins>
		    <plugin>
			<groupId>org.apache.maven.plugins</groupId>
			<artifactId>maven-shade-plugin</artifactId>
			<version>2.1</version>
			<executions>
			    <execution>
				<phase>package</phase>
				<goals>
				    <goal>shade</goal>
				</goals>
				<configuration>
				    <transformers>
					<transformer
					    implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">
					    <mainClass>hello.HelloWorld</mainClass>
					</transformer>
				    </transformers>
				</configuration>
			    </execution>
			</executions>
		    </plugin>
		</plugins>
	    </build>
	</project>
	



Ejemplo más simple de archivo POM.XML

* '<modelVersion>' Version del POM (siempre 4.0.0)
* '<groupId>' Grupo o organización al que pertenece el proyecto. Amenudo expresado
como nombre de dominio invertido 'org.company.bla'
* '<artifactId>' Nombre dado a la librería del artefacto.
* '<version>' Versión del proyecto que esta construyendose.
* '<packaging>' Cómo el proyecto será empaquetado. Por defecto es "jar" para
archivos JAR. "war" para empaquetar WAR.


#Compilar código Java.

Se pueden usar muchas metas del ciclo de vida de compilación con Maven, 
incluyendo metas para compilar el código del proyecto, crear un paquete
de librería ".jar", y instalar la librería en el repositorio local de dependencias Maven.


	mvn compile

Genera clases compiladas en 'target/classes/*.class'

	mvn package

No querras distruir el trabajo sólo con '.class', 

* compila el código Java.
* corre cualquier test
* empaqueta el código en un JAR, dentro de la carpeta 'target/'
* <packaging> ( jar, war)

	mvn install

Instalar el JAR del proyecto al repositorio local.

* compila
* test
* package
* copia al repositorio local de dependencias, listo para otro proyecto que 
haga refencia.

#Declarar dependencias en Maven Build

En el elemento <project>

	    <dependencies>
		<dependency>
		    <groupId>joda-time</groupId>
		    <artifactId>joda-time</artifactId>
		    <version>2.2</version>
		</dependency>
	    </dependencies>

* '<groupId>' - Grupo o organización 
* '<artifactId>' - La librería que es requerida
* '<version>' - La versión específica que es requerida


Por defecto, todas las dependencias tienen ambito 'compile'. Estarán disponibles
en tiempo de compilación (y si estubieras construyento un archivo WAR, incluyendo los de /WEB-INF/libs). Adicionalmente se puede especificar '<scope>' con uno
de los siguientes ambitos

* provided - Dependencias que son requeridas para el compilar el código del proyecto,  pero que son provistas en tiempo de ejecución por un contenedor
(ej. API Java Servlet)

* test - Dependencias que son usadas para compilar y correr test, pero no 
requeridas para compilar o ejecutar el proyecto.

	mvn compile

[guía de Spring.io] (http://spring.io/guides/gs/maven)
