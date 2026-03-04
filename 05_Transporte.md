# Transporte
    La capa de transporte se encarga de llevar los datos o information de un extremo al otro, osea de host a host, realizando la comunicacion sin importar el medio fisico por el que esten conectados.
    Esando la multiplexacion para distintos procesos de nivel aplicacion

## Multiplexación
    La multiplexacion es una tecnica de comparticion de recursos que permite el aprovechamiento total de un medio. 
    En redes, en la capa de transporte, la multiplexacion se encarga de aprovechar al máximo el medio físico por el cual viajan los datos, enviando datos o tramas cada vez que es posible, como una cinta transportadora enviando partes de autos mezcladas a ensamblar, cada parte tiene una etiqueta que al llegar al final es ensamblada con sus compañeras. Garantizando que el medio siempre este en uso.

## Multiplexacion UDP
    Uno de los servicios que ofrece la capa de transporte es no orientado a conexión, este servicio es UDP:
        -Envía los datos directamente sin necesidad de establecer una conexión.
        -No garantiza la entrega ni el orden; si un paquete se pierde, no se reenvía.
        -Al no tener comprobaciones, la latencia es mínima, osea es mucho mas rapido.
        se suele usar para: Streaming de video, VoIP, Videojuegos online, consultas DNS.
    Su cabecera consta de solo 8 bytes y posee una pseudo-cabecera que se usa para calcular el codigo de error, checksum, esta cabecera incluye information de IP para verificar que el datagrama llego al destino correcto antes de ser procesado, es decir verificar que llego al puerto o host correcto. Como el repartidor de pizza que verifica que sea el domicilio correcto antes de que entregar la pizza.

## Multiplexacion TCP
    El otro servicio de capa de transporte es TCP, a diferencia de UDP este es orientado a conexion, es decir:
        -Necesita establecer una conexion entre emisor y receptor antes de enviar datos;
        -Garantiza que todos los datos lleguen correctos y en orden;
        -Evita que el emisor sature al receptor;
        Usado para Web (HTTP), Email (SMTP), Transferencia de archivos (FTP).
    TCP requiere varias capas de verificacion o seguridad para funcionar, su cabecera tiene 20 bytes, y posee una pseudo-cabecera de 12 bytes, usada para calcular el checksum.
    TCP ejecuta un three-way-handshake, un saludo de tres vias o una verification, como en una llamada telefonica de pedido el cliente llama y pregunta si se comunico con la pizzeria, la pizzeria responde que si y el cliente ordena, y por cada orden(paquete) se necesita una confirmation y luego un orden de segmentos y control de flujo, el orden de segmentos es que lleguen en orden en caso de la pizza que primero se haga la masa y luego se pongan los ingredientes y el control de flujo es que si hablo demaciado rapido el receptor puede no escuchar asi que TCP regula eso tambien.

## Modelo Cliente-Servidor
    En este modelo, el intercambio de datagramas ocurre entre un proceso que solicita un servicio (cliente) y uno que lo ofrece (servidor).
        -La comunicación se identifica mediante sockets, que son la combinación de una dirección IP y un número de puerto (ej. 10.0.1.25:13).
        -El servidor suele estar en un estado de escucha en un puerto "bien conocido", esperando peticiones de los clientes.
    
## Mas sobre TCP:
    TCP permite múltiples conexiones simultáneas en un mismo host. Para que dos conexiones sean distintas, deben diferir en al menos uno de los cuatro valores: IP origen, puerto origen, IP destino o puerto destino.
    Se destaca la flexibilidad del sistema operativo para manejar interfaces:
        -NICs múltiples: Un servidor puede tener varias tarjetas de red físicas o virtuales, cada una con su propia IP.
        -IP Alias: Es posible asignar varias direcciones IP a una sola interfaz física para que el servidor escuche en distintas direcciones.

### Conexion y desconexion
    TCP utiliza un proceso formal para iniciar y terminar la comunicación.
    -Flags de Conexión/Desconexión: 
        Utiliza bits específicos (flags) en la cabecera, como SYN (sincronizar) para iniciar, ACK (acuse de recibo) para confirmar y FIN para terminar.
    -Identificadores de Conexión: 
        Cada extremo elige un ISN (Initial Sequence Number) aleatorio para evitar confusiones con paquetes de conexiones anteriores. También se negocia el MSS (Maximum Segment Size), que es el tamaño máximo de datos que cada host puede recibir en un segmento.

