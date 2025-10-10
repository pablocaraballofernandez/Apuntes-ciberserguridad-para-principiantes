<div align="center">
  
# Sistemas Operativos

<p align="center">
  <img src="https://img.shields.io/badge/Sistemas-Operativos-0078D6?style=for-the-badge&logo=windows" />
  <img src="https://img.shields.io/badge/Linux-Kernel-black?style=for-the-badge&logo=linux" />
  <img src="https://img.shields.io/badge/Procesos-y%20Memoria-orange?style=for-the-badge&logo=gnubash" />
  <img src="https://img.shields.io/badge/Aprendizaje-Actívo-success?style=for-the-badge&logo=bookstack" />
  <img src="https://img.shields.io/badge/Nivel-Estudiante-yellow?style=for-the-badge&logo=graduation-cap" />
</p>

</div>

  
Un sistema operativo es un conjunto de programas básicos que permiten manejar, organizar y optimizar los ficheros de datos y programas de las unidades de disco del sistema informático. Los ordenadores no pueden funcionar sin un sistema operativo, aunque cuenten con los mejores programas del mercado, o el mejor hardware del momento. De hecho, se podría encender, pero no valdría de mucho, no podría pedir que se introdujera comando alguno y mucho menos darle una orden.

En realidad, lo primero que realiza el sistema informático al arrancar (entre otras cosas) es cargar de una unidad de disco los ficheros del sistema y ejecutarlos. Tras unos instantes, el ordenador está preparado para empezar a ejecutar el programa o las órdenes que se le indique.

![Imágenes](Images_OS/1.png)

Existen una gran variedad de sistemas operativos, con diferentes características, que ofrecen una serie de ventajas e inconvenientes dependiendo del ordenador o el entorno donde se utilicen: UNIX, Linux, Windows, VMS, Solaris, etc. Sin embargo, actualmente el sistema operativo más extendido es Windows.  

La misión principal del sistema operativo es hacer de intérprete entre el usuario que está delante del teclado y el hardware del ordenador. Además de interpretar los comandos que permiten al usuario comunicarse con el ordenador, el sistema operativo realiza las siguientes funciones:  

**· Gestión de recursos:** coordina y manipula el hardware del sistema informático, como la memoria, las impresoras, las unidades de disco, el teclado o el ratón. En un ordenador actual suelen coexistir varios programas, del mismo o de varios usuarios, ejecutándose simultáneamente. Estos programas compiten por los recursos del ordenador, siendo el sistema operativo el encargado de arbitrar su asignación y uso.
  
**· Gestión y mantenimiento de archivos:** organiza los archivos en diversos dispositivos de almacenamien-to, como discos duros, discos ópticos, etc. El sistema operativo guarda los archivos en los dispositivos de almacenamiento, dentro de directorios y subdirecto-rios, de manera organizada y asegurando que el espacio se usa de la forma más eficiente.
  
**· Manejo de errores:** gestiona los errores de hardware y la pérdida de datos.
  
**· Secuencia de tareas:** el sistema operativo debe administrar el orden de las tareas (quién va primero y quién después).
  
**· Protección:** como complemento a la gestión de recur-sos, el sistema operativo debe evitar que las acciones de un usuario afecten al trabajo que está realizando
otro usuario.

Los sistemas operativos se clasifican desde el punto de vista del usuario final: 

**· Monousuario:** son aquellos que soportan a un usuario a la vez, sin importar el número de procesadores que tenga el sistema informático o el número de procesos o tareas que el usuario pueda ejecutar en un mismo instante de tiempo.

**· Multiusuario:** estos sistemas operativos son capaces de dar servicio a más de un usuario a la vez, ya sea por medio de varias terminales conectadas al sistemainformático o por medio de sesiones remotas en una red de comunicaciones. No importa el número de mi-croprocesadores, ni el número de procesos que cada usuario puede ejecutar simultáneamente.

**· Monotarea:** son aquellos que solo permiten una tarea a la vez por usuario. Puede darse el caso de un sistema multiusuario y monotarea, en el cual se admiten varios usuarios al mismo tiempo pero cada uno de ellos puede estar haciendo solo una tarea a la vez.

**· Multitarea:** son aquellos que permiten al usuario estar realizando varias labores al mismo tiempo. Por ejemplo, se puede estar editando el código fuente de un programa durante su depuración mientras se compila otro programa, a la vez que se está recibiendo el correo electrónico. Para ello, el microprocesador concede un pequeño tiempo a cada tarea. Es común encontrar en ellos interfaces gráficas orientadas al uso de menús y el ratón, lo cual permite un rápido intercambio entre las tareas para el usuario, mejorando su productividad.

**· Uniproceso:** estos sistemas operativos solo son capaces de manejar un microprocesador, de forma que si el sistema informático tuviese más de uno le sería in-útil. El ejemplo más típico de este tipo de sistemas es el DOS.

**· Multiproceso:** se refiere al número de microprocesadores del sistema, que es más de uno y este es capaz de usarlos todos para distribuir su carga de traba-jo. Generalmente, estos sistemas trabajan de dos for-mas: simétrica o asimétricamente. Cuando se trabaja de manera asimétrica, el sistema operativo selecciona a uno de los microprocesadores, el cual jugará el papel de procesador maestro y servirá como pivote para distribuir la carga a los demás microprocesa-dores, que reciben el nombre de esclavos. Cuando se trabaja de manera simétrica, los procesos o partes de ellos (threads) son enviados indistintamente a los microprocesadores disponibles, teniendo, teóricamente, una mejor distribución y equilibrio en la carga de trabajo bajo este esquema.


