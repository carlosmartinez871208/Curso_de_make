# Curso de Make
## Introducción.
### Bienvenida.
> Hola mi nombre es Carlos Martinez, me dedico al desarrollo de software embebido desde el 2015.
> A lo largo de mi experiencia en distintas organizaciones, surge la necesidad de hacer este curso
> para brindar las bases de cómo se usa esta herramienta para soluciones reales en diversas
> aplicaciones.
> 
> :metal: Bienvenidos :metal:

### Objetivo.
> Asentar las bases de la herramienta Make y sus aplicaciones.

> Este curso es **bottom to top**: lo que significa que vamos a ir desde lo más esencial hasta lo más
> complejo, de tal manera que el aprendizaje se vuelva acumulativo.

### Para quien es este curso.
> Este curso va dirigido a toda persona que quiera aprender las bases de **make** y como esta herramienta
> nos permite automatizar procesos en la generación de archivos que no son código fuente a partir de 
> archivos de código fuente.

> Se presentan diversos ejercicios de práctica para asentar mejor los conocimientos, despues de todo
> este tipo de herramientas se aprenden practicando.

### Requisitos.
> Se requiere tener conocimientos basicos de lenguage C o C++.

### Links.
#### Make oficial site.
> https://www.gnu.org/software/make/
#### Manual.
> https://www.gnu.org/software/make/manual/make.pdf


## Set up
### Windows.
> * Abrimos la consola de comandos y tecleamos:

	make --version


### Mac.
#### Verificar si ya tenemos instalado make.
> *  Abrimos la consola de comandos y tecleamos:

	make --version
	
#### En caso de ya tener **make** instalado nos saldra un mensaje similar al siguiente:

![mac_make_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_make_installed.png)

##### **Nota: Si este tu caso te puedes saltar esta sección.**

#### En caso de no tener make instalado nos saldra el siguiente mensaje:

![mac_no_make_tool](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_no_make_tool.png)

#### Usando un gestor de paquetes para macOS: **Homebrew**.
##### Link al sitio de **Homebrew**: https://brew.sh
> En el link se muestra el sitio de donde descargaremos nuestra herramienta para gestion de paquetes **Homebrew**. Dentro del sitio nos muestra un comando para instalacion:

	/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

> * 1. Copiamos el comando y lo pegamos en nuestra consola:.

![mac_brew_install](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_brew_install.png)

> * 2. Esperamos a que la instalación se termine, podemos observar que **brew** nos instala las herramientas de línea de comandos de xcode y demás dependencias para desarrollo. 

![mac_brew_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_brew_installed.png)

> * 3. Una vez que tenemos **brew** instalado, probamos:

	make --version

![mac_make_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_make_installed.png)

> * 4. Tambien podemos verficar que el compilador de lenguage C (**clang**) ya está instalado.

	gcc --version

![mac_gcc_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/mac_gcc_installed.png)

### Linux (ubuntu).
##### Verificar si ya tenemos instalado make.
> * Abrimos la consola de comandos y tecleamos: **make --version**.

	make --version
> * En caso de ya tener **make** instalado nos saldra un mensaje similar al siguiente:


>   Si este es tu caso te puedes saltar esta sección.

