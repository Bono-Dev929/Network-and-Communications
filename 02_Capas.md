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