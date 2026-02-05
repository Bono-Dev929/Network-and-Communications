# Arquitectura de Capas

## Modelo de capas
    Conciste en dividir un problema complejo en partes, estas partes son llamadas CAPAS. Este modelo permite un funcionamiento modular de una red.

## Modelo Hibrido (OSi + TCP/IP)
    El primer modelo de capas fue el modelo OSI que constaba de 7 capas luego surgio el modelo TCP/IP con 4. A menudo se suele usar una combination de ambos: el modelo OSI para las capas bajas y el TCP/IP para las capas altas

## Las cinco capas Modelo Hibrido
### Capa fisica:
    Se encarga de bits, señales, cables, todos los componentes fisicos que componen una red, aspectos electricos, mecanicos, mantener los dispositivos conectados fisicamente es decir sus cables, conectores, voltaje.

### Capa Enlace:
    Maneja tramas(Encapsulamientos), direcciones MAC, Ethernet. Su funcion principal es garantizar la comunicacion entre dispositivos conectados de manera segura y confiable. Se subdivide en MAC y LLC

### Capa Red:
    Se encarga de enrutar paquetes de datos desde origen hasta destino, es decir de guiar los conjuntos de datos desde su origen hacia el destino, ademas se encarga de IP(direccionamiento), encapsulacion, fragmentacion y deteccion de errores.

### Capa de transporte:
    se encarga de entregar los datos de un extremo a otro de manera confiable segun protocolo, se asegura que los datos lleguen completos correctos y ordenados. Protocolos como TCP/UDP y puertos.

### Capa Aplicacion:
    Esta capa proporciona interfaces y protocolos para que las aplicaciones de usuario se comuniquen a travez de la red, como HTTP/S, DNS, SMTP, etc.

## Protocolos por capa:
### Capa 2:
    Ethernet (IEEE 802.3): El más común en redes LAN por cable. Define tramas, direcciones MAC, acceso al medio (CSMA/CD).
    Wi-Fi (IEEE 802.11):Equivalente inalámbrico de Ethernet. Incluye control de acceso al medio (CSMA/CA).
    PPP (Point-to-Point Protocol): Utilizado en conexiones seriales (por ejemplo, antiguas líneas telefónicas, túneles VPN).
    MAC (Media Access Control): Subcapa que regula quién puede transmitir en un medio compartido (parte de Ethernet y Wi-Fi).

### Capo 3:
    IP (Internet Protocol): v4 y v6, el protocolo base.
    ICMP (Internet Control Message Protocol): Usado para diagnósticos como ping.
    ARP (Address Resolution Protocol): Traduce direcciones IP a MAC (aunque opera entre capa 2 y 3).

### Capa 4
    TCP (Transmission Control Protocol): Confiable, orientado a conexión (usa handshake, números de secuencia, retransmisiones). Este Protocolo de comunicación por Internet permite conectar dos dispositivos y enviar datos entre ellos.
    UDP (User Datagram Protocol): No confiable, sin conexión, más rápido y liviano, útil para streaming o DNS. Tiene como función principal ofrecer un método rápido y simple para enviar datos entre aplicaciones a través de la red, sin establecer una conexión previa ni garantizar que los datos lleguen correctamente.
    Handshake: Cuando el TCP verifica ambos dispositivos antes de permitir más comunicaciones

### Capa 5:
    HTTP/HTTPS – navegación web
    SMTP, POP3, IMAP – correo electrónico
    FTP, SFTP – transferencia de archivos
    DNS – resolución de nombres de dominio
    DHCP – asignación automática de direcciones IP
    SNMP – monitoreo de redes
