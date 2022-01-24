# Creación de un Pipeline en Jenkins
![logo](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/logo.png)

## Índice

- <a href="#1">1. Requisitos previos </a>
- <a href="#2">2. Creación de un Pipeline </a>
- <a href="#3">3. Solucionar error </a>
- <a href="#4">4. Comprobación </a>


<a name="1"></a>

### 1. Requisitos previos
Para empezar esta práctica necesitamos tener instalado en nuestra máquina virtual, Ubuntu 20.04, el servidor de automatización Jenkins.

<a name="2"></a>

### 2. Creación de un Pipeline
Un pipeline es una guía de instrucciones que la aplicación debe de seguir desde el repositorio de versiones hasta llegar a los usuarios. Esto sirve para un despliegue continuo de nuestras aplicaciones.

Para empezar tenemos que darle a nuevo item y nos saldrá la siguiente imagen. Le ponemos un nombre y seleccionamos Pipeline, le damos a siguiente.

![1](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/1.png)

Nos saldrá la siguiente configuración de pipeline, podemos poner una descripción para saber lo que hace concretamente el pipeline que vamos a crear.

![2](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/2.PNG)

A continuación ponemos la siguiente instrucción que va hacer nuestro pipeline, en este caso creará una imagen en docker con Maven instalado y nos mostraría la versión de Maven.

![3](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/3.PNG)

Cuando acabemos de hacer la configuración podemos ver que el pipeline ya está creado, ahora solo falta ejecutarlo para ver si funciona.

![4](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/4.PNG)

Podemos ver que ha habido un fallo al ejecutar el pipeline. A continuación explicaré cómo arreglar este error.

![5](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/5.PNG)

<a name="3"></a>

### 3. Solucionar error
El error que nos da es porque no tenemos los plugins instalados de Docker, ya que nuestro pipeline necesita Docker para crear las imágenes, por lo tanto, tendremos que ir a la configuración de Jenkins e instalar los plugins necesarios.

![6](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/6.PNG)

Una vez que se acabe de instalar los plugins nos saldrán como que ya están instalados y actualizados, nos pide reiniciar el servicio de Jenkins pero antes tenemos que hacer otra cosa.

![7](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/7.PNG)

Lo que tenemos que hacer a continuación es agregar el usuario <b>jenkins</b> al grupo <b>docker</b>. Ahora sí que podemos reiniciar el servicio de Jenkins.

![8](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/8.PNG)

<a name="4"></a>

### 4. Comprobación
Si recargamos la página podemos ver como ya nos sale que todo ha ido bien.

![9](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/9.PNG)

A continuación tendremos que hacer lo mismo para diferentes lenguajes, como PHP, Python, Ruby, etc. Y todos nos tienen que salir que se han ejecutado correctamente.

![10](https://github.com/Regnierd/Jenkins/blob/main/CreacionPipelineJenkins/img/10.PNG)

    