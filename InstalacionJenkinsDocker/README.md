# Instalación y configuración de Jenkins con Docker

![logo](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/logo.png)

## Índice

- <a href="#1">1. Requisitos previos </a>
- <a href="#2">2. Instalar Jenkins con Docker </a>
- <a href="#3">3. Acceso </a>
- <a href="#4">4. Instalación de Jenkins en Docker-Compose </a>
- <a href="#5">5. Acceso </a>

<a name="1"></a>

### 1. Requisitos previos
Para esta práctica necesitaremos tener una máquina con Ubuntu 20.04 con Docker y Docker-Compose instalado.


<a name="2"></a>

### 2. Instalar Jenkins con Docker
Lo primero que necesitamos es la imagen de Jenkins para Docker, para ello usaremos el siguiente comando para descargar la imagen: <b>sudo docker pull jenkins/jenkins:lts</b>.

![1](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/1.png)

Para comprobar que la hemos descargado usamos el comando <b>sudo docker images</b>.

![2](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/2.png)

Por último, debemos de crear el contenedor con la imagen descargada anteriormente. Le especificamos los puertos que va a tener abierto el contenedor para poder conectarnos a Jenkins. El comando quedaría tal que así: <b>docker run -p 8080:8080 -p 50000:50000 -v /your/home:/var/jenkins_home jenkins/jenkins:lts</b>

![3](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/3.png)

<a name="3"></a>

### 3. Acceso
Para saber que ya tenemos Jenkins en funcionamiento debemos de abrir un navegador y poner en la URL <b>localhost:8080</b> y veremos como se abre la pantalla de inicio de configuración de Jenkins.

![4](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/4.png)

Para obtener la contraseña que nos pide en la imagen anterior debemos de usar el siguiente comando: <b> sudo cat /var/lib/jenkins/secrets/initialAdminPassword</b>

![14](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/14.png)

Le damos a siguiente y seleccionamos la opción “<b>Install suggested plugins</b>” y le damos a siguiente.

![5](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/5.png)

En la siguiente pantalla se pondrá a instalarse Jenkins, cuando acabe le damos a siguiente.

![6](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/6.png)

Rellenamos los campos con nuestros datos y le damos a siguiente.

![7](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/7.png)

En la página siguiente establecemos la URL por defecto que tendrá el jenkins instalado.

![8](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/8.png)

Le damos a siguiente y veremos que ya podemos empezar a usar Jenkins.

![9-1](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/9-1.png)

<a name="4"></a>

### 4. Instalación de Jenkins en Docker-Compose
Para usar Docker-Compose tendremos que tener el fichero Dockerfile, el cual tendrá el siguiente código que podemos ver en la imagen.

![9](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/9.png)

Como podemos apreciar en el fichero Dockerfile podemos ver que el contenedor instalará unos plugins. Para ello tendremos que tener una lista de plugins. Usaremos un fichero .txt con todos los plugins dentro.

![10](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/10.png)

Obviamente, para usar el docker-compose necesitamos tener el fichero docker-compose.yml, donde tendrá la configuración del contenedor.

![11](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/11.png)

Cuando tengamos los 3 ficheros podemos proceder a construir el contenedor, con el siguiente comando:<b> sudo docker-compose build</b>

![12](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/12.png)

Cuando acabe de construir el contenedor, podemos levantar el contenedor con el siguiente comando: <b>sudo docker-compose up -d</b>

![13](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/13.png)

<a name="5"></a>

### 5. Acceso
Antes de empezar a configurar Jenkins, nos piden crear un dominio en concreto. Por lo tanto tenemos que ir a Apache y crear el fichero de configuración.

![16](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/16.png)

Y agregar el dominio al fichero <b>/etc/hosts</b>.

![15](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/15.png)

Una vez hecho esto, volvemos a ir al navegador y escribimos<b> -www.jenkins.javier.com:8080-</b> y nos saldrán las mismas pantallas de configuración descritas anteriormente, volvemos hacer los mismos pasos hasta llegar a la pantalla que vemos a continuación. Podemos apreciar que detecta el nuevo dominio sin problema, le damos a siguiente y listo.

![17](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkinsDocker/img/17.png)
