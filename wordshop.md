## Wordshop 1

### Prerrequisito Instalación de Virtual Box y Vagrant


[Virtual Box](https://www.virtualbox.org/)

[Vagrant](https://www.vagrantup.com/)

### Instalación de Virtual Box

Se instala en la pagina principal del virtualizador, ya instaldado
se debera entrar a la configuración de la BIOS del computador para 
habilitar la configuración de virtualización.

Luego procedemos a Iniciar el virtual box.

### Instalación de Vagrant

Se utiliza desde la terminal, se debe realizar un folder de las maquinas virtuales que se ocuparan con el vagrant.

### Creacion maquina Virtual

1. Para crear la primer maquina virtual se debe crear una carpeta y darle el nombre que usted prefiera o ya que se utilize las convenciones debidas.
2. Debera ingresar en la pagina de Vagrant en la parte superior donde lleva por nombre cajas, ahi debera escoger la maquina virtual de usted necesita, en este caso utilizaremos `dedian/bullsete64`.
3. Luego se mostraran una serie de comando con los cuales utilizaremos para la instalacion de la maquina virtual.


### Creacion LAMP y algunos cambios para hacer el servidor

1. Crear el nombre de la carpeta anfitriona: webserver: `vaigrand/debian/bullseye64`
2. En la terminal ejecutamos el init ` debian/bullseye64`

Para resolver un problema que es muy comun que es el del nombre del dominio que tendra esa maquina virtual se debe ingresar a la direccion `c:Windows\System32\drivers\hosts`

1. Luego Ejecutaremos el vagrand up que lo que hace es descargar la imagen 
2. Luego lo iniciamos

## Notas Importantes 

1. Se debera Cargar el agente y la llave SSH
2. Se cargar con el siguiente comando `"eval "$(ssh-agent -s)""`

## Creación del LAMP

1. Actualizamos los paquetes disponibles con el comando `apt-get update`

#### Punto importante Instalación de El servidor 

1. Se debe instalar los paquetes en la terminal.
2. Se abre el terminal y se debe escribir lo siguiente `sudo apt-get install vim vim-nox curl git apacge2 mariadb-server mariadb-client php7.4 php7.4bcmath php7.4xml php7.43som`
3. Se instalara el php,apache,mysql server.