# Protocolos Capa 2 y Capa 3

## ARP y RARP
    Estos protocolos actúan como un puente entre la capa de enlace y la de red.
        -ARP (Address Resolution Protocol): Se utiliza cuando un dispositivo conoce la IP de destino pero no su dirección MAC. Envía una solicitud(Request) de difusión (broadcast) preguntando quién tiene esa IP, y el dueño responde(Reply) con su MAC para completar la tabla ARP.
        -RARP (Reverse Address Resolution Protocol): Es un protocolo obsoleto que permitía a un dispositivo sin disco descubrir su propia IP a partir de su MAC. Ha sido reemplazado por DHCP.

