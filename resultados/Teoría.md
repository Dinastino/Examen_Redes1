## Parte 1: Conceptos y Teoría



### El mural de siete capas

Te adentras en la sala principal del templo y descubres un gran mural compuesto por siete franjas horizontales superpuestas, decoradas con símbolos y jeroglíficos. Cada franja representa un nivel diferente en un ritual de comunicación. Los sabios de esta civilización entendían que un mensaje debía pasar por varias etapas desde su origen hasta su destino, refinándose o traduciendo su forma en cada nivel de la pirámide comunicativa.

- *Pregunta:*  ¿Qué representa el mural de las siete capas en términos de las redes de comunicación modernas? Identifica brevemente cada capa y explica cómo se relaciona este antiguo “modelo” con el proceso de comunicación de datos actual.

#### Respuesta:

Las siete inscripciones en el gran mural del templo se refieren a un antiguo sistema de comunicación, cada franja representa una de las siete capas del antiguo sistema, el modelo OSI, cada una con su propia función. La **primera** franja o capa fisica se encargaba de la transmision de bits y interfaces mecánicas y eléctricas/ópticas, su **segunda** franja o capa de enlace de datos convierte el medio de transmisión en uno puro sin errores y divide los datos en tramas, su **tercera** franja o capa de red se encarga del rutado de de paquetes de origen a destino, de evitar la congestión y de asegurar la calidad, su **cuarta** franja o capa de transporte abstrae a las capas superiores de los cambios tecnológicos que puedan sufrirse en las capas inferiores (físico, enlace y red), divide los datos de capas superiores para adaptarlos a la red, su **quinta** franja o capa de sesion permite a usuarios de diferentes maquinas establecer sesiones entre ellos, la **sexta** franja o capa de presentación se ocupa de la sintaxis y semántica de la información para poder comunicar nodos con diferentes representaciones de datos, y por ultimo su **septima franja** o capa aplicación que contiene los protocolos que los usuarios usaban con frecuencia.


Nosotros no utilizamos este antiguo modelo OSI sino uno mas moderno llamado TCP/IP que consite de cuatro capas en vez de siete congregando la capa fisica y de enlace de datos del OSI en la capa link, la capa de red se trasnforma en la capa de internet, la de transporte sigue siendo la de trasporte y las ultimas tres capas del OSI se convierten en la capa de aplicaión de TCP/IP.

Este antiguo modelo tiene similitudes con el nuestro como el uso de una pila de protocolos independientes y una capa de trasnporte sin embargo estos dos modelos también tienen grandes diferencias:
- La mas grande de las diferencias es el numero de capas, el OSI tiene siete y el TCP/IP solo tiene 4.
- El modelo TCP/IP no distingue claramente entre servicio, interfaz y protocolo, lo que puede dificultar su implementación desde el punto de vista de la ingeniería del software.
- OSI, en su diseño original, no contemplaba redes de difusión, ya que su capa de enlace se enfocaba únicamente en conexiones punto a punto.
- OSI solo permite comunicación orientada a conexión en la capa de transporte, mientras que TCP/IP permite tanto orientada a conexión como no orientada.
- OSI tiende a repetir funciones como el direccionamiento, control de flujo y detección de errores en varias capas, lo cual reduce su eficiencia.
- Y otra de las mas grandes diferencias es que el antiguo modelo esta orientado mas a la teoría mientras que el TCP/IP esta orientado a la realidad y es mas facil de implementar.

![image](https://github.com/user-attachments/assets/9c471063-e041-4c70-8d01-69ac0b7f0273)


--- 
### Los dos pergaminos del mensajero

En una cámara oculta encuentras dos pergaminos polvorientos. El primero describe el Ritual del Mensajero Confiable: antes de entregar un mensaje, el mensajero realiza un saludo de tres pasos con el receptor para asegurarse de que ambos estén listos, luego entrega el mensaje y espera una confirmación de recibido. Si la confirmación no llega, reintenta el envío. El segundo pergamino narra el Ritual del Mensajero Veloz: un mensajero que sale disparado a entregar mensajes sucesivos sin aviso previo ni asegurarse de la recepción, cubriendo la mayor distancia en el menor tiempo, aunque a veces los mensajes se pierdan en el camino.


- *Pregunta*: Interpreta los dos rituales descritos. ¿A qué protocolos de comunicación actuales equivalen el mensajero confiable y el mensajero veloz? Compara sus características, explicando las ventajas y desventajas de cada enfoque en redes modernas.

#### Respuesta

Los dos pergaminos se refieren a dos protocolos : TCP y UDP. El mensajero confiable corresponde a TCP y a los tres saludos que se hacen al iniciar una conexión TCP, el mensaje de inicio, la confirmación de ese mensaje y la confirmación de conexión, garantiza la entrega ordenada de los mensajes, solicita confirmación de recepción y reintenta si hay pérdidas. En cambio, el mensajero veloz representa a UDP, un protocolo que envía mensajes sin verificación previa ni confirmación, priorizando la velocidad sobre la fiabilidad aunque se pierdan mensajes por el camino. Mientras TCP es ideal para aplicaciones que requieren precisión y seguridad dado que se asegura de que todos los datos lleguen sin errores puede causar sobrecarga al renviar los paquetes varias veces y es menos rapido debido a la constante confimacion, UDP es preferible en situaciones donde la rapidez es crucial y se puede tolerar la pérdida de algunos datos dado que es muy rapido y tiene baja latencia pero no tiene ningun metodo de confirmacion y si se quisiese comprobar la fiabilidad se debe de hacer en la aplicación.

![image](https://github.com/user-attachments/assets/bc5fc344-65cb-4e5e-b486-c8001d3cc8a3)


--- 

### La Encrucijada de las Rutas
Llegas a una encrucijada dentro de las ruinas: cuatro caminos diferentes se extienden hacia distintas aldeas en los alrededores de la ciudad antigua. En el centro, un tótem tallado muestra flechas apuntando hacia cada camino, con inscripciones de destinos y distancias. Notas que algunas flechas parecen fijas e inmutables (talladas en la piedra), mientras que otras son piezas móviles que pudieron reorientarse si se abría o cerraba algún camino en el pasado. Este tótem se asemeja a un antiguo dispositivo de enrutamiento que dirigía el tráfico de datos por el camino adecuado.

*Pregunta:* ¿Qué concepto moderno de redes representa el tótem con flechas de la encrucijada? Explica qué es una tabla de enrutamiento y cómo funciona en un router actual. Además, interpreta la diferencia entre las flechas talladas en piedra y las flechas móviles en términos de enrutamiento estático vs. enrutamiento dinámico en redes.



#### Respuesta:

El enigma de la losa representa una antigua red 192.168.50.0 dividida en 4 sub redes, para cada una de estas subredes se tiene que dividir la red original 192.168.50-192.168.50.255 en 4 subredes cada una con su rango de host,gateway y dirección de broadcast. Imaginemos que la antigua red se dividia en un router central conectado a cuatro switches para cada uno de los gremios:
- La primera subred seria:
    - Dirección de subred: 192.168.50.0/26.
    - Default gateway: 192.168.50.1.
    - Dirección de broadcast: 192.168.50.63.
    - Rango de host: 192.168.50.2 - 192.168.50.62.
    - Mascara de red: 255.255.255.192
- La segunda subred:
    - Dirección de subred: 192.168.50.64/26.
    - Default gateway: 192.168.50.65.
    - Dirección de broadcast: 192.168.50.127.
    - Rango de host: 192.168.50.66 - 192.168.50.126.
    - Mascara de red: 255.255.255.192
- La tercera subred:
    - Dirección de subred: 192.168.50.128/26.
    - Default gateway: 192.168.50.129.
    - Dirección de broadcast: 192.168.50.191.
    - Rango de host: 192.168.50.130 - 192.168.50.190.
    - Mascara de red: 255.255.255.192
- La cuarta subred:
    - Dirección de subred: 192.168.50.192/26.
    - Default gateway: 192.168.50.193.
    - Dirección de broadcast: 192.168.50.255.
    - Rango de host: 192.168.50.193 - 192.168.50.254.
    - Mascara de red: 255.255.255.192

    ![image](https://github.com/user-attachments/assets/a094da7c-19a9-410d-9b8b-18fc8315997d)


**Calculo de la mascara**


Se necesita dividir la mascara para cuatro subredes de igual tamaño para ello se necesitan 2 bits extra tomados del campo de host $2^{2}=4$. La red original tiene una máscara de 24 bits (/24), por lo que al sumar esos 2 bits obtenemos una nueva máscara de /26. Esto equivale a 255.255.255.192 que se muestra:  
1. /26 significa que los primeros 26 de la mascara son 1 y los ultimos 6 son 0 que en binario sería: 11111111.11111111.11111111.11000000.
2. Si se separa esa mascara por byte sería: 11111111 -> 255 . 11111111 -> 255 . 11111111 -> 255 . 11000000 -> ?
3. Entonces se calcula ese ultimo byte: $2^{7} + 2^{6} = 128 + 64 = 192$ por lo que la mascara de red se confirma como 255.255.255.192.



---

### La Encrucijada de las Rutas
Llegas a una encrucijada dentro de las ruinas: cuatro caminos diferentes se extienden hacia distintas aldeas en los alrededores de la ciudad antigua. En el centro, un tótem tallado muestra flechas apuntando hacia cada camino, con inscripciones de destinos y distancias. Notas que algunas flechas parecen fijas e inmutables (talladas en la piedra), mientras que otras son piezas móviles que pudieron reorientarse si se abría o cerraba algún camino en el pasado. Este tótem se asemeja a un antiguo dispositivo de enrutamiento que dirigía el tráfico de datos por el camino adecuado.

*Pregunta:* ¿Qué concepto moderno de redes representa el tótem con flechas de la encrucijada? Explica qué es una tabla de enrutamiento y cómo funciona en un router actual. Además, interpreta la diferencia entre las flechas talladas en piedra y las flechas móviles en términos de enrutamiento estático vs. enrutamiento dinámico en redes.

-
#### Resolución:

El totem que conecta las antiguas aldeas podria identificarse como un router o una tabla de entrutamiento. Dispositivos utilizados para determinar por qué camino debe enviar los paquetes de datos según su destino un mecanismo ensencial para asegurar que la información llegue a donde tiene que llegar.

![image](https://github.com/user-attachments/assets/706bb88c-0468-4c90-92ce-bd5c60bb42d5)


La tabla de enrutamiento es una parte esencial del router, son estructuras que almacenan informacion sobre rutas hacia otras redes, es decir, almacena la forma de llegar de una red a otra. Las tablas normalmente incluyen la red objetivo, su mascara, y la puerta de enlace o "next hop" que es el camino para llegar. También pueden almacenar la distancia o el costo de la ruta. La tabla se utiliza para comprobar rutas, cuando el paquete llega al router este compara la dirreción destino con las dirrecciones de su tabla para escojer el camino mas adecuado lo que serian las flechas indicando como ir a cada aldea. Los dos tipos de flechas representan los dos tipos de rutados que existen las flechas de piedra representa una camino estático y que siempre lleva al mismo sitio pero si uno de los caminos  ha colapsado despues de tantos años esa señal no se puede adaptar y continuara apuntando a una ruta inservible, las flechas moviles representan el rutado dinamico mas flexible y capaz de cambiar si uno de los caminos se cerraba o fallaba o se abria uno mas rapido.

![image](https://github.com/user-attachments/assets/66f82e54-7704-4a14-b3d4-26cdbdd525df)


---

### El Guardián de la Máscara Única
En la última sala del templo, frente a la salida, te encuentras con la estatua de un guardián con dos caras. Según una leyenda grabada en la base, este guardián protegía la ciudad oculta de los forasteros. Cuando un mensajero salía de la ciudad, el guardián reemplazaba su máscara por la suya propia, de modo que, para el mundo exterior, todos los mensajes parecían venir únicamente del guardián. Al regresar la respuesta, el guardián recordaba qué máscara original correspondía a cada mensaje y reenviaba la respuesta al habitante correcto dentro de la ciudad. Gracias a este ardid, la ciudad pudo ocultar la identidad de sus miembros y usar un único rostro para todas sus comunicaciones externas.

*Pregunta:* ¿Qué técnica de redes moderna se refleja en la leyenda del Guardián de la Máscara? Nombra y describe brevemente este mecanismo, explicando cómo permite que múltiples dispositivos internos de una red compartan una única identidad (dirección) al comunicarse con el exterior, y menciona dos beneficios que brinda esta estrategia a las redes actuales.


#### Respuesta:

La leyenda del guardian se refiere al protocolo NAT una técnica que permite que multiples dispositios dentro de una red privada se comuniquen con el esterior con un unico identificador. Funciona de forma que cuando un dispositivo de la red interna envia un paquete al exterior el guardian(Un dispositivo NAT como un router) cambia la mascara(La ip interna) por la suya propia(La ip externa) ademas se acuerda de quien es el dueño original de esa mascara(Que dispositivo envio el paquete) y cuando vuelva ese mensajero se le devolvera la mascara indicada, esto permite que toda la red parezca una sola identidad en el exterior ocultando la verdadera identidad del mensajero. Esta tecnica tiene sus beneficios como el ahorro de identidades publicas evitando la saturacion dado que multiples personas pueden tener la misma identidad para el exterior, y también aumentaba la seguridad dado que no se puede acceder a alguien en especifico desde el exterior evitando ataque o contactos no deseados.

![image](https://github.com/user-attachments/assets/61fccda1-b7f9-4d01-b1b1-cd01ae560a02)


