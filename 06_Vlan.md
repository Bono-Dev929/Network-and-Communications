# Vlans
    Una Vlan o Virtual LAN es una red logica que permite agrupar dispositivos dentro de una misma red permitiendo su cominicacion como si se tratara de una red aislada pero dentro de otra red local, impidiendo que quienes no pertenecen a dicha Vlan no puedan acceder a pesar de estar fisicamente en el mismo lugar o conectadas al mismo switch.
    Para poder realizar comunicaciones entre Vlans es necesario y obligatorio que la information pase a traves del router, y este se encarga de permitir su paso o no.

### Asignación
    Las dos aproximaciones más habituales para la asignación de miembros de una VLAN son las siguientes:
        • VLAN estáticas
        • VLAN dinámicas
    Las VLAN estáticas también se denominan VLAN basadas en el puerto. Las
    asignaciones en una VLAN estática se crean mediante la asignación de los
    puertos de un switch o conmutador a dicha VLAN. Cuando un dispositivo entra en la red, automáticamente asume su pertenencia a la VLAN a la que ha sido asignado el puerto. Si el usuario cambia de puerto de entrada y necesita acceder ala misma VLAN, el administrador de la red debe cambiar manualmente la asignación a la VLAN del nuevo puerto de conexión en el switch.
    En las VLAN dinámicas, el administrador de la red puede asignar los puertos que pertenecen a una VLAN de manera automática basándose en información tal como la dirección MAC del dispositivo que se conecta al puerto o el nombre de usuario utilizado para acceder al dispositivo. En este procedimiento, el dispositivo que accede a la red, hace una consulta a la base de datos de miembros de la VLAN.

## Estandar 802.1q IEEE
    Para que los switches identifiquen a qué VLAN pertenece una trama, se añade una "etiqueta" (tag) al encabezado Ethernet original. Esta etiqueta incluye el VID (VLAN Identifier), que permite definir hasta 4094 redes distintas.

