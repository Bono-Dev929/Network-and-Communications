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

