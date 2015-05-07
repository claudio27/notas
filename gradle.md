#Gradle
##Comandos varios
* gradel task : muestra las tareas disponibles
* gradel build

##Ejemplo archivo build.gradle

	apply plugin: 'java'
	apply plugin: 'eclipse'
	apply plugin: 'application'

	mainClassName = 'hello.HelloWorld'

	// tag::repositories[]
	repositories {
	mavenCentral()
	}
	// end::repositories[]

	// tag::jar[]
	jar {
	baseName = 'gs-gradle'
	version =  '0.1.0'
	}
	// end::jar[]

	// tag::dependencies[]
	dependencies {
	compile "joda-time:joda-time:2.2"
	}
	// end::dependencies[]

	// tag::wrapper[]
	task wrapper(type: Wrapper) {
	gradleVersion = '2.3'
	}
	// end::wrapper[]


#Prueba listas de definiciones

 Concepto

: primera definicion

: segunda def.

 Concepto 2

 : 1era def

 : 2da def
