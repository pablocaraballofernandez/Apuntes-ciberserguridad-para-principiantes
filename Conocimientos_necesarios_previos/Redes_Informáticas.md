<div align="center">
  
# Redes Informáticas

<p align="center">
  <img src="https://img.shields.io/badge/Redes-Informáticas-0078D7?style=for-the-badge&logo=cisco" />
  <img src="https://img.shields.io/badge/Protocolos-TCP/IP-orange?style=for-the-badge&logo=wireshark" />
  <img src="https://img.shields.io/badge/Modelo-OSI-blueviolet?style=for-the-badge&logo=internetexplorer" />
  <img src="https://img.shields.io/badge/Nivel-Estudiante-yellow?style=for-the-badge&logo=graduation-cap" />
</p>

</div> 

# Indice  

## · Redes de datos  

## · Tipos de redes de datos  

## · Modelos en capa


## Redes de datos  

Las redes de datos surgen ante la necesidad de comunicar y compartir información entre usuarios. Una red de datos informática mantiene los beneficios del ordenador personal (software propio, información personal, etc.), pero añadiendo la posibilidad de compartir recursos software y hardware con otros usuarios, lo que aporta unas enormes ventajas:  

**· Recursos compartidos:** los equipos conectados a una red pueden compartir determinados componentes como impresoras, unidades de discos, etcétera.
  
**· Dispositivos de protección de datos:** se puede programar la realización de copias de seguridad, por ejemplo, de todos los discos duros de la red.
  
**· Posibilidad de acceder a un soporte de datos com-partidos:** los usuarios pueden disponer de una base de datos común.
  
**· Procesamiento distribuido:** se puede repartir una tarea entre varios equipos, obteniendo una mayor potencia.
  
**· Alternativas de comunicación:** los usuarios pueden comunicarse con otros a través de aplicaciones informáticas específicas, por ejemplo mediante correo electrónico, videoconferencia, etcétera.
  
**· Capacidad de ampliación:** las redes de datos permiten una rápida expansión y es muy fácil añadir elementos nuevos,

### Elementos

Para que la comunicación sea posible, se necesita un elemento que realice la transmisión (trans-misor) y otro que reciba los datos enviados (receptor) a través de un medio (canal de transmisión).

![Imágenes](Images_Redes/1.png)

El **transmisor** es el elemento del sistema encargado de generar y preparar la información de forma adecuada para que viaje por el canal de transmisión.

El **receptor** es el elemento encargado de recuperar la información del canal (demodulación o decodificación) e interpretarla.

El **canal** de transmisión es el medio utilizado para hacer llegar la información. La transmisión se realiza habitualmente empleando ondas electromagnéticas que se propagan a través del canal. El canal de transmisión puede ser guiado o no. Un medio guiado es aquel compuesto por un material físico sólido encargado de llevar la señal de información por su interior, por ejemplo, un cable. Sin embar-go, en un medio no guiado, el canal es el aire y tanto la transmisión como la recepción de información se realizan mediante antenas o mediante emisores y sensores ópticos.  

Un sistema de comunicaciones puede verse afectado por **contaminantes** que modifican la señal transportada sobre el medio de transmisión. Estos contaminantes producen que el mensaje recibido no sea exactamente igual al transmitido. Estos contaminantes son imposibles de eliminar, por tanto, un objetivo de los sistemas de comunicaciones es reducir su incidencia.  

## Topologías y estructura  

Una red de datos está compuesta por equipos que están conectados entre sí mediante líneas de comunicación (cables de red, etc.) y elementos de hardware (adaptadores de red y otros equipos que garantizan que los datos viajen correctamente).
La configuración física, es decir, la configuración espacial de la red, se denomina topología física. El objetivo de cada topología es encontrar la forma más económica y eficaz de comunicar los equipos. Dependiendo de cómo se conecten los quipos entre sí, da lugar a varios tipos de configuraciones:  

**· Topología de bus (Ethernet):** en esta configuración, todos los equipos (ordenadores, impresoras, etc.) tienen una dirección diferente y están unidos en la red local por una única línea denominada bus, que suele ser un cable coaxial. Cuando un equipo envía un mensaje, indica la dirección del equipo al que va dirigido. El mensaje al entrar en la red llega a todos los equipos, de forma que los que no tienen la dirección especificada por el mensaje ignoran su contenido y el que tiene la dirección especificada lee la información contenida. La capacidad de la red va decreciendo a medida que aumenta el número de equipos conectados. El fallo de un equipo no interrumpe el funcionamiento de la red, pero el fallo en el cable hace que la red deje de funcionar.

![Imágenes](Images_Redes/2.png)

**· Topología en anillo (Token-Ring):**  en esta topología todos los equipos están conectados a la red en forma de lazo. Cuando un equipo envía un mensaje, indica la dirección del equipo al que va dirigido. El mensaje entra en la red y empieza a recorrer todo el anillo, de forma que los equipos que no tienen la dirección especificada por el mensaje ignoran su contenido y el que tiene la dirección especificada lee la información contenida. La ventaja de esta configuración con la anterior consiste en que si se rompe la red por un punto, los mensajes siguen llegando al resto de los equipos de la red.

![Imágenes](Images_Redes/3.png)

**· Topología de estrella (Ethernet):** en esta configuración, todos los equipos están conectados por líneas separadas que van al mismo nodo o estación central. La función de esta estación central consiste en conectar las líneas con cualquiera de las otras. Cuando un equipo envía un mensaje, indica la dirección del equipo al que va dirigido. El mensaje, al llegar a la estación central, es dirigido a la línea que conecta con el equipo que tiene la dirección del mensaje. Para evitar que algunos equipos monopolicen la red, la estación central concede una porción de tiempo a cada una de las líneas de la red cuando hay enviándose varios mensajes.

![Imágenes](Images_Redes/4.png)

**· Topología de árbol:** es una generalización del tipo bus. Tiene su primer equipo en la raíz (cabecera) y se expande hacia fuera utilizando ramas, en donde se conectan los demás equipos. Esta topología permite que la red se expanda y, al mismo tiempo, asegura que nada más existe una ruta de datos entre dos equipos cualesquiera. Esta configuración suele utilizarse en redes grandes.  

![Imágenes](Images_Redes/5.png)

**· Topología de malla:** es una combinación de más de una topología, como podría ser una bus combinada con una estrella. Este tipo de topología es común en lugares en donde tenían una red de bus y luego la fueron expandiendo en estrella. Son complicadas para detectar una avería por parte del servicio técnico. La ventaja de esta red es que permite garantizar la comunicación entre equipos porque dada su complejidad siempre existen varios caminos posibles.

![Imágenes](Images_Redes/6.png)

### Internet

Internet es una red de redes de alcance mundial que permite la interconexión descentralizada de redes de datos utilizando el protocolo TCP/IP.

El desarrollo de internet ha superado ampliamente cualquier previsión y ha constituido una verdadera revolución en la sociedad moderna.

Una buena red de contactos es fundamental en los negocios y, aprovechando la conectividad que brinda internet, nace el servicio Networking. El Networking está basado en una red de contactos profesionales que permite dar a conocer un negocio, escuchar y aprender de los demás, econtrar posibles colaboradores, socios o inversores. 

## Tipos de redes de datos

Las redes de datos pueden clasificarse atendiendo a diversos criterios. La más común es con relación al tamaño de la red (área de distribución), pudiéndose encontrar los siguientes tipos:  

### LAN o Red de área local  

Su extensión está limitada físicamente a un edificio o como mucho a edificios contiguos. Es una red privada para conectar ordenadores personales y estaciones de trabajo en oficinas, fábricas, etcétera.  

### WLAN o Red de área local inalámbrica  

Es una red de área local sin cables, utiliza tecnologías de radiofrecuencia que permiten mayor movilidad al minimizar las conexiones cableadas. Se utiliza como alternativa a la red LAN o como extensión de estas con un alcance aproximado de 100 metros. Existen varios tipos de tecnologías:  

**· Wi-Fi o estándar IEEE 802.11:** es una tecnología de comunicación inalámbrica con el respaldo de WECA
(Wireless Ethernet Compatibility Alliance). Es el estándar más extendido para la creación de redes WLAN.
Actualmente hay seis versiones importantes:
- **802.11a**, hasta 54 Mb/s en la banda de 5 GHz.
- **802.11b**, hasta 11 Mb/s en la banda de 2,4 GHz.
- **802.11g**, hasta 54 Mb/s en la banda de 2,4 GHz.
- **802.11n**, hasta 300 Mb/s en la banda de 2,4 GHz.
- **802.11ac**, hasta 1 Gb/s en la banda de 5 GHz.
- **802.11ad**, hasta 7,2 Gb/s en las bandas de 2,4 GHz, 5 GHz y 60 GHz.

**· HiperLAN (High Performance Radio LAN):** es un estándar europeo desarrollado por ETSI (European Telecommunications Standards Institute). Su última versión, la HiperLAN2, permite a los usuarios alcanzar una velocidad máxima de 54 Mb/s en un área aproximada de 100 metros.

### MAN o Red de área metropolitana  

Esta red es una versión más grande de una LAN que cubre ciudades enteras y, normalmente, se basa en una tecnología similar. La principal razón para distinguir las MAN como una categoría especial es que se ha adoptado un estándar para ellas, DQDB (Distributed-Queue Dual-Bus) o bus dual de cola distribuida, para asegurar una alta velocidad.  

### WAN o Red de área extensa  

Engloba todas las redes de datos que cubren un área geográfica extensa. Normalmente, una WAN está compuesta por un grupo de LAN conectadas a través de enlaces, ya sean cableados o inalámbricos. Un ejemplo de este tipo de redes sería RedIRIS, internet o cualquier red en la cual no estén en un mismo edificio todos sus miembros.  

## Modelos en capa  

La comunicación entre dos equipos conectados a una red de datos es un proceso complejo. Por tanto, el estudio y el desarrollo de estas redes es una tarea complicada. Para facilitarla, se emplean estrategias modulares, que dividen el problema complejo en partes más simples. Cada parte se encarga de realizar, de manera transparente para las demás, una determinada función dentro del proceso de comunica-ción. De este modo, cada parte del proceso se despreocupa del resto y únicamente se encarga de las tareas de su nivel o capa. Así, esta idea de dividir en partes el proceso de comunicación desemboca en un modelo en capas.  

El modelo en capas es jerárquico, esto es, las capas se sitúan una encima de otra, por lo que es posible distinguir entre capa superior y capa inferior. Una capa únicamente atenderá a las peticiones de la capa inmediatamente superior y solo pedirá tareas a la capa inmediatamente inferior. Cada capa se encargará de llevar a cabo la tarea solicitada de manera transparente para el resto de las capas.

![Imágenes](Images_Redes/6.png)

### Modelo OSI

El modelo OSI (Open System Interconnection) fue creado por la Organización internacional de normalización (ISO, International Standardization Organization) en 1984 como un marco de referencia para la definición de arquitectura de interconexión de sistemas de comunicaciones.  

El modelo de referencia OSI está formado por siete capas o niveles (Figura 4.22) que definen las diferentes fases por las que deben pasar los datos para viajar de un dispositivo a otro sobre una red de comunicaciones de datos. A continuación se describe la función de cada una de estas capas:  

**· Capa física:** es la encargada de transformar las tramas en señales eléctricas. Define el medio físico por el que van a viajar los datos, el tipo de cable, los materiales, las especificaciones eléctricas, etcétera.  

**· Capa de enlace de datos:** se ocupa del direcciona-miento, la topología de la red, el acceso al medio, la detección de errores, la distribución ordenada de tramas y del control del flujo, esto es, que los mensajes lleguen sin errores, independientemente de la tecnología de transmisión física empleada.  

**· Capa de red:** se encarga de establecer la ruta que llevarán los datos hasta su receptor final. Su objetivo es hacer que los datos lleguen desde el origen al destino, aun cuando ambos no estén conectados directamente.  

**· Capa de transporte:** efectúa la transferencia de los datos del origen al destino, ofreciendo mecanismos de seguridad e independientemente del tipo de red física que se esté utilizando.  

**· Capa de sesión:** se encarga de sincronizar el envío de información, mantener y controlar el enlace creado entre dos equipos, estableciendo la conversación, los turnos de palabra, el intercambio de datos, etc. Esta capa es quien libera la memoria cuando se están enviando datos.  

**· Capa de presentación:** su tarea es la representación de la información. De modo que, aunque los equipos tengan diferentes representaciones internas de ca-racteres, los datos lleguen de manera reconocible. En esta capa se tratan aspectos tales como la semántica y la sintaxis de los datos transmitidos, ya que distintos equipos pueden tener diferentes formas de manejarlas.
Por tanto, podría decirse que esta capa actúa como un traductor. Esta capa también permite cifrar los datos y comprimirlos.  

**· Capa de aplicación:** ofrece a las aplicaciones la posibilidad de acceder a los servicios de las demás capas y define los protocolos que utilizan las aplicaciones para intercambiar datos. Es importante aclarar que el usua-rio, normalmente, no interactúa directamente con el nivel de aplicación. Suele interactuar con programas que a su vez interactúan con el nivel de aplicación.  

![Imágenes](https://www.stackscale.com/wp-content/uploads/2023/04/OSI-modelo-capas-ataques-Stackscale.jpg)


![Imágenes](Images_Redes/7.png)

### Modelo TCP/IP

El modelo TCP/IP (Transmission Control Protocol/Inter-net Protocol) es el modelo más empleado para la interconexión de sistemas. Nace en la década de los setenta en una agencia del Departamento de Defensa de los Estados Unidos (DoD) para la red ARPANET.  

Este modelo describe un conjunto de reglas generales para permitir que cualquier equipo pueda comunicarse en una red, por lo que se ha convertido en un estándar de internet. TCP/IP especifica cómo deben ser tratados los datos, direccionados, transmitidos, enrutados y recibidos. TCP/IP no es un modelo de referencia como OSI, sino que describe y define todas las tareas del proceso de comunicación.  

El modelo TCP/IP, al igual que el OSI, organiza todas las tareas en capas, de manera que las entidades de una capa ofrecen servicios a las entidades de la capa superior. A diferencia del modelo OSI, TCP/IP solo tiene cuatro capas o niveles de abstracción:  

**· Capa de acceso a la red:** define las características del medio de transmisión y las características físicas de la transmisión como tipo de señal, velocidad de transmi-sión, etc. Además, realiza la traducción de las direcciones de nivel de red (IP) a direcciones físicas, generando las tramas de datos a enviar. Asimilable a la capa de enlace de datos y a la capa física del modelo OSI.  

**· Capa de internet:** define el camino a seguir por los datos desde el origen hasta el destino. Cuando dos equipos están conectados a redes diferentes y desean intercambiar datos, es necesario determinar un camino para transportarlos, atravesando en ocasiones distintas redes. Asimilable a la capa de red del modelo OSI.

**· Capa de transporte:** también denominada extremo a extremo (host to host). Proporciona un servicio de transferencia de datos garantizado entre sistemas fina-les, ocultando detalles de la red. Existen dos tipos de protocolos de este nivel, atendiendo al tipo de servicio ofrecido, orientado a la conexión (TCP) o no orientado a la conexión (UDP). El protocolo UDP (User Da-tagram Protocol) permite el envío de datos sin que se haya establecido previamente una conexión y proporciona un nivel de transporte no fiable. Mientras que el protocolo TCP proporciona un envío fiable, a costa de añadir más información en los datos. Asimilable a la capa de transporte del modelo OSI.  

**· Capa de aplicación:** permite la comunicación entre aplicaciones de equipos remotos. Maneja aspectos de representación, codificación y control de diálogo. Asimilable a la capa de sesión, de presentación y de aplicación del modelo OSI.

<div align="center">

![Imágenes](https://www.textoscientificos.com/imagenes/redes/tcp-ip-osi.gif)

</div>

### Protocolos de resolución de direcciones (ARP)  

El protocolo de resolución de direcciones (Address Resolution Protocol) es un protocolo de la capa de internet de gran importancia. Este protocolo permite que se conozca la dirección física de una tarjeta de red correspondiente a una dirección IP.  

Cada dispositivo conectado a la red tiene un número de identificación de 48 bits. Este número es único y se establece en el momento de fabricación de la tarjeta. Sin embargo, la comunicación en internet no utiliza directamente este número, puesto que implicaría que las direcciones de los dispositivos deberían cambiarse cada vez que se reemplaza la tarjeta de red. Por ello, se utiliza una dirección lógica (dirección IP) asignada por un organismo llamado ICANN (Internet Corporation for Assigned Names and Numbers).  

Para conocer la correspondencia entre las direcciones físicas con las direcciones lógicas, el protocolo ARP interroga a los dispositivos de la red y crea una tabla en una memoria caché llamada tabla ARP. De este modo, cuando un dispositivo debe comunicarse con otro, consulta la tabla ARP. Si la dirección requerida no se encuentra en la tabla, el protocolo ARP envía una solicitud a la red (ARP-REQUEST). Todos los dispositivos de la red comparan esta dirección lógica con la suya. Si alguno de ellos se identifica con esta dirección, el dispositivo responderá al ARP (ARP-REPLY) y se almacenarán los datos en la tabla ARP. A continuación, podrá establecerse la comunicación. Sin em-bargo, no es muy recomendable mantener esta información para siempre, ya que las tarjetas de red de los dispositivos pueden haber sido reemplazadas. Por este motivo, las entradas en la caché ARP son desechadas cada cierto tiempo para forzar otra búsqueda de la dirección IP.  

A veces, también, es necesario encontrar la dirección IP asociada a una dirección física. En este caso, el protocolo que resuelve el problema es el RARP (Reverse Address Resolution Protocol). El protocolo RARP se usa esencialmente en estaciones de trabajo sin disco duro que al arrancar necesitan conocer su dirección IP. Para ello envía una petición RARP a un servidor de direcciones que, a partir de la dirección física, consulta su base de datos para obtener la dirección IP correspondiente, y le responde indicándosela.  

![Imágenes](https://www.manageengine.com/latam/oputils/images/Address-resolution-protocol-tech-page-creatives-01.png)
