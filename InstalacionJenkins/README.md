# Instalación y configuración de Jenkins en Linux

![logo](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/logo.png)

## Índice

- <a href="#1">1. Requisitos previos </a>
- <a href="#2">2. Instalar Jenkins </a>
- <a href="#3">3. Iniciar Jenkins </a>
- <a href="#4">4. Abrir el firewall </a>
- <a href="#5">5. Configurar Jenkins</a>

<a name="1"></a>

### 1. Requisitos previos
Para realizar la siguiente práctica necesitaremos una máquina virtual de Ubuntu con la versión 20.04. 
Con la instalación de Open JDK 11 anteriormente y la creación de un dominio.

Creamos el sitio web con Apache, y le asignamos el nombre de nuestro dominio como “<b>-www.javieric.com-</b>” y que escuche por el puerto 8080. Para que también funcione debemos de agregar al fichero hosts el nuevo dominio, para que actue en local.

![15](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/15.PNG)

<a name="2"></a>

### 2. Instalar Jenkins
Lo primero que haremos será descargarnos los paquetes de la propia página oficial de Jenkins ya que los paquetes que vienen con Ubuntu suelen ser versiones anteriores. Usaremos el siguiente comando:<b> wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add</b>. Una vez hecho el sistema nos dará un OK.

![1](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/1.png)

Cuando nos diga el OK, debemos de conectar el repositorio de paquetes de Debian a <b>sources.list</b> del servidor con el siguiente comando:<b> sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'</b>

![2](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/2.png)

Una vez hecho lo anterior tendremos que actualizar los paquetes con el comando<b> sudo apt update</b>.

![3](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/3.png)

Una vez actualizados los paquetes ya podremos instalar Jenkins en nuestro servidor. Con el comando <b>sudo apt install jenkins</b>.

![4](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/4.png)

<a name="3"></a>

### 3. Iniciar Jenkins
Cuando acabe de instalarse debemos de iniciar Jenkins y comprobar el estado del servicio. Usaremos el siguiente comando: <b>sudo systemctl status jenkins</b>.

![5](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/5.png)

<a name="4"></a>

### 4. Abrir el firewall
Ahora debemos de activar el firewall para Jenkins, el cual trabajará en el puerto 8080.
Para ello usaremos el siguiente comando:<b> sudo ufw allow 8080</b>. Después de habilitar el firewall, podemos comprobar el estado y vemos que el 8080 está activo.

![6](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/6.png)

<a name="5"></a>

### 5. Configurar Jenkins
A partir de aquí ya podremos empezar con la configuración de Jenkins, para ello tendremos que abrir un navegador y poner el dominio creado anteriormente con el puerto activado recientemente. Y se nos abrirá la siguiente pantalla.

![7](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/7.png)

La contraseña que nos pide en la imagen anterior la podremos obtener con el siguiente comando en la terminal del sistema, <b>sudo cat /var/lib/jenkins/secrets/initialAdminPassword</b>

![8](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/8.png)

Una vez puesta la contraseña en la configuración le damos a siguiente y nos aparecerá la siguiente imagen, nosotros le daremos a “<b>Install suggested plugins</b>” y le damos a siguiente.

![9](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/9.png)

Y empezará el proceso de instalación.

![10](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/10.png)

Cuando acabe la instalación nos saldrá otra pantalla, que será la creación de un usuario para poder acceder a Jenkins, solo tendremos que rellenar los campos.

![11](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/11.png)

Una vez rellenado los campos le damos a siguiente y nos saldrá otro campo para verificar la URL que usaremos para acceder a Jenkins. Le damos a guardar y acabar.

![12](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/12.png)

Una vez acabado nos saldrá un mensaje diciendo que Jenkins está listo. Le damos a empezar con Jenkins.

![13](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/13.png)

Y por último nos saldrá el index de Jenkins listo para usar.

![14](https://github.com/Regnierd/Jenkins/blob/main/InstalacionJenkins/img/14.png)



