# security-architecture
Aquitectura de seguridad de la red 









Prerequisitos: 

- Una Máquina ubuntu 20.04 LTS o debian entre 4gb y 7gb de RAM 
- Tener Instalado los prerequisitos de [Hyperledger Fabric](https://hyperledger-fabric.readthedocs.io/en/release-2.2/prereqs.html)
- [Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04-es) y [Docker compose](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04-es)
- go en su version [1.13 o 1.14](https://golang.org/dl/)



#1) Paso 1: Crear Instacia con los requerimientos de fabric.


1.1: En la consola GCP vaya a la página de compute engine especificamente el de [Instancias VM](https://console.cloud.google.com/compute/instances?hl=es-419&_ga=2.261880845.-1491417428.1579698808&_gac=1.48926292.1579702038.CjwKCAiAgqDxBRBTEiwA59eEN1_hwlITQhlBjDKLQut5LrtKDmWF6BN315v8BgLH2BnBrndm4tf6ZRoCsF8QAvD_BwE)

1.2: Haz clic en Crear instancia



1.3: En la Sección de la configuracion de la máquina, seleccione como serie la estandar y como tipo de maquina deje los valores como estan.




1.4:En la sección Disco de arranque, haz clic en Cambiar para comenzar a configurar el disco de arranque



1.5: En la pestaña Imágenes eliga la imagen de maquina que escoja la que diga Ubuntu de alli escoja la que diga , Por último  en la parte que dice tipo de disco de arranque seleccione tipo persistente y coloquele el tamaño que quiera aunque se recomienda 30gb minimo.


1.6: Haz clic en Seleccionar.

1.7: En la seccion identidad y acceso a las apis en la parte que dice Alcance del acceso elija la opcion de permitir el acceso completo a todas las API de Cloud.

![](https://files.slack.com/files-pri/T23DATAB1-FSL5XE69G/image.png)

1.8: En la sección de  Administración, seguridad, discos, redes, único propietario, escoga lo siguiente:

Administraccion:

Política de disponibilidad: aceptar.

Redes: 

- etiquetas de red: fabric-health (es una etiqueta que hace una referencia a una regla cortafuegos creada que permite el acceso a los sistemas de chequeo de estado de google.)




En la parte de abajo de click en crear.

* Advertencia: esto puede tomar un corto período de tiempo para que la instancia se inicie. Una vez listo, se incluirá en la página Instancias de máquina virtual con un icono de estado verde.

1.9: Si quiere desactivar la maquina puede apagarla o borrarla, esto es para cuando no la este usando ya que google cobra por uso es decir mientras este activada el facturara.

1.9.1: para apagarla de click en un cuadrado al lado del nombre de la instancia, y luego en el panel de arriba dele click en detener.

![](https://files.slack.com/files-tmb/T23DATAB1-FSNUZLY0Z-7e15f086e7/image_720.png)

1.9.2: Para borrarla es el mismo procedimiento anterior solo que en vez de darle en detener le damos en el de borrar.

![](https://files.slack.com/files-pri/T23DATAB1-FT118PJB1/image.png)

 * Advertencia: esto tarda unos minutos.

 y listo ya no tiene que preocuparse por la facturacion.

1.9.3 Si quiere activarla de nuevo, realize el mismo procedimiento anterior, pero ahora como la maquina esta pausada (ya que si esta eliminada tendra que crearla de nuevo) tiene que darle al icono de activar.

![](https://files.slack.com/files-tmb/T23DATAB1-FSLC0T38A-b610d3c2e8/image_720.png)

Advertencia: es posible que cada vez que pause y reeactive una vm si direccion ip cambie recuerde esto.
