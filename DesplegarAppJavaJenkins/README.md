# Creación de los Pipeline en Php

![logo](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/logo.png)

## Índice

- <a href="#1">1. Clonar el proyecto en local desde Github </a>
- <a href="#2">2. Crear estructura de ficheros </a>
    - <a href="#2.1">2.1 Dockerfile </a>
    - <a href="#2.2">2.2 Jenkinsfile </a>
- <a href="#3">3. Subir cambios a Github </a>
- <a href="#4">4. Creación de Pipeline </a>
- <a href="#5">5. Comprobación </a>

<a name="1"></a>

### 1. Clonar el proyecto en local desde Github
Para empezar creamos un repositorio en nuestra cuenta de Github y luego clonamos el repositorio a nuestro equipo local.

![1](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/1.png)

<a name="2"></a>

### 2. Crear estructura de ficheros

<a name="2.1"></a>

### 2.1 Dockerfile
En el repositorio clonado anteriormente, empezamos a crear los ficheros del proyecto, en este caso con el fichero Dockerfile con la siguiente estructura. Usaremos una imagen de Docker de Tomcat para poder desplegar la aplicación Java con JSP.

![2](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/2.png)

<a name="2.2"></a>

### 2.2 Jenkinsfile
El siguiente fichero será el Jenkinsfile, con los siguientes pasos a seguir.

![3](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/3.png)

A parte de estos dos ficheros agregamos la aplicación Java al repositorio. Y ya estaría listo para subirlo a nuestro Github.

<a name="3"></a>

### 3. Subir cambios a Github
Usamos la aplicación Github Desktop para subir los cambios a nuestro repositorio. Como se puede apreciar en la imagen tenemos el proyecto Java, con los dos ficheros creados anteriormente.

![4](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/4.png)

Hacemos el push.

![5](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/5.png)

<a name="4"></a>

### 4. Creación de Pipeline
Una vez subido a nuestro repositorio podemos empezar a crear el Pipeline en nuestro servidor Jenkins.

![6](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/6.png)

Le ponemos una descripción al Pipeline.

![7](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/7.png)

Le decimos al pipeline que va a coger el proyecto desde nuestro repositorio de Github.

![8](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/8.png)

Y por último, le decimos que actúe sobre el fichero Jenkinsfile del proyecto que le viene desde Github.

![9](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/9.png)

<a name="5"></a>

### 5. Comprobación
Cuando acabamos de crear el pipeline nos saldrá que está “inactivo”.

![10](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/10.png)

Lo ejecutamos y esperamos a que se ejecute todos los pasos y veremos como nos ha dado que todo ha ido correcto.

![11](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/11.png)

Para comprobar que todo ha ido realmente bien, abrimos un navegador y colocamos en la URL: <b>localhost:82/app-web-demo</b>, que es nuestra aplicación.

![12](https://github.com/Regnierd/Jenkins/blob/main/DesplegarAppJavaJenkins/img/12.png)


