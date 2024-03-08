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

Ahora voy a crear una página web que mediante php se enlaza y muestra contenido de la base de datos que elija.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/4eac5c97-64a5-4223-b473-77b8b3f77629)

Ahora desde el navegador voy a acceder a dicha página para ver si me muestra el contenido de la tabla.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/1ff166de-da7e-4a44-925d-a6510e615ca2)

Ahora voy a configurar mi DNS para que el cliente acceda a mi servidor a través del mismo.

Voy a instalar openssh-server para dar servicio ssh.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/4142ed65-482e-4dbb-890e-269306f49484)

Voy a abrir el puerto 22 de mi server (ssh)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/a65367e3-7963-4995-afc0-8fbc9022c828)

Ahora voy a hacer una conexión ssh desde mi equipo cliente usando mi usuario root.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/1e37cbeb-21c5-47d1-ae74-ca7153c55049)

Voy a crear un usuario en mi servidor para conectar los clientes por ssh.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/9247d029-97c5-4b99-81bd-15842afcd9fb)

Ahora voy a añadir al usuario al grupo sudo.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/ba09256e-6ddc-4c6c-a082-91918b29c82b)

Para darle seguridad a la conexión ssh de mi servidor, voy a crear claves ssh y compartirlas. Creo la clave.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/a3f746de-81d3-47b0-9b4f-1fa2446b0b00)

Voy a compartir la clave desde el el equipo cliente hacia servidor.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/8a38b0d1-3b51-40af-b746-d78dd99cc314)

Voy a comprobar si la clave está en el archivo authorized_keys de mi servidor.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/758b765a-d435-4749-9555-383a33436444)

Voy a deshabilitar la contraseña de acceso mediante ssh, ya que dispongo de la clave ssh. /etc/ssh/sshd.config

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/7675541d-789d-426d-87eb-e000264e811a)

Compruebo que puedo acceder mediante la clave ssh generada al servidor.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/d9ae1991-14b3-4812-a471-75b09d2fbf04)

Puedo compartir la misma clave pública con varios usuarios del servidor y autenticarte como cualquiera de esos usuarios desde tu equipo cliente.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/b7b8968e-12b3-4e2f-bbbb-5abdefa3acf0)

Voy a instalar el software bind para montar mi DNS y luego configurarlo.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/2ab89c9a-3f1e-4062-8c00-d9702a72de31)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/c8f99c67-2f01-46b6-80e6-20d9ea52a3c2)

Ahora voy a configurar mi DNS caching (caché) para mejorar la velocidad y la carga del servidor.
Para ello voy al directorio /etc/bind y modificamos el archivo named.conf.options

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/5b2fd1ef-0a4a-4d4b-9a87-89d9bc6f5743)

Ahora voy a modificar el archivo añadiendo la subred en la que están mi servidor y clientes que son de confianza para mi DNS.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/482a4faf-4a37-47f9-944a-c28bd0a7c2f0)

Ahora voy a añadir los DNS a los que hare consutlas de nombres (forwarding) añadiendo los DNS de google.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/f7798010-06df-4925-b90f-a39301e5a2a4)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/43ff40a0-7cb4-4f88-a8fc-4df2cc8c2dbd)

Antes de levantar el servicio DNS voy a comprobar que la configuracion del servidor es correcta.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/44566338-07a3-43e9-acbc-e99e3fe511a9)

(He corregido los fallos) La opcion dnssec-enable es obsoleta para bind de buntu 22.04, viene por defecto activada.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/ef5518a8-ea9c-4646-93aa-2b1732f8bb25)

Ya no hay fallos en la sintaxis en mi configuración de DNS así que voy a arrancarlo para probar si funciona.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/d086b06d-3c10-46fb-8cc1-1085f553828e)

Voy a hacer un systemctl status bind9 para ver el si esta funcionando correctamente y cómo.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/1608eebc-4549-4830-bdc3-35af1507cbbf)

Como podemos ver esta corriendo y voy a hacer un ping desde mi propio server (localhost).

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/6dbe83ee-f4e2-4e38-82ef-7eb947274f9e)

Ahora tenemos que configurar el cliente para conectarse al DNS en mi caso "rafamarisma" edito el archivo /etc/resolv.conf

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/1ba35401-fdd2-41a3-960a-db2ce3fe155a)

Voy a probar un ping a google usando el DNS.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/93ffe40a-4823-476b-9e8f-8469d4906afd)

Voy a usar dig comando de DNS en mi cliente.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/6c9df513-6177-4030-beb4-ca53de0a0700)

Si vuelvo a hacerlo el tiempo de respuesta debe ser minimo, puesto que el servidor guarda la query en la caché.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/01d76ec3-b972-4349-8b19-992ab4e6e92b)

Ahora voy a modificar el archivo de configuracion del servicio bind que lo arranca para que solo tome IPv4.
Para ello uso el comando: "sudo systemctl edit --full bind9"

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/5d0f0d6c-843c-4cc5-8c44-307249271261)

Ahora voy a reiniciar el servicio Bind.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/bd79b1d1-6df0-449c-a536-8e0c02fdb0d2)

Ahora en el servidor voy a modificar mi archivo /etc/hosts para que referencie la IP publica con el NS.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/d9fc99a7-69a8-4ba1-a41b-9f2f0f5c6277)

Ahora en el servidor voy a modificar el archivo /etc/hostname

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/021b6314-5913-48d3-ac62-e9facaf503bc)

Ahora voy a modificar el archivo named.conf.local para añadir una zona directa e inversa de mi DNS.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/68ea9a28-c4fe-4f40-abd2-a2e03ceefed4)

Ahora voy a crear un directorio zona para configurarlas, copiare la informacion por defecto de bind al mismo.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/2b1c9798-fa11-4248-9d3b-8ada3eee5bfa)

Eso lo hice para la zona directa, ahora hago lo mismo para la zona inversa.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/a86f3fc4-1470-4524-bff4-3dbbe1059c2a)

Ahora voy a modificar los ficheros de zona recién creados.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/37a165d0-2967-4f47-a106-9f638118964f)

Ahora modifico la zona inversa recién creada.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/4e5dc52e-5786-4b0c-8532-4abc14f9c411)

Voy a comprobar desde el cliente que el DNS está funcionando, hare un ping hacia el DNS

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/7b1984f3-4677-47a4-ade6-7de48109651d)

Desde el servidor puedo usar un comando para ver el estado de rndc. sudo rndc status

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/f3851451-ce39-4e34-8d24-8010f06dd584)

Mi DNS funciona, ya tengo configurado ssh previamente asi que ahora voy a comenzar a instalar FTP.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/64780d1e-8b8f-48d2-a9c3-1fd1aa6befbb)

Ahora voy a configurar el archivo "/etc/proftpd/proftpd.conf" para mi servidor.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/0232d627-ea3f-4339-a40f-0839377706a3)

Ahora voy a instalar openssl.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/e383d5ea-b458-4813-bff9-40437276f556)

Voy a probar una conexion a ftp en mi servidor.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/013c963b-0874-489d-9cc7-af270f83b7f2)

Para que mi servidor use TLS vamos al fichero de proft: "/etc/proftpd/proftpd.conf" y descomentamos una linea.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/ca563058-f80c-4752-ab16-dece0066fb81)

Ahora voy a generar certificados ssl para mi servidor.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/153833b7-4364-4ff7-837d-76b206554244)

Compruebo que se han generado y cambio los permisos de las claves generadas.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/4fe65bc6-6b4f-4210-ab3d-2d155ae08cdf)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/3418ee9c-2699-4659-8b5e-e75eeea9206a)

Ahora voy a configurar el archivo "/etc/proftpd/tls.conf".

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/fc0af316-8eeb-4876-8d65-ad3aeb35e22e)

Agora voy a reiniciar el servicio proftpd

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/cd67a1a8-53d9-442a-b631-e26355237a4e)

Ahora voy a instalar filezilla en el equipo cliente para acceder por sftp desde el mismo.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/617e1f1e-7155-4280-92e3-78f806bcb6a5)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/6b05f26a-7e6a-422f-b277-bd242ed52bd8)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/c9d05ea7-6fbe-45bc-b8ac-7472d14b7154)

Ahora comprobamos si la conexion es correcta. Puedo ver que me da la opcion de acceso TLS usando ftp.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/24944811-8f9b-48e2-a153-48023f234bed)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/6a6b629c-8254-4e60-948e-0ece64877dca)

El protocolo FTP usando TLS es seguro pero podemos mejorarlo usando SFTP.

Voy a configurar mi servidor FTP para que use SFTP en su lugar, así la conexion es segura.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/70fa403f-d2aa-43c0-8db7-41adf1e1f7f8)

Voy a comprobar con un usuario ssh si puedo acceder desde sftp.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/83ae71f6-5a83-4e17-9be4-22102e646c43)

Ahora desde filezilla en el equipo cliente probaré la conexion SFTP.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/51c8bf43-3166-4112-97df-4886b368e11f)

Introducimos la contraseña del usuario ssh.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/bc079d0f-0ac0-4144-b8f1-598e74eb85a1)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/9cd63b0d-44c8-40ec-aad6-1da23d154c58)

Y ya nos ha conectado a mi servidor (rafamarisma) desde una conexion segura sftp.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/b37ae546-e26f-4e5d-b9ee-d05e511cd69e)

Ahora voy a crear un archivo que contiene scripts (formato: .sh) que automatizen creacion de subdominios, usuarios virtuales y su directorio virtual , host virtual de apache, base de datos además de un usuario con permisos sobre la misma, usuarios ssh.
Los incluiré todos en un mismo archivo (.sh) que tendrá un menú para elegir entre las opciones.

Aqui tengo la funcion que crea el subdominio en mi DNS.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/ca1e5274-a22e-4f19-a833-72c9edbc3a2d)

Aqui esta la funcion que crea un usuario y el directorio que da servicio web.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/1887e7e1-f605-4bb8-af8e-0740380d82e6)

Aqui la esta funcion que crea una base de datos además de un usuario con todos los permisos sobre dicha base de datos.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/739970da-0306-4e41-8609-a64401f01e88)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/b462e31e-6f55-49f9-89df-34bf5e9d2814)

Aqui esta la funcion que crea un usuario del sistema para acceso a ssh.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/b549199d-b933-44ec-a0cb-68ce8275ae82)

Aqui esta la funcion de menu que hace la llamada al resto de funciones del script.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/1095d1ee-5817-4bd9-856c-12228aa67360)

Voy a ejecutar el script por partes y muestro los resultados.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/d0a9e4d8-277e-48ca-84fe-612537cff886)

Dentro del directorio db.rafamarisma1.local me crea un subdominio, en este caso "subrafamarisma".

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/bd539bd0-13d3-4410-9f44-21f6820d782d)

Ya hemos comprobado que el subdominio se crea correctamente dentro de nuestro archivo de DNS (bind).

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/5b314402-6be5-4522-8700-15f650d7b023)

Ahora voy a comprobar la creacion del usuario y del directorio para el alojamiento web.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/ca1683e0-3443-4b70-aeec-d702fd175ea7)

Voy a los virtualhost de apache2, en sites-avaiable puedo ver como se ha creado el virtualhost.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/9eb95778-e0f2-49ca-9e24-b866081c7c09)

Voy al directorio donde se ha creado la pagina web con una pagina index.html para mostrar su funcionamiento.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/b55ffced-cbe4-4043-8947-8280964a71fd)

Desde el navegador voy a comprobar si funciona correctamente.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/0c046b62-0521-4947-88ec-a0103c0baa95)

Ya he comprobado la creacion de usuario y directorio para alojamiento web.

Ahora voy a comprobar la funcion que crea una base de datos además de un usuario con todos los permisos sobre dicha base de datos

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/a75c99d6-2de6-456e-9546-200e913a2d07)



Ahora voy a comprobar que la creacion del usuario ssh es correcta usando la ultima funcion.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/c7fe93ab-03a9-4864-9254-5660ac73595d)

Voy a comprobar el acceso mediante ssh y luego si al crear otro usuario con el mismo nombre, nos lo debe impedir.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/47233623-dc73-47e5-9b56-6c4a1d6b20ec)

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/d23f1ecc-4630-4e9e-a1b2-bd1aff0b8bf4)







