<h1>Proyecto 1º Trimestre Servidor Web.</h1>

Para empezar este proyecto empezaré con un Ubuntu limpio recién instalado.
Haré un sudo apt update para actualizar los paquetes del S.O.

![1](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/9a070caa-6002-4f57-94e8-72239565b843)

Ahora voy a instalar apache2 con el comando apt isntall apache2.

![2](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/24ff2ad3-d60a-4d32-af2f-a7f2a8b975c0)

Vamos a comprobar que el firewall del S.O. permite las conexiones a internet. Usaremos el comando ufw app list.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/349f9043-4c48-4063-adc7-fb4f86df880e)

Mediante el comando: ufw app info "Apache Full" vamos a comprobar la información que tenemos de apache2 en nuestro S.O.(puertos que usa,etc)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/78022486-301f-49ab-abbe-ab894c8e86b2)

Para permitir el tráfico HTTP y HTTPS en nuestro server usamos el comando: ufw allow "Apache Full"

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/c12382c0-0ecb-4c2a-9217-2fcf00a950f8)

Una vez instalado y configurado de forma muy básica nuestro apache, podemos comprobar su funcionamiento desde el navegador.
Antes dejo aquí una muestra de la configuración de red de mi S.O.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/d7c698af-8198-4dd5-ab43-0adbace92a3a)

Ahora puedo buscar la direccion ip en el navegador, (en mi caso 127.0.0.1 O 182.168.195.128)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/bb4d7456-0a6c-4e17-89c2-18f5027bd46a)

Una vez tengo mi servidor apache instalado, voy a instalar mysq usando el comando: apt install mysql-server

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/e715d615-8f34-4cf2-940e-8ff3b145cd9c)

Podemos acceder a mysql y ver si la instalacion es correcta además de su versión usando el comando: sudo mysql

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/630dd97f-f528-446d-850e-8f4e60225d7d)


Para poder seguir instalando aplicaciones en nuestro ubuntu es importante actuyalizar el S.O sudo apt update

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/65de4a71-03ea-4435-8839-7dd8aaac50ce)

Seguimos instalando ahora PHP y librerías relacionadas con php-apache2 y php-mysql. (Ya las tenía instaladas pero adjunto captura).

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/3394744c-73fc-450c-8b58-4560be6ac886)

Puedo empezar a crear los dos dominios DNS en mi directorio raíz /var/www 

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/d5d0bd09-e0fa-4622-a2d9-d03cdd2cc677)

Voy a cambiar los permisos sobre el documentRoot (/var/www) para que se permita el acceso de lectura al directorio web general y a los archivos y las carpetas que contiene

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/5b5ef697-bec3-4fb5-8375-39db51108e39)

Voy a crear una pagina html de demostración en centro.intranet para comprobar luego que los host virtuales están operativos.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/562866b2-4b1d-4bd3-aa40-848c318b4299)

Hago lo mismo para departamentos.centro.intranet.

Una vez hecho esto, voy a crear un archivo de configuración de host virtual para centro.intranet, por defecto tenemos la 000-default.conf.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/5906f0d9-1832-4f8a-b465-ed3bbd2a80e8)

Haré lo mismo para departamentos.centro.intranet. Haré una copia con el nombre: departamentos.centro.intranet y la modificaré.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/bf2dc0d8-ecee-4c76-82ef-280488c18828)

Voy a modicarlo con nano, luego guardo el archivo y cierro.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/d3593d83-c697-456a-9974-b6fbeb32319f)

Una vez creados los archivos de configuración de los Hosts virtuales, voy a eliminar los que vienen por defecto en Apache y a habilitar los que he creado.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/8b214840-1ac5-485c-84f8-8d00a993cbb3)

Para finalizar vamos a agregar los DNS a la ip de mi servidor en el archivo hosts.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/8b214840-1ac5-485c-84f8-8d00a993cbb3)

Una vez he reiniciado el servidor, usando el comando "systemctl reload apache2" apache ya debería mostrarnos las páginas de ejemplo de cada Host virtual. voy a comprobarlo.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/0b7804c9-7886-4c4e-ace4-50edac322463)

Haré la misma comprobación con mi dominio virtual departamentos.centro.intranet.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/4d12a35a-1f07-461f-a498-4f1afae37d45)

Voy a crear una página de prueba de formato php para probar que PHP funciona correctamente.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/34a823ec-31bd-41b3-a2c1-b42efd432534)

La página de ejemplo con informacion php se ve así.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/9f64ecce-a556-448d-8a28-ff65f2ddc5a6)

Ahora voy a configurar mysql para instalar wordpress, crearé una base de datos de wordpress (entramos en mysql mediante el comando: sudo mysql).

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/7e90f744-bc73-4521-ab4a-5372ed270576)

Ahora voy a crear un usuario para la base de datos WordPressBD que acabo de crear, también le indico la contraseña de acceso al usuario y le doy permiso sobre toda la base de datos.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/7065d312-f9a8-4277-bbe5-abdec601837d)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/f06bc063-84ff-4eed-b9b8-d92cd752ee43)

Podemos comprobar que se ha creado el usuario usando la siguiente query: mysql> SELECT user FROM mysql. user;

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/377f4ce2-02af-4170-a889-cd897db12335)

Para instalar Wordpress voy a modificar el archivo de configuración de mi domino centro.intranet que servirá contenido a través de wordpress.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/0e3f669c-fbde-4de3-acab-dd6eaf393237)

Es necesario activar el modulo rewrite para que Wordpress use enlaces permanentes.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/9186a03b-e16f-4fed-8906-d981e80d318e)

Voy a comprobar que el servidor se encuentra operativo después de aplicar los cambios en virtual host.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/da4530ca-a8f6-4f7e-ba90-7aeaa95dae6f)

En el archivo de configuración apache2.conf voy a implementar la directiva ServerName y la IP de mi server.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/b56f3b9d-c40b-4975-bcc7-4e7f3eb72ca0)

Voy a comprobar que la configuracíon es correcta mediante: apachectl configtest.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/a0d963c3-0185-4e67-90e6-f56878c5be59)

El servidor está listo para instalar wordpress. Para ello voy a instalar el paquete wget para descargar los archivos de la nube.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/8992531d-06f9-413a-8613-534c90528678)

Ahora voy a descargar el paquete comprimido de wordpress desde la página oficial.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/c07d1f6b-3f3f-4c10-946e-820196590980)

Una vez que he descargado el archivo comprimido, instalaré la aplicación de descompresión "unzip"

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/171452b2-a6fe-4a56-a340-8e3ceee92591)

Ahora voy a mover el archivo comprimido (antes de descomprimirlo) al directorio centro.intranet(Mi dominio que usará Wordpress).

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/2c6ea0df-6191-40ef-8f07-b03065f34c69)

Una vez situados en el directorio correspondiente, voy a descomprimir el archivo.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/6dc4b5ca-1342-45d0-888a-22e2900ff653)

Así queda mi DNS una vez he descomprimido wordpress.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/9d85afaf-a4d5-4536-8dfc-cff6e6ab1df3)

Ahora voy a comprobar mediante el navegador si todo funciona y comenzaré a configurar mi wordpress.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/a93fba3c-1114-46ef-8fec-fc64ce27274d)

Voy a configurar wordpress desde el navegador usando la base de datos que creé antes, el usuario su contraseña.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/7efc0c43-4b70-4043-8fe7-d233ca611e7c)

Me dice que no puede encontrar el fichero wp-config.php (no coinciden los nombres), he buscado en el directorio wordpress y al descomprimirlo el nombre es distinto pero el archivo es igual, tiene de nombre wp-config-sample.php. Le cambiaré el nombre a wp-config.php

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/2dff4823-c5e7-4a3d-a1a7-5e595678a9f4)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/db0a4e4c-0182-4259-b214-352dd9456ccf)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/bcd85640-9df9-4e0a-a67a-4c29e6cfd9ef)

Ahora recargo el server apache con systemctl restart apache2 y vuelvo a conectar wordpress con la base de datos.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/e3193ebe-ac7e-48cf-9cad-7116248bb1e6)

Una vez wordpress ha conectado con exito con la base de datos mysql de mi server apache, voy a instalarlo definitivamente.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/ecb2d223-aed2-4132-bc90-00ddac550445)

Una vez instalado voy a hacer login con mi mi usuario de wordpress RafaWordPress.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/ac20e4fd-8426-49f4-8a5e-cbf34ebfb72b)


![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/7ef4ba1b-b10a-45ff-923e-eaf1d36e7af2)

Con esto ya tenemos el wordpress instalado correctamente y vinculado a nuestra base de datos mysql.

Así se ve mi pagina de centro.intranet usando wordpress.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/d67c6406-3884-4c51-859b-4cc0a5b555b9)


Ahora voy a implementar el modulo wsgi, antes voy a instalar librerias de python que son necesarias.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/15fff534-cb40-4bea-93ee-c33348e977e7)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/07dbcabe-edfe-4038-9102-309eb1a23304)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/d327149a-d462-4344-9dcc-ea47720974e3)

Ya tenemos el modulo instalado voy a habilitarlo usando: a2enmod wsgi

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/9991e362-75f9-486d-b39b-2d0bf9c579c8)

Voy a usar django para probar que mi servidor puede interpretar el lenguaje python, para instalar django usar pip.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/ffe9797d-4a8f-4fac-89d9-189e37cacd7e)

Ahora voy a isntalar django mediante el comando: python3 -m pip install Django.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/af103ebd-4b7e-46d9-af56-ce465fd7bf33)

Voy a instalar git para poder descargar archivos desde repositorios de git hub.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/92f81925-143f-4a24-beb4-b2b0d077d559)



Una vez instalado git, voy a extraer de git hub la aplicacion django y la descargaré directamente en mi DNS departamentos.centro.intranet. 

Para probar con una aplicación voy a crear un pequeño script muy simple que mediante Flask se visualizará en mi navegador. 
Primero voy a instalar Flask.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/612ab601-703d-4c15-bddb-83ec0abfc3b3)

Ahora voy a crear el script llamado aplicacion.py dentro de mi DNS departamentos.centro.intranet.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/8c7b6b76-485f-4b57-96f3-e9a026f1baa7)

Una vez creada la aplicación voy a crear un archivo de configuración llamado aplicacion-wsgi.ini para la aplicación dentro del mismo directorio.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/f577ee4a-ae61-4206-b8e2-150655464376)

El directorio de mi DNS quedad así.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/7c65298a-945d-410f-8249-909804844ea0)

Ahora voy a modificar mi archivo virtual host para departamentos.centro.intranet. 

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/df7ccd72-bfe5-4ce6-84b8-5423be2924f3)

Ahora voy a reiniciar apache y comprobar si funciona.



