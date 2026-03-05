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

## Puerto access y trunk
    Antes de definir estos tipos de puerto hay que dejar 2 cosas claras:
        -Transparencia: los dispositivos finales(de usuario) no entienden de estandar 802.1q, estos solo operan con tramas normales o estandar, osea sin etiquetas;
        -Desconocimiento: los dispositivos no saben a que Vlan pertenecen ni cuales existen, si no que el switch es el encargado de decidir por el dispositivo.
    
### Access Port
    Es el puerto del switch donde se conectan los dispositivos finales, tecnicamente es un modo de puerto, es decir para un puerto donde se conecta un dispositivo final como una pc se configura para que sea tipo access.

    Mecanismo de funcionamiento:
        -Trama Entrante (del PC al Switch): El switch recibe la trama normal y le asigna el tag 802.1Q correspondiente a la VLAN configurada en ese puerto.

        -Trama Saliente (del Switch al PC): El switch identifica el tag de la trama, verifica que el puerto pertenece a esa VLAN y extrae (quita) el tag antes de enviarla al dispositivo.   

### Trunk Port
    Estos puertos estan diseñados para conectar dispositivos de red entre si, que manejan varias Vlans, al igual que la definition de access port, nos referimos al modo trunk una configuration asignada al puerto que queramos.
    Características principales:
        -Multiplexación: Transporta tráfico de varias VLANs simultáneamente por un solo cable.
        -Identificación: Utiliza etiquetas 802.1Q para que el dispositivo del otro extremo sepa a qué VLAN pertenece cada trama.
        -Esencialidad: Es el requisito para que exista comunicación entre diferentes dispositivos de red sin mezclar el tráfico.

#### Vlan Default y Vlan Nativa
    Vlan Default: Es la Vlan que viene configurada de manera estandar en todos los dispositivos de red asignada a todos los puertos disponibles, es decir es el estado base de todo equipo.
    A esta Vlan no se la puede borrar ni cambiar el ID, la funcion principal es habilitar el switch desde el principio

    Vlan Nativa: Esta Vlan por default, viene configurada junto con la default, es la misma, la Vlan 1, pero su proposition es totalmente distinto.
    Esta Vlan se encarga de manejar o resivir las tramas que viajan por enlaces trunk sin una etiqueta 802.1q, esta falta de etiqueta puede darse por varias rasones. Al venir configurada junto con la Vlan default se suele cambiar el nombre, numero e VID para separarla del resto de Vlans y manejar ese trafico sin etiquetar de manera eficiente.

    Las razones por las cuales una trama puede no tener etiqueta 802.1q son varias:
        -Dispositivos antiguos: las tramas que vienen de dispositivos antiguos suelen no tener incuidos algunos protocolos como el 802.1q y por lo tanto no etiquetan tramas. La Vlan nativa garantiza la compatibilidad entre estos dispositivos y los nuevos.
        -Ataques: Un atacante puede enviar tramas sin tag para acceder a la Vlan nativea y de ahi intentar acceder a las otras Vlans de la empresa y a sus datos.

## Vlan de datos/acceso
    Estos terminos en la practica son tomados como uno solo pero en definition son diferentes:
        -Vlan de datos: esta es la Vlan que nosotros creamos para segmentar el trefico que circula, donde asignamos un numero y nombre en representation de los datos que se vana enviar, EJ: Vlan 10 administracion.
        - Vlan de acceso: Hace referencia al estado del puerto (Modo Access). Su función es recibir tramas sin etiqueta de un dispositivo final y entregárselas también "limpias", actuando como el puente entre el mundo sin VLANs (el PC) y el mundo etiquetado (el Switch).