# 1) Crear un grupo de instancias no administrado.


* En Cloud Console, ve a la página Grupos de instancias.

[](https://console.cloud.google.com/compute/instanceGroups/list?authuser=0&project=guminator&instanceGroupsTablesize=50)

* Haz clic en Crear un grupo de instancias.

![Crear](images/G2.png)



* Haz clic en Grupo de instancias no administrado nuevo.
 
 

* Ingresa un nombre para el grupo de instancias no administrado.


* En agregar un puerto selecciona el puerto 443 o el p y como nombre pon http.

* En Ubicación, selecciona una región y una zona.

* Selecciona una Red y una Subred.

* En Instancias de VM, selecciona las VM que desees agregar a este grupo en este caso agrega la que correrá en nuestra aplicación.

# Ejemplo:

![](images/G3.png)


Haz clic en Crear.
---

# 2) Conectarse a la instancia

- En GCP Console, ve a la página Instancias de VM.

- En la lista de instancias de máquinas virtuales, haz clic en SSH en la fila de la instancia a la que deseas conectarte.



![Botón SSH junto al nombre de la instancia.](https://cloud.google.com/docs/images/establish-ssh-connection-1.png?hl=es-419)

- Ahora tienes una ventana de la terminal para interactuar con tu instancia de Linux.

- Para desconectarse simplemente cierra la ventana del ssh.

- Para este este caso primero crea otra vm siguiendo los pasos anteriores y una vez creada conectate a esta

- Esto se debe  a que más adelante aislamos la instancia en la que correrá la aplicación, de manera que la única forma que le lleguemos totalmente sea a través de una conexión interna dentro de la misma red.

- Esta vm la llamaremos host bastión, y será nuestra forma de ingresar a la vm para levantar la red, una vez en en el host bastion nos conectaremos a la instancia que correrá la aplicación la cual llamaremos backend a través de la ip interna:



```
gcloud compute ssh [nombre de la vm] --internal-ip --zone=us-central1-a
```
Una vez listo  estaremos conectados.


# 3) Conexión a Cloud NAT:

A pesar que nuestra solución no tiene ip externa, es necesario que esta pueda conectarse a internet de forma segura, ya que la mayoría de las funciones, envían mensajes a un nodo de iota que se encuentra en la red.

Para realizar esto se usa un servicio llamado Cloud NAT  donde puedes aprovisionar instancias que no tengan direcciones IP públicas, para que así puedan acceder a Internet de forma controlada y eficiente para hacer distintas operaciones, como aplicar actualizaciones y parches o gestionar la configuración, entre otras. 

Los recursos externos no pueden acceder directamente a ninguna de las instancias privadas ubicadas tras la pasarela de Cloud NAT, lo que contribuye a que tus redes privadas virtuales (VPC) de Google Cloud permanezcan aisladas y protegidas.


En nuestro caso usamos una configuración básica de  Cloud NAT:





* En Google Cloud Console, ve a la página de Cloud Nat.

* [Ir a la página de Cloud NAT](https://console.cloud.google.com/net-services/nat/list?hl=es&_ga=2.10075125.1577132522.1603220388-459450626.1601906451)

* Haz clic en Comenzar o Crear la puerta de enlace NAT.

* Ingresa un Nombre de puerta de enlace.

* Elige una red de VPC la de nosotros es la default.

* Configura la Región para la puerta de enlace NAT, en este caso debe ser la misma que usa la máquina con la aplicación .

* Selecciona o crea un Cloud Router en la región y dale el nombre que prefieras.

* Haz clic en Registro, puertos mínimos, tiempo de espera para abrir esa sección.

* En la sección Stackdriver Logging, selecciona Traducción y errores. Esto envía todos los registros a Cloud Logging.

* Haz clic en Crear.

* Espera un rato y verifica si en la máquina sin ip externa puedes realizarle una actualización.

* Si es así el NAT está habilitado.



