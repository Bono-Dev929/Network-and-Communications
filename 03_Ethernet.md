# Ethernet

## Que es:
    Es un conjunto de protocolos de capa 2, el mas utilizado en el mundo para comunicar dispositivos, no es solo un cable
    
## Control de Acceso al Medio(MAC):
    Se establece que en un medio compartido, como un cable donde todos escuchan, los dispositivos conectados que quieran transmitir, primero deben verificar que el medio no este siendo utilizado. 
    Cada uno de los host compara la señalización electrica del medio para saber si se esta transmitiendo o no, Al encontrar el medio ocupado cada uno espera un tiempo random hasta volver a enviar pero hasta un máximo de 16 intentos, si esos intentos fallan, el host avisa a capas superiores que no se pudo enviar la trama.
    En redes modernas armadas con swicht esto ya no se usa dado que son punto a punto y no se generan coliciones. En medios guiados no quedan medios compartidos, esto se aplica principalmente en medios no guiados con el protocolo CSMA/CA.

## Solt Time
    Este concepto se refiere al tiempo minimo que tiene una NIC para detectar una colicion por ende comprobar si el medio esta ocupado o no. Este tiempo equivale lo que tarde una trama en ir y volver desde su origen hasta el punto mas lejano de la red.
    Si no hay colicion la trama sigue siendo enviada pero en caso de encontrarse con una colicion la NIC interrumpe el envio de la trama por completo, antes de silenciarse envia un JAM signal, que sirve para que los demas host detecten la colicion y nadie crea que esa trama fue valida. El fragmento de trama que se envio queda corrupto y no se recupera, solo se descarta y se reinicia el proceso.
    Para retransmitir, la NIC espera un minimo tiempo de ranura para permitir que cualquier otro pulso que se alla enviado antes llegue a la NIC en espera, provocando una colicion local evitando una colicion tardia lo que permite al protocolo de CSMA/CD recuperar la situacion y retransmitir mas tarde.


