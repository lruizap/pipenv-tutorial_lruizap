# Pipenv

Instrucciones básicas para el uso de la herramienta "pipenv"

Vamos a tratar de instalar pipenv para Windows

Pipenv es una herramienta que nos permite administrar dependencias y crear entornos virtuales de Python a través de un modulo llamado Pipenv.

## 1. Instalación

Para instalar tendremos que instalarlo con:

```bash
pip install pipenv
```

Una vez instalado, podremos comprobar las librerías instaladas con

```bash
pip list
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3629b024-3db1-4829-adfc-73bfc0b0fb43/Untitled.png)

---

## 2. Utilización

Para comenzar a utilizar esta librería usaremos el siguiente comando:

```bash
pipenv shell
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2d130365-1263-41a0-943f-166e4b01c51b/Untitled.png)

Esto nos crea un entorno virtual y un fichero con las dependencias y las versiones del proyecto.

En este fichero listaremos las dependencias, módulos y versiones que utilizará el proyecto de forma automática.

Como podemos comprobar, la herramienta nos ha creado un entorno virtual en nuestro ordenador para que todo aquello que instalemos, sea instalado en dicho entorno y no en todo el PC

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1f2ca199-5002-4709-b275-263838a705e9/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5958212e-72fa-4ad3-9636-dc2bfea3c4b0/Untitled.png)

Así cuando creemos un nuevo proyecto, las dependencias de otros proyectos no interferirán en nuestro desarrollo.

Con esto ya tenemos nuestro proyecto inicializado y podremos comenzar a trabajar en él.

---

## 3. Ejemplo

Vamos a comenzar a trabajar con la herramienta haciendo un proyecto de ejemplo. Lo que haremos será instalar una librería para mostrar texto de colores por pantalla.

Para esto usaremos la librería `colorama`

Vamos a instalar las librerías a través del entorno virtual para que no se nos instale en nuestro ordenador. Para ello se debe usar el comando `pipenv`en vez de `pip`

```bash
pipenv install colorama

# Para desinstalar paquetes es tan sencillo como

pipenv uninstall colorama
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5ab946af-d0c9-4ebd-a116-4489f62e8019/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ab348a6b-d6bf-4d7f-88a9-b74ef431a45e/Untitled.png)

Una vez instalada la librería podemos irnos al fichero “Pipfile” que se nos había creado anteriormente para comprobar que efectivamente ha sido modificado y nos muestra la librería que hemos instalado.

Para comprobarlo vamos a crear el fichero “main.py” y a escribir el siguiente código

```python
from colorama import Fore, Style

print(Fore.RED+"Hola mundo")
print(Style.RESET_ALL)
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e0084437-8762-4e09-bf76-e3b24a7d750d/Untitled.png)

Una vez introducido el código debemos ejecutar el fichero dentro del entorno virtual ya que dentro de este es donde se encuentran instaladas las librerías.

---

## 4. Pipfile.lock

Este archivo es para decirle internamente al entorno que versión es la que necesitamos de las librerías que hemos instalado.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c1cbb4e7-dffb-4ed2-96ad-623335076caa/Untitled.png)

Como podemos ver, de la librería “colorama” estamos usando actualmente la versión 0.4.6

Este archivo no debe ser modificado, simplemente nos da información sobre nuestro proyecto

---

## 5. Librerías de desarrollo

Al mirar más de fondo el archivo “Pipfile” nos daremos cuenta que hay dos formas distintas de instalar librerías, los “packages”, que son librerías que necesita la aplicación para funcionar; mientras que los “dev-packages” son las librerías de desarrollo del proyecto

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/25504223-f130-48be-ba97-aeefda9d935b/Untitled.png)

Vamos a proceder a instalar “colorama” como “dev-packages”

```bash
pipenv install colorama --dev
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e36cd97a-7e63-4d0f-8be0-706cdcc2d470/Untitled.png)

La diferencia entre estos dos es el uso que le demos a la librería. Si el uso es concreto ponla en “packages”, pero si es para desarrollo entonces debe ir en “dev-packages”.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2bfef5fc-2c20-4ad3-be73-51435748481a/Untitled.png)

---

## 6. Frameworks

En este apartado instalaremos un framwork para comprobar el funcionamiento de “pipenv” con esta herramienta.

Vamos a aprovechar y explicar el fichero “requirements”, este fichero nos indicará los elementos que es necesario instalar para que nuestro proyecto funcione correctamente.

En este fichero tendremos que indicar que dependencias queremos instalar junto a la versión

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/199ce104-7517-4285-954b-13a491728bea/Untitled.png)

Para instalar las librerías, dependencias o frameworks indicadas en este fichero tendremos que introducir el siguiente comando:

```bash
pipenv install -r requirements.txt
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8b111968-3500-4310-996b-98b7893a37aa/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c0a16a2a-23e7-421c-a839-ac9ced07e708/Untitled.png)

Para comprobar que Django está instalado vamos a inicializar un proyecto con el comando

```bash
django-admin startproject nombre-proyecto
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8c97363e-b03d-497d-ae03-da66307cacdd/Untitled.png)

Para iniciar la aplicacion debemos arrancar el proyecto con el comando

```bash
python manage.py runserver
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/25235e03-04c2-4de2-8161-8b61f5620867/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8a6cfb4d-af21-4f79-9d3a-2abbf12508e0/Untitled.png)

Y con esto tenemos una aplicación de Django en localhost.

---

## 8. Ver las dependencias instaladas

Para ello introduciremos el comando:

```bash
pipenv graph
```

Con esto podemos ver tanto los módulos instalados como las dependencias que instala cada módulo para funcionar correctamente

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/78cb822c-ec64-4615-a388-39f79a2273bb/Untitled.png)

También podemos comprobar las vulnerabilidades de seguridad que tengan los paquetes instalados. Esto nos sirve para actualizar versiones

```bash
pipenv check
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/25cfcb56-f116-4f49-9b71-3c9f0a688e7c/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d853b19d-0b62-4c67-b365-1383396dfe0f/Untitled.png)

Si hay alguna vulnerabilidad tendremos que actualizar la versión del paquete que falle.

---

## 9. Desplegar la aplicación

Para comenzar a desplegar la aplicación, debemos comenzar por introducir el siguiente comando

```bash
pipenv lock
```

Esto lo que hace es ver las dependencias del proyecto y actualizarnos el fichero de despliegue

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/01b550ef-91c3-48e8-9ce9-4c36f58a19e2/Untitled.png)

Tendremos que tener en cuenta que tendremos que cambiar el fichero “Pipfile” para introducirle la versión de los módulos que estamos usando y a su vez el fichero “requirements.txt” ó también podemos hacer que se ignore el fichero “Pipfile” y solo se tome el fichero “Pipfile.lock” para instalar.

```bash
pipenv install --ignore-pipfile
```

Así podemos instalar exactamente el mismo módulo con la misma versión de desarrollo del proyecto.

---

## 10. Ejecutar el proyecto sin tener que entrar al entorno virtual

Lo primero que tendremos que hacer es salir del entorno virtual

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cba40f38-225f-41c1-875e-6b139d149622/Untitled.png)

Para volver a entrar es tan fácil como volver a introducir el comando

```bash
pipenv shell
```

Una vez finalizado el trabajo, vamos a borrar el entorno virtual. Para ello tendremos que usar el comando

```bash
pipenv --rm
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b0eec6de-2c36-4fab-b496-3afc882c97d2/Untitled.png)

Y ahora volvemos a inicializar el entorno virtual `pipenv shell` . Una vez inicializado tendremos que usar el comando

```bash
pipenv install
```

Para que se nos instalen los módulos que están especificados en el documento “Pipfile.lock”

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a6be209d-d8ca-4322-9b89-5a800c3feb3f/Untitled.png)

---

Con esto ya estaría el uso básico de esta herramienta para trabajar con proyectos de python de forma aislada.
