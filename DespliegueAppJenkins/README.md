# Creación de los Pipeline en Php

![logo](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/logo.png)

## Índice

- <a href="#1">1. Clonar el proyecto en local desde Github </a>
- <a href="#2">2. Crear estructura de ficheros </a>
    - <a href="#2.1">2.1 Jenkinsfile </a>
    - <a href="#2.2">2.2 Dockerfile </a>
- <a href="#3">3. Subir cambios a Github </a>
- <a href="#4">4. Creación de Pipeline </a>
- <a href="#5">5. Comprobación </a>

<a name="1"></a>

### 1. Clonar el proyecto en local desde Github
Para empezar la práctica debemos de crear un repositorio en nuestra cuenta de Github y luego clonar ese repositorio a nuestro equipo local, para ello he usado Github Desktop.

![9](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/9.PNG)

Como podemos ver nuestro repositorio se llama hello-world-php-apache y que está dentro de la carpeta Github, esto quiere decir que el repositorio creado ya lo tenemos en local.

![10](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/10.PNG)

<a name="2"></a>

### 2. Crear estructura de ficheros
Lo primero que tenemos que hacer es crear el fichero index.php con algún código para verlo por pantalla más adelante.

![6](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/6.PNG)

<a name="2.1"></a>

### 2.1 Jenkinsfile
Luego tenemos que crear el fichero Jenkinsfile, para que le digamos a Jenkins con cuál fichero va a trabajar. 

![5](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/5.PNG)

<a name="2.2"></a>

### 2.2 Dockerfile

En el Dockerfile le diremos que coja la imagen con php y apache para poder abrir el fichero index.php.

![1](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/1.PNG)

En resumen nos quedamos con esta estructura de ficheros.

![12](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/12.PNG)

<a name="3"></a>

### 3. Subir cambios a Github
Después de crear todos los ficheros debemos de subir los cambios a nuestro repositorio.

![8](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/8.PNG)

<a name="4"></a>

### 4. Creación de Pipeline
Ahora tenemos que entrar a Jenkins y crear un nuevo Pipeline. Escribimos una descripción.

![2](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/2.png)

Ahora debemos de asignarle al pipeline que el proyecto viene desde un repositorio de Github y especificar el repositorio con la URL.

![13](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/13.PNG)

Y por último, decirle que el script viene desde un fichero Jenkinsfile y le damos a guardar

![3](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/3.png)

Y podemos ver que el pipeline ya está creado, ahora podemos ejecutarlo para comprobar si todo ha ido correcto.

![4](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/4.png)

Y por último, podemos ver que se ha puesto el tick verde, lo cual es que ha ido todo bien.

![7](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/7.PNG)

<a name="5"></a>

### 5. Comprobación
A continuación, abrimos un navegador y colocamos en la URL: localhost:81 y podemos ver como se nos carga la página index.php creada anteriormente.

![11](https://github.com/Regnierd/Jenkins/blob/main/DespliegueAppJenkins/img/11.PNG)




