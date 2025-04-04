### Ejercicio 2: La Ciudad de las Redes Aisladas

Este proyecto recrea la antigua red de la ciudad segmentada mediante VLANs, con un router central que permite la comunicación entre gremios de forma controlada.

Diagrama:

![image](https://github.com/user-attachments/assets/d03c6243-7aef-4816-84af-708159f2df74)


Red:
- Una gran torre central que consiste del router y un switch configurado en modo trunk que se conecta a otros dos switches.
- El primer switch fuera de la torre central es el gremio de arquitectos o la vlan 5 con 4 puertos configurados como access mode para los ordenadores.
- Un segundo switch fuera de la torre central es el gremio de carpinteros o la vlan 10 con otros 4 puertos configurados como access mode para los ordenadores


**Direcciones de las vlans**
|Vlan |Red|Gateway |Broadcast |
|-----|---|--------|----------|
|5|192.168.1.0/24 |192.168.1.1|192.168.1.255|
|10|192.168.2.0/24 |192.168.2.1|192.168.2.255|


**Configuracion del router**

Para que el router sea capaz de cambiar entre subredes/vlans se crean dos sub-interfaces del puerto 0/0/0 que esta conectado al switch central.

- Se crea una primera sub-interfaz 0/0/0.5 para que el router se puede conectar a la primera subred/vlan-5 con la ip de la gateway = 192.168.1.1
- Se crea una segunda sub-interfaz del 0/0/0.10 para que el router se pueda conectar a la segunda subred/vlan-10 con la ip del gateway = 192.168.2.1

Una vez configurado esto, como el switch central se encuentra en mode trunk el router ya esta comunicando las vlans siempre que toddo este bien hecho las dos vlans podran ya comunicarse.

**Pruebas de red:**

![image](https://github.com/user-attachments/assets/d068f030-b012-4b93-8f04-6311fa2dffcf)


En la captura se ve al PC0 que esta en la subred-1/vlan-5 haciendo un ping a la subred-2/vlan-10 y recibiendo una respuesta demostrando que la red funciona.
