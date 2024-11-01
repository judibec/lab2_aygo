# Lab 02 AYGO
## Arquitectura
Se crea una maquina virtual EC2 en la cual se crean 3 usuarios diferentes y asi lograr crear 3 instancias con el mismo backend, como ambas estan en la misma ec2, comparten la ip por lo tanto pueden compartir el hashmap con los mensajes

![arq_jgroups drawio](https://github.com/user-attachments/assets/3bf1b9c9-74c6-4674-afda-0bd0076b6dee)

## Explicación
Creamos 2 usuarios extra aparte del ec2-user que es el que se crea por defecto, con el comando `sudo useradd <nombre_usuario>` despues de esto antes de entrar a la instancia elegimos el usuario que vamos a usar como mostramos en la imagen 
![image](https://github.com/user-attachments/assets/40641aa9-9ede-4e76-a099-dbbee5ebae43)

En la parte de abajo vemos que esta la opcion de cambiar el usuario de la ec2

Para el despliegue se debe tener en cuenta instalar maven y git en las maquinas `sudo yum install git` y `sudo yum install maven` este 2do comando instala por defecto una version de java para poder ejecutar el codigo, estos comandos son usados para linux

Luego de clonar el repositorio con `git clone <url del repo>` entramos a la carpeta root y ejecutamos el aplicativo con el comando de maven `mvn exec:java -D exec.mainClass="<ruta.de.la.clase.main>"`

Ya deberia estar corriendo el chat esperando que el usuario escriba

## Evidencias
Vemos como se crean los 3 usuarios, instanciando la maquina 3 veces

![image](https://github.com/user-attachments/assets/4195b8c5-171a-45d2-9fc9-a03ce9185d0b)
![image](https://github.com/user-attachments/assets/e7617a82-ed26-4443-b1e6-fca038324d55)
![image](https://github.com/user-attachments/assets/0001fe8a-4ae3-486a-adf4-77688ef9a7d1)

Luego de esto hacemos el `mvn clean install` parandonos en el root del repo 

![image](https://github.com/user-attachments/assets/17409b30-fc83-472b-9ff5-c7bba128f714)

Ya luego corremos el comando de exec que se menciono anteriormente y vemos como las instancias se comunican

![image](https://github.com/user-attachments/assets/ee98c17c-8956-4ec3-ba4b-a9ab8c962679)

![image](https://github.com/user-attachments/assets/9f652dbe-4b16-468c-a079-b97cd05fb25b)


![image](https://github.com/user-attachments/assets/a27ab0cd-750a-4551-9a73-96b6afca5bf0)


## Video
https://youtu.be/ptzJ5PEiKIU
