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



