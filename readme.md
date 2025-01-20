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
Para poder llevar este curso de manera satisfactorio, se deben instalar las siguientes dependencias de desarrollo en nuestros equipos de computo.

> * Herramienta make.
> * Compilador de C/C++.

### Windows.
#### Verificar si ya tenemos instalado el entorno de desarrollo.
Corroboramos si tenemos **make** instalado, ingresamos en la terminal el siguiente comando:

	make --version

En caso de ya tener **make** instalado, nos saldra un mensaje similar al siguiente:

![win_make_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_make_installed.png)

Corroboramos si tenemos el compilador de C/C++ instalados, ingresamos cualquiera de los comandos siguientes.

	gcc --version

o

	g++ --version

En caso de ya tener instalado el compilador, nos saldra un mensaje similar al siguiente.

![win_compiler_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_installed.png)

##### **Nota: Si este tu caso te puedes saltar esta sección.**

En caso de no tener **make** instalado, nos saldra el siguiente mensaje:

![win_no_make_tool](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_no_make_tool.png)

Para instalar **make** usamos el siguiente comando:

	winget install ezwinports.make

![win_make_installation](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_make_installation.png)

Verificamos la instalación.

	make --version

![win_make_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_make_installed.png)

En caso de no tener instalado el compilador instalado, nos saldra el siguiente mensaje:

![win_no_compiler](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_no_compiler.png)

Para instalar el compilador, hacemos el siguiente proceso.
* 1. Navegamos al sitio oficial de MSYS2: https://www.msys2.org

* 2. Bajamos un poco hasta encontrar el instalador, damos clic en el enlace para descargar.

![win_compiler_installer](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_installer.png)

* 3. Una vez descargado, corremos el archivo ejecutable:

* 4. Especificamos el directorio **C:\msys64** (mi caso en particular) donde sera instalado MSYS2 y damos clic en **Next**.

![win_compiler_path](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_path.png)

* 5. Nos pide agregar un acceso directo y damos **Next** nuevamente.

![win_compiler_shortcut](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_shortcut.png)

* 6. Esperamos un tiempo para que se instale.

![win_compiler_installation](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_installation.png)

* 7. Damos clic en finalizar una vez instalado.

![win_compiler_done](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_done.png)

* 8. Dirigete al directorio de instalación y ejecuta **msys2.exe**.

![win_msys2_install](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_msys2_install.png)

* 9. Una consola comando se va a abrir, dentro de la consola ejecuta el comando **pacman -Syu** para actualizar las dependencias, al finalizar escribe la letra **Y** para terminar.

	pacman -Syu

![win_msys2_update](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_msys2_update.png)

* 10. Nuevamente nos dirigimos al directorio de instalación y ejecutamos nuevamente **msys2.exe**, ya con la consola abierta escribimos el comando **pacman -Su**, para actualizar las depedencias faltantes.

	pacman -Su

![win_msys2_upgrade](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_msys2_upgrade.png)

* 11. Nos dirigimos al directorio de instalacion y esta vez ejecutamos **mingw64.exe** para SO de 64 bits, usa **mingw32.exe** para SO de 32 bits.

![win_mingw_installer](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_mingw_installer.png)

* 12. Dentro de la consola que se ha abierto, escribimos el comando **pacman -S mingw-w64-x86_64-gcc** para SO de 64 bits, usa **pacman -S mingw-w64-i686-gcc** para SO de 32 bits.

	pacman -S mingw-w64-x86_64-gcc

o

	pacman -S mingw-w64-i686-gcc

![win_mingw_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_mingw_installed.png)

* 13. Copiamos el directorio de instalacion de mingw64 **C:\msys64\mingw64\bin** (mi caso en particular) y lo agregamos a las variables de entorno.

![win_variables](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_variables.png)

![win_variables](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_variables.png)

Verificamos la instalación.
	gcc --version

o

	g++ --version

![win_compiler_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/win_compiler_installed.png)

### Mac.
#### Verificar si ya tenemos instalado el entorno de desarrollo.
> * Abrimos la consola de comandos y tecleamos:

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
##### **Nota: normalmente ubuntu ya viene con todo el paquete de desarrollo instalado, solo debemos actualizar las herramientas.**

#### Verificar si ya tenemos instalado el entorno de desarrollo.
> * Abrimos la consola de comandos y tecleamos: **make --version**.

	make --version

![linux_build_installed](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/linux_build_installed.png)

#### En caso de no tener el paquete de desarrollo, debemos ingresar los siguientes siguientes comando:

> * 1. El siguiente comando nos permite obtener las ultimas actualizaciones de las herramientas de ubuntu.

	sudo apt-get update

> * 2. El siguiente comando nos permite descargar las herrameintas del entorno de desarrollo de ubuntu.

	sudo apt-get install build-essential

> * 3. El siguiente comando nos actualizar las herramientas a las ultimas versiones disponibles.

	sudo apt-get upgrade

> * 4. Verficar la instalación de make:

	make --version

> * 5. También podemos verificar los compiladores de lenguage C (gcc) y C++ (g++).

	gcc --version
	g++ --version

![linux_complete_setup](https://github.com/carlosmartinez871208/Curso_de_make/blob/main/images/linux_complete_setup.png)