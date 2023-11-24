<h1>Proyecto 1º Trimestre Servidor Web.</h1>

Para empezar este proyecto empezaré con un Ubuntu limpio recién instalado.
Haré un sudo apt update para actualizar los paquetes del S.O.

![1](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/9a070caa-6002-4f57-94e8-72239565b843)

Ahora voy a instalar apache2 con el comando apt isntall apache2.

![2](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/24ff2ad3-d60a-4d32-af2f-a7f2a8b975c0)

Vamos a comprobar que el firewall del S.O. permite las conexiones a internet. Usaremos el comando ufw app list.

![image](https://github.com/RafaelNunezVazquez/SREI-2ASIR/assets/91255999/349f9043-4c48-4063-adc7-fb4f86df880e)

Mediante el comando: ufw app info "Apache Full" vamos a comrpobar la información que tenemos de apache2 en nuestro S.O.(puertos que usa,etc)

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




