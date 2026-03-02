# Red No Aislada/ Internet
    A diferencia de las redes aisladas, en estas se necesita un paso mas para poder enviar o recibir information, ya que con la MACAdress no es suficiente, para dirigir ese trafico hacia fuera de la red aislada se necesita un dispositivo de capa 3, de red, un router, que sepa como y hacia donde debe enviar la information conectando varias redes aisladas dejando de estar tan aisladas

## IP Internet Protocol
    Este protocolo se encarga de direccionar el trafico entre redes distintas desde el host de origen hasta el de destino. 
    Actualmente conviven IPV4 e IPV6 cada uno se compone de varios octetos binarios, 4 y 8 respectivamente, estos octetos forman la direccion que permite identificar la red y el dispositivo especifico.
    Se usa una mascara de red para determinar si el destino es local o remoto haciendo una operacion AND entre la direction y la mascara (IPV4)

## Direccionamiento IP
    El sistema de direccionamiento ip nació de proyectos militares y universitarios en los 70 para garantizar la distribución de información.
    Se planificaron 4000 millones de direcciones IP, pero el crecimiento de dispositivos forzó el desarrollo de IPV6 que eleva exponencialmente la capacidad que tenia IPV4 de 2 elevado 32 a 2 elevado 128.