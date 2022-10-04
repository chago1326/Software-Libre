# [Ir a inicio](Readme.md/)


## 1. Estructuras de directorios para sitios

1-Desde la maquina anfitriona, a nivel del archivo
vagrantfile, creamos la siguiente estructura de los archivos y directorios con los siguientes comando:

    1. mkdir -p sites/lfts.isw811.xyz/public

    2. touch sites/lfts.isw811.xyz/public/index.html

    3. echo "<h1>Hola Mundo</h1>" > sites/lfts.isw811.xyz/public/index.html

Importante Para que esta configuración surta efecto, debe:

## 2. Creacion de vhost

1- En la maquina Anfitriona crear la plantilla para el VHOST mediante el comando:

    touch lfts.isw811.xyz.conf

2- Editar el archivo y pegamos el siguiente contenido:

    <VirtualHost *:80>

        ServerAdmin webmaster@lfts.isw811.xyz
        ServerName lfts.isw811.xyz

        # Indexes + Directory Root.

        DirectoryIndex index.php
        DocumentRoot /vagrant/sites/lfts.isw811.xyz/public

        <Directory /vagrant/sites/lfts.isw811.xyz/public>
            DirectoryIndex index.php
            AllowOverride All
            Require all granted
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/lfts.isw811.xyz.error.log

        # Possible values include: debug, info, notice, warn, error, crit,

        # alert, emerg.

        LogLevel warn

        CustomLog ${APACHE_LOG_DIR}/lfts.isw811.xyz.access.log combined
    </VirtualHost>

3-Modificamos el Vagrantfile, para agregar la siguiente dirección:

    config.vm.synced_folder "sites/", "/home/vagrant/sites", owner: "www-data", group: "www-data"

4-Desde la maquina virtual se copia el archivo vhost a la ruta de sitios disponibles de apache

    sudo cp /vagrant/lfts.isw811.xyz.conf /etc/apache2/sites-available/

5-Desde la maquina virtual se instalan las extensiones de apache

    sudo a2enmod vhost_alias  rewrite ssl

6-Editar el archivo **/etc/apache2/apache2.conf** y agregar lo siguiente:

    ServerName webserver

7-Habilitamos el sitio lfts.isw811.xyz.conf

    sudo a2ensite lfts.isw811.xyz.conf


8-Para aplicar la configuración anterior, se debe reiniciar el servidor de apache mediante los siguientes comandos:

    sudo apache2ctl -t
    sudo systemctl reload apache2.service