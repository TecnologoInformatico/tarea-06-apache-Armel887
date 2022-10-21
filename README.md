# apache

Reemplace `$ALUMNO` por el nombre de su nombre de usuario en www.tecnologoinformatico.com

EJ: `dmascheroni`

1. Cree el directorio ~/repositorios y dentro clone el
repositorio: `https://github.com/TecnologoInformatico/AdmInf-web.git`
2. Actualice el repositorio de la lista de paquetes.
    `apt update`
3. Instalar el servidor Apache mediante apt.
4. Cree el directorio /var/www/$ALUMNO
5. Asigne como propietario del directorio su usuario.
6. Configure un nuevo Virtual host. (copiando el archivo de configuración por defecto)
  6.1. ServerName $ALUMNO.tecnologoinformatico.com
  6.2. Correo de contacto con el administrador.
  6.3. El root de la aplicación. (/var/www/$ALUMNO)
7. Modifique el archivo /etc/hosts de modo que el ServerName coincida con este equipo `127.0.0.1`.
8. Reinicie el servidor apache para que los cambios tengan efecto.
9. Copie el contenido del directorio ~/repositorios/AdmInf-web a /var/www/$ALUMNO, de tal modo que el contenido del repositorio antes clonado se encuentre en el root de la aplicación.
10. Verifique que el servidor funcione correctamente.
11. Ingrese la IP del servidor y el servername a continuación:

```json
{
    "serverName": "",
    "ip": ""
}


```

1 -  mkdir repositorios
     git clone `https://github.com/TecnologoInformatico/AdmInf-web.git`

2 - sudo apt update

3 - sudo apt install apache2

4 - sudo mkdir var/www/agonzalez

5 - sudo chown ubuntu:ubuntu /var/www/agonzalez

6 - cd /etc/apache2/sites-available/
    sudo cp 000-default.conf a.gonzalez.conf
    sudo nano agonzalez.conf

7 - cd /etc/
    sudo nano hosts(cambio localhost poner ip 129.148.28.149
    y en la ultima linea 127.0.0.1 agonzalez.tecnologoinformatico.com)

8 - ubuntu@instance-20220927-2201:~$ sudo systemctl reload apache2
    ubuntu@instance-20220927-2201:~$ sudo netfilter-persistent save
    run-parts: executing /usr/share/netfilter-persistent/plugins.d/15-ip4tables save
    run-parts: executing /usr/share/netfilter-persistent/plugins.d/25-ip6tables save

9 - ubuntu@instance-20220927-2201:~$ cp -r ~/repositorios/AdmInf-web/* /var/www/agonzalez
     
10 - ubuntu@instance-20220927-2201:~$ sudo a2ensite a.gonzalez.conf
     Enabling site a.gonzalez.
     To activate the new configuration, you need to run:
     systemctl reload apache2

11 - ubuntu@instance-20220927-2201:~$ { "serverName": "agonzalez.tecnologoinformatico",; "ip": "129.148.28.149" }

