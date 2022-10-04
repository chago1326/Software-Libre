
# [Ir a inicio](Inicio.md.md/) 

# **Agregar un registro al archivo host**


## Los registros nos permiten simular la resolucion de un nombre de dominio. 

1. Abrir un cmd y ejecutarlo como administrador, luego ir a la siguiente ruta:

        c:\windows\system32\drivers\etc\host

2. Abrir el archivo host y agregar lo siguiente:

        192.168.50.10 webserver
        192.168.50.10 mibanco.com
        192.168.50.10 lfts.isw811.xyz

3. Para comprobar que todo esta correcto hacer ping a cada entrada creada mediante los comandos siguientes:

        ping webserver
        ping mibanco.com
        ping lfts.isw811.xyz