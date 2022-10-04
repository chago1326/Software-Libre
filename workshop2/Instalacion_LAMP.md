# [Ir a inicio](Readme.md/) 


### Cambiar el nombre de la maquina por default por **webserver**, esto mediante el siguiente comando:

    sudo hostnamectl set-hostname webserver

### Luego se debe editar con vim el archivo host de la maquina virtual mediante el siguiente comando:

    sudo vim /etc/host

### Una vez dentro del archivo host reemplazar el nombre de la maquina por el nuevo nombre, quedando de la siguiente manera

    127.0.0.2 webserver

### Una vez realizados los pasos anteriores reiniciar la maquina para ver los cambios
****
# **Instalar LAMP**

### Para actualizar los paquetes ejecutar el siguiente comando

    sudo apt-get update
### Para instalar las herramientas LAMP, se debe ejecutar los siguientes comandos

    sudo apt-get install vim vim-nox curl git apache2 mariadb-server mariadb-client php7.4 php7.4-bcmath php7.4-curl php7.4-json php7.4-mbstring php7.4-mysql php7.4-xml

### Durante la instalacion de los paquetes, se preguntará si se desea continuar, por lo que damos en la tecla **Enter**