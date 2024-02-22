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







