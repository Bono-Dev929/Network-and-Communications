# Ethernet

## Que es:
    Es un conjunto de protocolos de capa 2, el mas utilizado en el mundo para comunicar dispositivos, no es solo un cable
    
## Control de Acceso al Medio(MAC):
    Se establece que en un medio compartido, como un cable donde todos escuchan, los dispositivos conectados que quieran transmitir, primero deben verificar que el medio no este siendo utilizado. 
    Cada uno de los host compara la señalización electrica del medio para saber si se esta transmitiendo o no, Al encontrar el medio ocupado cada uno espera un tiempo random hasta volver a enviar pero hasta un máximo de 16 intentos, si esos intentos fallan, el host avisa a capas superiores que no se pudo enviar la trama.
    En redes modernas armadas con swicht esto ya no se usa dado que son punto a punto y no se generan coliciones. En medios guiados no quedan medios compartidos, esto se aplica principalmente en medios no guiados con el protocolo CSMA/CA.



