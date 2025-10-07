<div align="center">
  
# Hardware Básico

</div>

---
# Indice

## Características y análisis de las necesidades informáticas  
## Arquitectura hardware de un sistema informático.
## Esquema de bloques de un sistema basado en microprocesador
## Buses del Sistema
## Elementos hardware de un sistema informático
## Componentes de la unidad central





## Características y análisis de las necesidades informáticas

· Determinar las necesidades informáticas en función de las aplicaciones y el uso.  
· Seleccionar los componenetes del equipo informático y los diferentes tipos de periféricos.  
· Determinar las necesidades software.  
· Dejar abierta la posibilidad de una ampliación posterior.  

## Arquitectura hardware de un sistema informático

Los circuitos digitales pueden realizar funciones específicas o de propósito general. En los circuitos específicos (lógica cableada) solo hay una parte hardware, mientras que los de propósito general (lógica programada) constan de una parte fija, hardware, y de otra variable, software, que indica al circuito digital la tarea a realizar. A este tipo de circuitos se les denomina microprogramables.  

Muchos sistemas microprogramables, además, añaden un pequeño software grabado en la estructura y del sistema llamado firmware. El firmware contiene un grupo de programas que sirve de intermediario entre el software y el hardware, el cual el usuario no puede alterar. En los sietemas informáticos se le llama BIOS (Basic Input/Output System).

[Imágenes](./Images_Hardware/1.png)

Todo sistema por complejo que sea, poseen una estructura, en esta se distinguen los siguientes elementos:

  **· Reloj:** es un generador de impulsos de ondas cuadradas periódicas. Se utiliza para que todo el sistema vaya en sincronía, esto es, que cada elemento funcione cuando le corresponde.  
  **· Unidad central de procesos o CPU (Central Process Unit):** es la parte más importante del sistema microprogramable. Es donde se realiza la interpretación y ejecución de las intrucciones y genera todas las funciones de control para gobernar todo el sistema. Dichas funciones se realizan en sincronía  con la señal del reloj define la velocidad del sistema. Su estructura interna es compleja y puede realizarse de las siguientes formas:

- Con un conjunto de complejos circuitos digitales cableados colocados en tarjetas de circuito impreso, que se instalan en un mismo chásis o armario.
- Todo integrado en un único circuito o chip denominado micrporcesador.El uso de dichos microprocesadores está muy extendido y son ampliamente utilizados en sistemas como ordenadores personales, controles industriales, etc.

**· Memoria central o interna:** en este elemento se encuentran los datos y programas que debe utilizar el sistema microprogramable. Existen otros tipos de memorias con las cuales no se debe confundir, denominadas memorias de masa, que forman parte de los periféricos y que se encuentran fuera del sistema.

**· Unidad de entrada/salida(Interface):** permite la comunicación del sistema microprogramable con el exterior. Su función fundamental es la de adaptar las diferentes velocidades y códigos utilizados por los elementos externos del sistema y el interior.

**· Periféricos:** es un conjunto de dispositivos que realizan un trabajo en el exterior del sistema. Estos periféricos pueden ser de entrada o salida, aunque existen algunos que realizan ambas funciones.

[Imágenes](./Images_Hardware/2.png)

## Esquema de bloques de un sistema basado en microprocesador

Los elementos esenciales que constituyen un sistema basado en microprocesador se representan en el esquema. Como se puede observar está dividido en los siguientes bloques:

**· Unidad de control (UC).**  
**· Unidad aritmética-lógica (UAL).**  
**· Acumuladores y registros.**  
**· Reloj.**  
**· Memoria central (MC).**  
**· Unidad de entradas/salidas (interface).**  
**· Periféricos.**  

[Imágenes](./Images_Hardware/3.png)

### Unidad de Control (UC)

Esta es la parte más importante del microprocesador y es la encargada de gobernar el funcionamiento global del mismo. Recibe la información, la transforma e interpreta, enviando órdenes precisas a los elementos que las requieren para un procesamiento correcto de los datos.

### Unidad Aritmética-lógica (ALU)

Es la parte operativa del microprocesador. Es la zona donde se realizan las operaciones aritméticas y lógicas ordenadas desde la unidad de control con los datos procedentes de la memoria central o contenidos en registros. Se compone de tres elementos:

**- Resgistro acumulador:** es un registro de almacenamiento temporal, donde se repositan los resultados obtenidos en las operaciones.
**- Registro de estado:** informa sobre el resultado que se obtuvo al ejecutar la última instrucción y que se tendrá que tener en cuenta en otras operaciones
**- Registro de entrada(R1 y R2):** almacenan los datos que intervienen en la operación a realizar por la ALU.

### Reloj

Para que el microprocesador genere todas las señales necesarias para controlar los restantes bloques del sistema y para que todo el sistema vaya en sincronía. A partir de esta señal de reloj, el microprocesador realiza una serie de ciclos de trabajo denominados ciclo máquina. Cada ciclo máquina representa un acceso a memoria o a un dispositivo de E/S. El número de ciclos necesarios para completar una instrucción es llamado ciclo de instrucción, dividido en dos fases:

**- Fase de búsqueda(fetch cycle):** en esta fase el micro realiza la búsqueda en memoria de una intrucción y la guarda en el registro correspondiente.
**-Fase de ejecución(executa cycle):** en esta fase el micro ejecuta o realiza la transferencia de datos ordenada.

### Memoria cental o Memoria Principal (MC)

Es la encargada del almacenamiento de los programas y de la información necesaria para el funcionamiento del sistema. Se compone de celdas o palabras de memoria, semejantes y funcionalmente diferentes. Esta dividida en dos partes:

**- RAM:** su nombre corresponde a las iniciales de Ran-dom Access Memory, que significa memoria de acceso aleatorio. Este tipo de memoria permite tanto la lectura (read) como la escritura (write). Su función en el sistema es la de almacenar los programas a ejecutar, los datos y los resultados intermedios del proceso. Se suele dividir en dos zonas denominadas:
- **Memoria de programa:** es la zona de memoria donde se almacena el programa a ejecutar.
- **Memoria de datos o de trabajo:** en esta zona se almacenan los datos del programa.

**- ROM:** su nombre corresponde a las iniciales de Read Only Memory, que significa memoria de solo lectura. Al contrario que la memoria RAM, este tipo de memoria solo permite la lectura (read). Su función en el sistema es contener los datos y programas de arranque, para que el microprocesador pueda comunicarse con el resto del sistema. En los sistemas informáticos se le denomina BIOS, porque contiene las intrucciones básicas de entrada y salida.

### Unidades de Entrada y Salida

Estas unidades consisten, generalmente, en registros que, accionados por los buses de control y direccio-nes, almacenan la información suministrada por el bus de datos. Las salidas de estos registros son accesibles desde el exterior para su conexión a cualquier dispositivo que se deba accionar.  

**Los registros de entrada**, de utilización general, son multiplexores a los cuales se conectan dispositivos exte-nores por una serie de terminales (o a „). Mediante los buses de control y de direcciones, el sistema selecciona en un instante dado cuáles de esas informaciones presentes en las entradas deben transferirse al bus de datos para su pro-ceso. En las entradas se puede introducir la información de forma automática o de forma manual, mediante ciertos dispositivos como pulsadores que, cuando se ordena, desde el resto del sistema, se introducen en los registros internos adecuados para su tratamiento.  
  
**Los registros de salida**, al igual que los de entrada, son multiplexados, cuya carga se realiza desde el interior del sistema sobre una serie de registros en los que el sistema deposita el resultado de la información ya procesada. Como se observa en la Figura 1.9, el contenido de estos registros es accesible en cualquier momento desde el exterior por una serie de terminales (O, a O,).

### Periféricos

Están formados por un amplio grupo de dispositivos, cir-cuitos, máquinas, etc.; en definitiva, todos los aparatos que, controlados por el sistema, realizan un trabajo exterior. Los periféricos se clasifican según el tipo de función que pueden realizar:  

**· Periféricos de comunicación:** la función de este tipo de periféricos consiste en enviar información desde el interior del sistema al exterior (si son dispositivos de salida) o de recibir la información desde el exterior (si se trata de dispositivos de entrada). Aunque existen periféricos que pueden realizar ambas funciones, según el sistema se lo indique. Los periféricos de comunicación más importantes son el teclado, el ratón, el monitor y la impresora.  

**· Periféricos de almacenamiento masivo:** la función de este tipo de periféricos es la de almacenar una gran cantidad de información de forma permanente y segu-ra, ya que el contenido de la memoria RAM se pierde cuando se desconecta el sistema. Existen numerosos sistemas de almacenamiento masivo, pero los más utilizados son las unidades de disco magnético y las unidades de disco óptico.

## Buses del Sistema

Los elementos principales de un sistema microprogramable van comunicados a través de canales llamados buses. Estos buses están compuestos por diferentes hilos eléctricos que transportan información del mismo tipo. El número de líneas indica el ancho del bus.

Los sistemas microprogramables se componen de tres buses fundamentales:

-**Bus de direcciones(address bus):** por este bus van a circular los bits (combinación binaria) que seleccionarán la posición de la memoria o el registro de entrada/ salida en el que se desea leer o escribir.

-**Bus de datos(data bus):** Bus de datos (data bus): por este bus circularán los bits que componen la información binaria, ya sean instrucciones o datos contenidos en la posición de memoria o en los registros de entrada/salida, seleccionada por el bus de direcciones.  

-**Bus de control(Control bus):** *  este bus está formado por una serie de líneas denominadas líneas de control, por las que va a circular el conjunto de señales necesarias para la correcta coordinación de todos los elementos del sistema, tales como: órdenes de lectura o escritura, inhabilitación (desactivación) de un dispositivo, etcétera.  

## Elementos hardware de un sistema informático

Un sistema informático tiene al menos tres partes bien diferenciadas:

-**Unidad Central:** es la encargada de controlar todos los procesos que se realizan.

-**Monitor:** es el periférico de salida más importante y permite la visualización de la información.

-**Teclado:** es el periférico de entrada más importante y permite dar las órdenes al sistema informático.

## Componentes de la unidad central

### Caja

Es la coraza en cuyo interior se alojan los demás piezas que forman la unidad central. Hay diferentes tipos de caja:

-**Minitorre:** dispone de dos bahías para unidades de 3,5"  y dos para 5,25".

-**Semitorre:** es igual al anterior pero añade una bahía más del tamaño de 5,25".

-**Sobremesa:** estas cajas se colocan en horizontal con el monitor encima. Suele disponer de una o dos bahías como mucho. Cada vez más en desuso.

-**Cubo o barebone:** caja muy reducida. Tiene escasa o ninguna posibilidad de expansión y puede tener problemas de calentamiento.

-**Rack:** es una caja especial con se atornilla a un armario o bastidor metálico que tiene una medida estandarizada, la U. Una U es la altura de una ranura del armario metálico.

-**TPV:** es una caja para terminales de venta.

-**Portátiles:** los hay de muy diversas formas, auqneu suelen tener un espesor de 1 a 4cm y su lomgitud y anchira se asemejan a un formato A4, aunque actualmente son panorámicos en su mayoría.

### Placa base

Es una placa de circuito impreso sobre la que se encuentra montada una serie de componentes electrónicos que hacen funcionar a todo el sistema informático. Su calidad influye sustancialmente en las prestaciones del equipo. Aparte de los componentes pasivos (resistencias, condensadores, etc.), pueden distinguirse una serie de elementos importantes:  

**· Un zócalo (socket)** para la instalación del microproce-sador.  

**· Slots de expansión**, una serie de conectores ranura-dos sobre los que se pinchan (conectan) las tarjetas.  

**· Un controlador de teclado**, que traduce las teclas pulsadas a los códigos adecuados para que el microprocesador pueda interpretarlos.  

**· Una serie de conectores denominados bancos**, sobre los que se monta la memoria RAM.  

**· Un grupo de chips de memoria caché**, que agiliza la transferencia de datos del microprocesador a la memoria principal (RAM) y viceversa.  

· Conectores para el teclado, ratón, puertos USB, indicadores luminosos, pulsadores, unidades de disco, et-cétera.  

**· Un pequeño chip de memoria ROM denominada BIOS**, en el que se encuentran grabadas las instrucciones de arranque del sistema y un programa de configuración del equipo denominado Setup. 

**· Un conjunto de jumpers y/o microinterruptores** que se abren o se cortocircuitan para configurar la placa, e indicar qué componentes se instalan en ella.  

**· Conector de alimentación** para suministrar la tensión adecuada de funcionamiento a todos los componentes de la placa base.

**· Puerto norte:**  es el circuito controlador del sistema y el que determina qué tipo de CPU debe usarse en la placa base. Comunica a la CPU con el resto del sistema, para lo que contiene:

- Interfaz con el bus externo del microprocesador (bus del sistema).  

-  Controlador de memoria (bus de memoria).  

- Interfaz con el sistema gráfico (bus gráfico).
  
- Interfaz con el puente sur (bus de enlace).

**· Puerto sur:** su misión básica consiste en la comunicación de la CPU con los periféricos a través de los buses de expansión, puertos, etc., para lo cual contiene:  

- Interfaz con el puente norte (bus de enlace).

- Interfaz con el bus de expansión.

- Dispositivos PCI integrados: controladora USB, controladora de discos duros y unidades ópticas, etcétera.

- Dispositivos estándar heredados: controlador de DMA, controladores de interrupciones, reloj de tiempo real, etcétera.

[Imágenes](./Images_Hardware/4.png)

### Unidades de disco

Son dispositivos de almacenamiento de gran capacidad de información de forma permanente. Existen tres tipos:

**· Magnéticos:** son dispositivos de almacenamiento de información que utilizan un soporte circular magnético protegido por una carcasa. Dicho soporte es regrabable y de acceso aleatorio; es decir, se puede leer un dato almacenado en cualquier posición del disco sin necesidad de tener que leer lo grabado anteriormente. Hay dos tipos:

  - **Disquetes:** son pequeños y el soporte magnético está protegido por una cubierta de plástico.
  - **Disco duro:** son de mayor tamaño que los disquetes y están protegidos por una carcasa metálica.

Componentes principales:

  **· Platos:** Discos metálicos recubiertos de material magnético que giran a alta velocidad (5400-15000 RPM).
  **· Cabezales de lectura/escritura:** Pequeños electroimanes que flotan sobre los platos sin tocarlos (a nanómetros de distancia).
  **· Actuador:** Brazo mecánico que mueve los cabezales con precisión.

Proceso de funcionamiento:

  **· Escritura:** El cabezal genera un campo magnético que orienta las partículas magnéticas del plato en una dirección (norte o sur), representando bits (0 o 1).
  **·Lectura:** El cabezal detecta la orientación magnética de las partículas y la convierte en señales eléctricas que el sistema interpreta como datos.

Organización del Disco Duro

La superficie de los platos se organiza en una estructura geométrica precisa:

Estructura física:
  **· Pistas (Tracks):** Círculos concéntricos donde se almacenan los datos.
  **· Sectores:** Divisiones de cada pista, típicamente de 512 bytes o 4KB.
  **· Cilindros:** Conjunto de pistas alineadas verticalmente en todos los platos.
  **· Clústeres:** Agrupación de sectores consecutivos (unidad mínima de almacenamiento del sistema operativo).

Direccionamiento:

  **· CHS (Cilindro-Cabeza-Sector):** Método antiguo de localización física.
  **·LBA (Logical Block Addressing):** Método moderno que asigna números consecutivos a los sectores.

Zonas del disco:

  **· MBR/GPT:** Tabla de particiones al inicio del disco.
  **· Particiones:** Divisiones lógicas del espacio total.
  **· Sistema de archivos:** Estructura que organiza archivos y carpetas dentro de cada partición.

  **· Ópticos:** son dispositivos de almacenamiento masivo de información de gran capacidad. Utilizan tecnología óptica.

  **· De estado sólido(SSD):** son unidades de disco compuestos por chips de memoria flash, sustituyendo a los discos magnéticos de los discos duros rígidos. 

  ### Tarjetas

  Son componentes que realizan multitud de funciones:

  **· Tarjetas gráficas de vídeo:** esta tarjeta está interconectada con el monitor y lo controla. Dispone de una memoria RAM donde se almacenan los datos de információn gráfica que deben mostrarse en la pantalla.  
 
  **· Tarjeta controladora de disco y puertos:** esta tarjeta sirve de intermediario, adaptando la información contenida en los sistemas de alamcenamiento para que el ordenador la pueda utilizar y para que pueda almacenar información en ellos.

  **· Tarjeta de sonido:** actualmente, la mayoría de placas integran chips de audio para reproducir los sonidos, pero si deseas mejorar las prestaciones o este chip se avería, se puede añadir una tarjeta de sonido que suple y mejora las prestaciones del chip de audio.

  **· Tarjeta de red:** permite la conexión a internet, la mayoría de placas base ya traen una integrada.

  ## Fuente de alimentación

  Se encargan de alimentar a todos lo elementos del sistema informático. Se conecta a la placa base en varias partes con diferentes conectores, cada línea de cables contiene cables de diferentes colores cp¡on diferentes tensiones y funciones: 

  [Imágenes](./Images_Hardware/5.png)

  

  
  

  

  










