Para empezar vamos a instalar ubuntu22.04 que actuará como master.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/f7f8a4c1-5230-4f63-861d-e1441cc95a5c)

Una vez hemos arrancado la máquina master, vamos a actualizarla y upgradear los paquetes apt.
En la máquina master instalamos apache2.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/c07fc334-2c84-4dbd-9c2b-fb50ec87635f)

Una vez instalado nuestro servidor apache, vamos a concederle permiso de trafico http y https a nuestra firewall.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/1c53c650-1bc3-4136-be7e-a7b1eedabb31)

Podemos comprobar que funciona correctamente mediante: "https://ip_del_servidor"

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/eea7fbc7-9668-4715-84d7-59fe5f5a86b4)

Ahora voy a instalar php y librerías de php necesarias.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/3ee97726-cbd2-49a2-bc9b-c618c34c7172)

Una vez he instalado php voy a instalar mysql.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/013bd260-2ab9-4916-94c2-67ab1f0f9aeb)

Vemos que puedo acceder a mi base de datos mysql a través del usuario root.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/5fa18fce-ca72-4baf-a36c-0d9117bdb25b)

Voy a crear un virtualhost para mi servidor en el directorio /var/www/ , luego voy a cambiarle los permisos.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/e4b8608a-f556-44cc-bb5a-7062e0b39280)

Ahora voy a crear un archivo de configuración nuevo, (apache trae uno predeterminado).

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/7c44f20a-b0ae-4a23-a6a8-e497400d4b42)

Una vez creado el archivo de configuración para nuestro dominio recién creado, voy a activar la configuración.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/188e827d-3f46-42b0-9670-034a7f81716c)

Ahora voy a desactivar el virtualhost por defecto de apache: 000-default.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/1fd3947e-af09-44cb-8aa1-321c4dc43715)

Luego voy a usar el comando: "systemctl reload apache2", para aplicar la nueva configuración.

Una vez he recargado la configuración vamos a añadir un index.html a nuestro virtualhost para probarlo.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/f3f2530f-fb4d-4dbb-85cc-6938d5ae81fa)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/4c662894-8a1c-4e06-ba73-4e282cf7ebf0)

Ahora voy a especificar de forma global(archivo apache2.conf) para darle nombre al servidor.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/582dfa12-090e-407e-9399-bbcf9ab0b000)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/32f51d51-ba5a-4b91-a099-269132b192de)

Vamos a añadir el nombre de nuestro dominio al archivo /etc/hosts

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/18837e1e-ed18-459b-b312-a7c760228ffc)

Voy a probar que el dominio responde.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/00a3747c-c8d2-41da-83ea-81458022613a)

Ahora voy a darle prioridad a los archivos de formato .php mediante el modulo dir.conf

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/3c4c411d-0393-49a2-9b83-368d056bb42a)

Una vez hecho esto voy a crear un archivo .php de prueba para que me lo muestre antes que otro de formato .html

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/0205c5d8-8423-4b42-955c-7e67d8d79212)

Voy a añadir la directiva directory en mi virutal host para dar acceso a los clientes.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/683722dd-36b4-455c-8ede-570b04f7cf40)

Ahora voy a crear una base de datos rafamarismaBD en mi servidor mysql y un usuario, para que los usuarios accedan a ella.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/2cd467d7-fd6b-4f04-a6a8-3ce94f5150eb)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/0a692e61-98cb-4a14-b690-5dfd9538abbf)

Ahora le doy permisos al usuario que he creado para hacer consultas y modificaciones en la BD recién creada.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/c4efd7b1-f2e4-4504-805b-0d348f6a657f)

Ahora voy a probar que puedo acceder a la BD con el usuario de mysql.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/5891e7d9-0b94-4e0c-b2a8-441a6b06ba92)

Ahora voy a instalar phpmyadmin en mi servidor para dar una interfaz gráfica a la Base de datos.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/b604daef-5d9d-4318-8f80-c1e7456a427f)

Una vez hemos instalado phpmyadmin hay que configurarlo para que acceda a mi servidor mysql.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/fd763c91-2f1c-4f4b-af0e-e4402874b592)

Una vez hemos configurado phpmyadmin vamos a acceder al mismo desde el navegador.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/a3d6a0d7-236e-49ba-90ff-a52b5d07c909)

Vamos a comprobar si el usuario tiene permisos para modificar la base de datos, creare una tabla.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/2e70c0a0-8ca8-4d31-9ab9-38156f749e90)

Podemos ver en local (desde mi pripio servidor) que el usuario que he creado puede modificar la base de datos.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/c22a839f-baf4-4ef4-8988-d8b30c1578b3)

Ahora voy a crear una página web que mediante php muestra contenido de la base de datos que elija.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/61deae89-3e50-4f19-8eb9-7b4471e5e038)

Ahora desde el navegador voy a acceder a dicha página para ver si me muestra el contenido de la tabla.



Ahora voy a configurar mi DNS para que el cliente acceda a mi servidor a través del mismo.



Voy a instalar openssh-server para dar servicio ssh.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/4142ed65-482e-4dbb-890e-269306f49484)

Voy a abrir el puerto 22 de mi server (ssh)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/a65367e3-7963-4995-afc0-8fbc9022c828)


