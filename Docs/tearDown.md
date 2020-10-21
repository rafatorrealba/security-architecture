 
# Borra el balanceador de cargas:
 
* Ve a la página Balanceo de cargas en Google Cloud Console.
     
* [Ir a la página Balanceo de cargas](https://console.cloud.google.com/networking/loadbalancing/add?_ga=2.14810614.1577132522.1603220388-459450626.1601906451&_gac=1.90551400.1603290227.Cj0KCQjwuL_8BRCXARIsAGiC51BdtPExmWw2X24PAqMjlvrRMdOr96slsvmu_BVtttXqJlonboVFsRgaAta4EALw_wcB)
 
* Selecciona la casilla de verificación junto al nombre de tu balancer.
 
* Haz clic en el botón Borrar en la parte superior de la página.
 
* Selecciona las casillas de verificación junto a todos los recursos adicionales, incluidos los servicios de backend, las verificaciones de estado y los certificados SSL.
 
* Haz clic en Borrar el balanceador de cargas y los recursos seleccionados.
 
 
# Borra los grupos de instancias no administrados:
 
* Ve a la página Grupos de instancias en Google Cloud Console.
 
* [Ir a la página Grupos de instancias](https://console.cloud.google.com/compute/instanceGroups?hl=es-419&_ga=2.142774517.1577132522.1603220388-459450626.1601906451&_gac=1.90682856.1603290227.Cj0KCQjwuL_8BRCXARIsAGiC51BdtPExmWw2X24PAqMjlvrRMdOr96slsvmu_BVtttXqJlonboVFsRgaAta4EALw_wcB)
 
* Selecciona la casilla de verificación en la parte superior junto a Nombre para seleccionar todos los grupos de instancias.
 
* Haz clic en Borrar para quitar los grupos. Los grupos se quitan, pero las VM de los grupos no se borran.
 
# Zona DNS:
 
* Ve a la página Zonas de Cloud DNS en Cloud Console.
 
* [Ir a la página Zonas de DNS](https://console.cloud.google.com/networking/dns/zones/?hl=es&_ga=2.15376246.1577132522.1603220388-459450626.1601906451&_gac=1.84277611.1603290227.Cj0KCQjwuL_8BRCXARIsAGiC51BdtPExmWw2X24PAqMjlvrRMdOr96slsvmu_BVtttXqJlonboVFsRgaAta4EALw_wcB)
 
* En la página Zonas de Cloud DNS, haz clic en el nombre de la zona, por ejemplo, my-new-zone, para acceder a la página Detalles de la zona.
 
* Seleccione los registros A y CNAME que creaste.
 
* Haz clic en Borrar conjuntos de registros.
 
* Para borrar la zona, haz clic en el ícono de borrar delete correspondiente al nombre de la zona my-new-zone.
 
* Por último en AWS borra los servidores de nombres que colocaste y coloca los que tenía por defecto y habilita el bloqueo de transferencia.
