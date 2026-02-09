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

## Framing o Encapsulado de tramas:
    Este proceso es mediante el que se separan, los datos a enviar, en tramas, que son unidades mas pequeñas de information, para poder ser transmitidos por el medio fisico.
    Una trama se compone de:
        -Una cabezera, compuesta por el preambulo, las direcciones MAC de origen y destino y tipo;
        -Datos;
        -Secuencia de verificacion.
    Sirve para delimitar donde inicia y termina cada unidad de datos, para favorecer la deteccion de errores(con CRC) y ayuda a la sincronizacion entre emisor y receptor.
    Composition detallada de una trama:
        -Preambulo + SFD: sincronización
        -MACs: direcciones físicas
        -Tipo: indica el protocolo de capa superior
        -Datos: Cualquier cosa que pertenezca a capas superiores
        -FCS: verificación de errores.
        -Gap entre frames: El gap de final de trama son 12 bytes vacíos con el objetivo de espaciado entre tramas.

## Direcciones MAC:
    Estas direcciones son un identificador unico asignados a las NIC, usados por la subcapa MAC en la capa de enlace para reconocer interfacez y permitir la comunicacion local.
    Se compone de 48 en 6 bloques hexadecimales, algunos dispositivos pueden tener mas de una direction
        -Los primero 24 corresponden al fabricante y los otros 24 al equipo.
    Respecto a su uso, no todos los protocolos de comunicacion las usan y no todos requieren identificadores globales.

## Segmentacion
    Esta concepto conciste en dividir la red en segmentos mas pequeños para evitar congestion en el trafico de red y reducir coliciones a través de switches.
    Cada segmento functiona como un medio compartido, por ende como un dominio de colicion particular donde los dispositivos conectados se comunican entre si y comparten ancho de banda y los datos que quieren ir a otro segmento lo hacen a traves de un puente
    Caracteristicas de Segmentacion:
        -Los puentes almacenan y luego envían tramas, basándose en las direcciones de Capa 2.
        -Es independiente del protocolo de Capa 3.
        -Aumenta la latencia en la red.
        -Un switch es un bridge con más puertos.

## Bridging y Switching
    Estos conceptos parten de la segmentacion, llamados asi por los dispositivos usados para realizar dichas segmentaciones, sus propositions siguen siendo segmentar una red para reducir trafico.
        -Bridge o puente: conecta dos o mas redes permitiendo comunicacion entre dispositivos que lo necesiten, es antiguo, tiene pocos puertos y filtra por MAC Address.
        -Switch: Es la evolucion del bridge, tiene muchos puertos, filtra por tablea MAC, y es de conmutacion rapida, cada puerto es un dominio de colicion.

