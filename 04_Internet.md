# Red No Aislada/ Internet
    A diferencia de las redes aisladas, en estas se necesita un paso mas para poder enviar o recibir information, ya que con la MACAdress no es suficiente, para dirigir ese trafico hacia fuera de la red aislada se necesita un dispositivo de capa 3, de red, un router, que sepa como y hacia donde debe enviar la information conectando varias redes aisladas dejando de estar tan aisladas

## IP Internet Protocol
    Este protocolo se encarga de direccionar el trafico entre redes distintas desde el host de origen hasta el de destino. 
    Actualmente conviven IPV4 e IPV6 cada uno se compone de varios octetos binarios, 4 y 8 respectivamente, estos octetos forman la direccion que permite identificar la red y el dispositivo especifico.
    Se usa una mascara de red para determinar si el destino es local o remoto haciendo una operacion AND entre la direction y la mascara (IPV4)

## Direccionamiento IP
    El sistema de direccionamiento ip nació de proyectos militares y universitarios en los 70 para garantizar la distribución de información.
    Se planificaron 4000 millones de direcciones IP, pero el crecimiento de dispositivos forzó el desarrollo de IPV6 que eleva exponencialmente la capacidad que tenia IPV4 de 2 elevado 32 a 2 elevado 128.

## Tipos de direccionamiento
### Class & Classless: 
    Tradicionalmente, las redes se dividían en clases según su primer octeto:
        Clase A (0-127): Máscara /8, para redes con millones de hosts.
        Clase B (128-191): Máscara /16, permite hasta 65,534 hosts por red.
        Clase C (192-223): Máscara /24, ideal para redes pequeñas de hasta 254 hosts.
        Clase D y E: Reservadas para Multicast e investigación respectivamente.
    
### Direcciones Públicas o Privadas:
    Públicas: Son visibles y ruteables en todo el internet.
    Privadas: Se usan internamente en hogares u oficinas y no se publican directamente a internet.
    Los rangos definidos por la IANA incluyen el 10.x.x.x, 172.16.x.x a 172.31.x.x, y el 192.168.x.x.

## Trama IP(V4)
    Un paquete IP (Datagrama) consta de un encabezado de 20 a 60 bytes y el resto datos. 
    El encabezado incluye campos criticos como:
        - TTL (Time to Live): Un contador que disminuye en cada router para evitar que los paquetes circulen indefinidamente.
        - Protocolo: Indica si el contenido es TCP, UDP, etc.
        - Checksum: Para detectar si la cabecera se dañó en tránsito.
        - Direcciones IP: Tanto de origen como de destino.

## Gestion de redes (SubNeting y SuperNeting)
    -Subneteo: Consiste en dividir una red grande en subredes más pequeñas "robando" bits a la porción de host para asignarlos a la red. Esto permite un mejor aprovechamiento de las direcciones y mayor control del tráfico.
    Superneteo: Conciste en combinar o juntar redes pequeñas en una mas grande para simplificar la tabla de enrutamiento, se hace reduciendo los bits asignados a red.

