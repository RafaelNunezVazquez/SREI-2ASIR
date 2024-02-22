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










