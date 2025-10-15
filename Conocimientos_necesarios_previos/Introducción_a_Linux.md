<div align="center">
  
# Introducción a Linux

## Apuntes de Ciberseguridad para principiantes

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Linux-Introducción-000000?style=for-the-badge&logo=linux" />
  <img src="https://img.shields.io/badge/Shell-Bash-4EAA25?style=for-the-badge&logo=gnubash" />
  <img src="https://img.shields.io/badge/Distribuciones-Ubuntu%20%7C%20Debian%20%7C%20Fedora-orange?style=for-the-badge&logo=ubuntu" />
  <img src="https://img.shields.io/badge/Nivel-Estudiante-yellow?style=for-the-badge&logo=graduation-cap" />
</p>


</div> 

---

## ÍNDICE

**1. ¿Qué es Linux?**
 

**2. Como está ordenado Linux**


**3. Usuarios y permisos**


**4. Modelos en capa**
   

**5. Procesos - Los programas en ejecución**


**6. La shell**


**7. Gestión de software**


**8. Servicios y Systemd**


**9. Redes en Linux**


**10. Seguridad Básica en Linux**      

---



## 1. ¿QUÉ ES LINUX Y POR QUÉ ES IMPORTANTE?


Linux es un sistema operativo, es decir, el software fundamental que hace que tu computadora funcione. Es lo que está entre el hardware (los componentes físicos como el procesador, la memoria, el disco duro) y los programas que usas día a día como navegadores web o editores de texto. Sin un sistema operativo, tu computadora sería solo una caja con componentes electrónicos que no sabrían cómo trabajar juntos.

Lo que hace especial a Linux es que es software libre y de código abierto. Esto significa que cualquier persona puede ver exactamente cómo está programado, puede modificarlo si tiene los conocimientos necesarios, y puede compartirlo con otros. Es como tener una receta de cocina que no solo puedes usar, sino también modificar y compartir tu versión mejorada con otros. Esta filosofía es radicalmente diferente a sistemas como Windows o macOS, donde el código es secreto y propiedad de una empresa.

La historia de Linux comienza en 1991 cuando Linus Torvalds, un estudiante universitario en Finlandia, decidió crear su propio sistema operativo como proyecto personal. Lo que empezó como un hobby de un estudiante se convirtió en uno de los proyectos de software más importantes del mundo. Hoy en día, Linux está en todas partes: funciona en los servidores que alojan las páginas web que visitas, en los teléfonos Android, en los routers de Internet, en los supercomputadores más potentes del mundo, e incluso en muchos dispositivos inteligentes de tu hogar.

Es importante entender que cuando decimos "Linux", técnicamente nos referimos solo al kernel o núcleo del sistema. El kernel es como el director de una orquesta: coordina todos los componentes del hardware y se asegura de que trabajen juntos armoniosamente. Pero así como una orquesta necesita más que un director para hacer música, un sistema operativo necesita más que un kernel para ser útil. Necesita programas, herramientas, interfaces. Por eso, el sistema completo que usamos se llama GNU/Linux, porque combina el kernel Linux con las herramientas del proyecto GNU, que fue iniciado por Richard Stallman en 1983 con el objetivo de crear un sistema operativo completamente libre.


## 2. CÓMO ESTÁ ORGANIZADO LINUX

Para entender cómo funciona Linux, es útil pensar en él como un edificio de varios pisos. En el sótano está el hardware, los componentes físicos de tu computadora. En el primer piso está el kernel Linux, que tiene acceso directo al hardware y lo controla. En los pisos superiores están los programas que tú usas, que no pueden acceder directamente al hardware sino que tienen que pedirle al kernel que haga las cosas por ellos.

Esta separación es fundamental para la seguridad y estabilidad del sistema. Imagina que cada programa pudiera acceder directamente al hardware. Un programa mal escrito o malicioso podría dañar otros programas, robar información, o incluso dañar el hardware. Al forzar a todos los programas a pasar por el kernel, Linux puede verificar que cada operación sea segura y válida antes de permitirla.

El kernel funciona en lo que llamamos "modo privilegiado" o "modo kernel", donde tiene poderes totales sobre el sistema. Puede acceder a cualquier parte de la memoria, controlar cualquier dispositivo, y ejecutar cualquier instrucción del procesador. Los programas normales funcionan en "modo usuario", donde tienen restricciones. No pueden acceder a la memoria de otros programas, no pueden controlar directamente el hardware, y si intentan hacer algo peligroso, el kernel los detiene.

Cuando un programa necesita hacer algo que requiere privilegios, como leer un archivo del disco duro, tiene que hacer lo que llamamos una "llamada al sistema" o system call. Es como cuando en un edificio de oficinas necesitas algo del sótano: no puedes ir tú mismo, tienes que llamar al encargado del edificio y pedírselo. El programa le pide al kernel "por favor, léeme este archivo", el kernel verifica que el programa tenga permiso para leer ese archivo, y si todo está bien, el kernel lee el archivo y le pasa los datos al programa.

Entre el kernel y los programas hay una capa intermedia muy importante: las bibliotecas del sistema. Las bibliotecas son colecciones de código que los programas pueden reutilizar. Es como tener un conjunto de herramientas compartidas: en lugar de que cada programa tenga que crear su propio martillo, todos pueden usar el mismo martillo de la caja de herramientas común. La biblioteca más importante es glibc, que proporciona las funciones básicas que casi todos los programas necesitan.

## 3. EL SISTEMA DE ARCHIVOS  


Una de las primeras cosas que puede confundir a alguien nuevo en Linux es cómo se organizan los archivos y carpetas. Si vienes de Windows, estás acostumbrado a tener diferentes unidades como C:, D:, etc. Linux hace las cosas de manera diferente: todo el sistema de archivos es un único árbol que empieza desde una raíz llamada "/" (barra diagonal).

Piensa en el sistema de archivos como un gran árbol invertido. La raíz (/) está en la parte superior, y de ella cuelgan todas las ramas (directorios), que a su vez tienen más ramas (subdirectorios) y hojas (archivos). No importa cuántos discos duros tengas físicamente, todos aparecen en algún lugar dentro de este único árbol. Esto tiene una ventaja enorme: no necesitas preocuparte de en qué disco está cada cosa, todo está unificado en una sola estructura.

Linux tiene una estructura de directorios estándar que encontrarás en casi cualquier sistema Linux. El directorio /home es donde están las carpetas personales de cada usuario. Si tu nombre de usuario es "juan", tu carpeta personal será /home/juan. Aquí es donde guardas tus documentos, fotos, música, y donde los programas guardan tu configuración personal. Es tu espacio privado en el sistema.

El directorio /etc es muy importante porque contiene todos los archivos de configuración del sistema. Es como el panel de control del sistema, pero en lugar de una interfaz gráfica, son archivos de texto que puedes editar. Aquí está la configuración de la red, de los usuarios, de los servicios que se ejecutan, prácticamente todo lo configurable del sistema.

Los programas ejecutables están principalmente en varios directorios "bin" (de binary, binario). El directorio /bin contiene comandos esenciales que todos los usuarios pueden usar, como ls para listar archivos o cp para copiar. El directorio /usr/bin contiene la mayoría de los programas de usuario. El directorio /sbin tiene comandos de administración del sistema que normalmente solo el administrador usa.

Un concepto fundamental en Linux es que "en como archivos especiales en el directorio /dev. Tu disco duro puede aparecer como /dev/sda, tu teclado como /dev/input/keyboard. Incluso la información sobre los procesos en ejecución aparece como archivos en el directorio /proc.todo es un archivo". Esto no significa que literalmente todo sea un archivo en el disco, sino que Linux presenta muchas cosas como si fueran archivos para que puedas interactuar con ellas de manera uniforme. Por ejemplo, los dispositivos de hardware aparec

Algo muy importante en Linux es que el sistema distingue entre mayúsculas yúsc minulas. "Archivo.txt", "archivo.txt" y "ARCHIVO.TXT" son tres archivos completamente diferentes. Esto puede ser confuso al principio si vienes de Windows, pero te acostumbras rápidamente y permite mucha más flexibilidad en los nombres.

![Imagenes](https://www2.iib.uam.es/bioinfo/curso/perl/so/images/arboldir.gif)  

## 4. USUARIOS Y PERMISOS  

Linux fue diseñado desde el principio como un sistema multiusuario. Esto significa que múltiples personas pueden usar el mismo sistema al mismo tiempo, cada una con su propia cuenta, sus propios archivos, y sin interferir con los demás. Aunque hoy en día la mayoría usamos computadoras personales, este diseño multiusuario es fundamental para la seguridad del sistema.

Cada usuario en Linux tiene un nombre de usuario y un número de identificación único llamado UID. El sistema internamente no entiende nombres, solo números, pero usa los nombres para que sea más fácil para los humanos. Hay tres tipos principales de usuarios en un sistema Linux.

El primer tipo es el superusuario o root, que tiene UID 0. Root es el administrador todopoderoso del sistema. Puede hacer absolutamente cualquier cosa: leer cualquier archivo, modificar cualquier configuración, instalar o desinstalar programas, crear o eliminar usuarios. Es como tener la llave maestra de un edificio. Por este poder absoluto, es peligroso usar root para tareas cotidianas. Un error simple como borrar el archivo equivocado podría destruir el sistema completo.

El segundo tipo son los usuarios del sistema, que tienen UIDs entre 1 y 999. Estos no son personas reales, sino cuentas especiales que los servicios del sistema usan para ejecutarse. Por ejemplo, el servidor web Apache puede ejecutarse como el usuario www-data, la base de datos MySQL como el usuario mysql. Esto es por seguridad: si alguien encuentra una vulnerabilidad en el servidor web y logra tomar control de él, solo tendrá los permisos limitados del usuario www-data, no podrá acceder a todo el sistema.

El tercer tipo son los usuarios normales, como tú y yo, que tienen UIDs a partir de 1000. Cada usuario tiene su propia carpeta home donde puede guardar sus archivos, su propia configuración, y sus propios procesos ejecutándose. Los usuarios normales no pueden modificar archivos del sistema ni instalar programas para todo el sistema, solo en su propio espacio.

Los permisos en Linux son elegantemente simples pero muy poderosos. Cada archivo y directorio tiene tres tipos de permisos: lectura (read), escritura (write) y ejecución (execute). Estos permisos se aplican a tres categorías de usuarios: el propietario del archivo, el grupo al que pertenece el archivo, y todos los demás.

El permiso de lectura en un archivo significa que puedes ver su contenido. En un directorio, significa que puedes ver qué archivos contiene. El permiso de escritura en un archivo significa que puedes modificarlo. En un directorio, significa que puedes crear o eliminar archivos dentro de él. El permiso de ejecución en un archivo significa que puedes ejecutarlo como un programa. En un directorio, significa que puedes entrar a él y acceder a los archivos que contiene.

Los permisos se ven como una serie de letras, por ejemplo: rwxr-xr--. Los primeros tres caracteres (rwx) son los permisos del propietario: puede leer, escribir y ejecutar. Los siguientes tres (r-x) son para el grupo: pueden leer y ejecutar pero no escribir. Los últimos tres (r--) son para todos los demás: solo pueden leer.

Este sistema de permisos es la primera línea de defensa en Linux. Evita que los usuarios accedan a archivos que no deberían ver, que modifiquen archivos importantes del sistema, o que ejecuten programas peligrosos. Es simple pero efectivo, y ha protegido sistemas Linux durante décadas.

![Imágenes](https://computernewage.com/wp-content/uploads/2015/06/representacion-permisos-en-linux1.png)

## 5. PROCESOS - LOS PROGRAMAS EN EJECUCIÓN

Un proceso es un programa que se está ejecutando. Es importante entender la diferencia: un programa es como una receta en un libro de cocina, estático, solo instrucciones escritas. Un proceso es el acto de cocinar siguiendo esa receta, dinámico, con ingredientes reales, usando utensilios reales, en un momento específico. Puedes tener múltiples procesos del mismo programa, como varias personas cocinando la misma receta al mismo tiempo.

Cada proceso en Linux tiene un número único llamado PID (Process ID) que lo identifica. El primer proceso que se ejecuta cuando arranca el sistema siempre tiene PID 1, y es especial: es el padre de todos los demás procesos. En sistemas modernos, este proceso suele ser systemd, que se encarga de iniciar todos los servicios del sistema.

Los procesos en Linux forman una jerarquía familiar. Cada proceso es creado por otro proceso, estableciendo una relación padre-hijo. Cuando un proceso crea otro, el nuevo proceso es su hijo. Si el padre termina antes que el hijo, el hijo queda huérfano y es adoptado automáticamente por el proceso init (PID 1). Esta estructura familiar es importante para la gestión del sistema.

Un proceso puede estar en diferentes estados durante su vida. Puede estar ejecutándose (running), que significa que está usando el CPU en este momento. Puede estar durmiendo (sleeping), esperando a que ocurra algo, como que el usuario escriba algo o que lleguen datos de la red. Puede estar detenido (stopped), pausado temporalmente. Y puede estar en estado zombie, que es cuando el proceso ha terminado pero su información aún no ha sido recogida por su proceso padre.

Los procesos no siempre están activos. De hecho, en un momento dado, la mayoría de los procesos están durmiendo, esperando a que ocurra algo. Esto es normal y eficiente. Un editor de texto pasa la mayor parte del tiempo esperando a que escribas algo. Un navegador web pasa mucho tiempo esperando datos de Internet. El kernel se encarga de despertar los procesos cuando ocurre lo que estaban esperando.

Linux puede ejecutar muchos más procesos que CPUs tiene tu computadora. Lo hace mediante una técnica llamada time-sharing o tiempo compartido. El kernel da a cada proceso un pequeño tiempo para ejecutarse (milisegundos), luego lo pausa y da tiempo a otro proceso. Esto ocurre tan rápido que parece que todos los procesos se ejecutan al mismo tiempo, pero en realidad se están turnando muy rápidamente.

Hay un tipo especial de procesos llamados demonios (daemons). Los demonios son procesos que se ejecutan en segundo plano, sin interacción directa con el usuario, proporcionando servicios al sistema. Por ejemplo, el demonio sshd espera conexiones SSH remotas, el demonio cron ejecuta tareas programadas, el demonio de impresión gestiona la cola de impresión. Los demonios típicamente se inician cuando arranca el sistema y se ejecutan continuamente hasta que el sistema se apaga.


## 6. LA SHELL

La shell es tu ventana al sistema Linux. Es un programa que acepta comandos que escribes con el teclado y le dice al sistema operativo que los ejecute. Aunque hoy en día tenemos interfaces gráficas bonitas, el shell sigue siendo fundamental en Linux porque es potente, flexible, y te permite hacer cosas que serían difíciles o imposibles con una interfaz gráfica.

Piensa en el shell como un intérprete entre tú y el sistema. Tú hablas en comandos que puedes entender, como "ls" para listar archivos o "cp" para copiar. El shell toma estos comandos, los interpreta, y hace las llamadas necesarias al sistema operativo para ejecutarlos. Es como tener un asistente personal que entiende tus instrucciones y las lleva a cabo.

La shell más común en Linux es Bash (Bourne Again Shell). Cuando abres una terminal, normalmente estás usando Bash. Pero Bash es más que un simple intérprete de comandos: es un lenguaje de programación completo. Puedes escribir scripts (programas) en Bash para automatizar tareas repetitivas. Por ejemplo, si necesitas renombrar cientos de archivos siguiendo un patrón, puedes escribir un script Bash que lo haga automáticamente.

Una de las características más poderosas del shell es la capacidad de combinar comandos simples para hacer cosas complejas. Esto se hace con tuberías (pipes), representadas por el símbolo |. Una tubería toma la salida de un comando y la usa como entrada para otro comando. Es como una línea de ensamblaje donde cada trabajador hace una tarea simple y pasa el resultado al siguiente trabajador.

La shell también maneja las variables de entorno, que son valores que afectan cómo funcionan los programas. La variable PATH, por ejemplo, le dice al shell dónde buscar los programas cuando escribes un comando. La variable HOME indica cuál es tu directorio personal. La variable USER contiene tu nombre de usuario. Estas variables crean un "ambiente" personalizado para cada usuario.

La redirección es otra característica poderosa del shell. Normalmente, cuando ejecutas un comando, su salida aparece en la pantalla. Pero puedes redirigir esa salida a un archivo usando >. Por ejemplo, "ls > archivos.txt" guarda la lista de archivos en un archivo en lugar de mostrarla en pantalla. También puedes hacer que un programa lea su entrada desde un archivo en lugar del teclado usando <.

La shell mantiene un historial de los comandos que has ejecutado. Puedes navegar por este historial con las flechas arriba y abajo, lo que es muy útil para repetir o modificar comandos anteriores. También tiene autocompletado: si empiezas a escribir un comando o nombre de archivo y presionas Tab, el shell intentará completarlo por ti.


## 7. GESTIÓN DE SOFTWARE


Instalar software en Linux es diferente a lo que podrías estar acostumbrado en Windows o Mac. En lugar de descargar instaladores de diferentes sitios web, Linux usa un sistema centralizado llamado gestión de paquetes. Es como tener una tienda de aplicaciones integrada en el sistema, pero más poderosa y que existe desde mucho antes que las tiendas de aplicaciones móviles.

Un paquete es básicamente un archivo comprimido que contiene todos los archivos necesarios para que un programa funcione: el programa ejecutable, archivos de configuración, documentación, y información sobre qué otros paquetes necesita para funcionar. Esta última parte es crucial y se llama dependencias.

Las dependencias son otros paquetes que un programa necesita para funcionar. Por ejemplo, un editor de fotos puede depender de bibliotecas para leer diferentes formatos de imagen. El sistema de paquetes se encarga automáticamente de instalar todas las dependencias necesarias. No tienes que preocuparte de instalar las cosas en el orden correcto o de olvidar algo: el sistema lo maneja por ti.

Cada distribución de Linux tiene su formato de paquetes y su gestor de paquetes. Debian y Ubuntu usan paquetes .deb y el gestor APT. Red Hat y Fedora usan paquetes .rpm y el gestor YUM o DNF. Arch Linux usa pacman. Aunque esto puede parecer confuso, el concepto es el mismo: un sistema centralizado para instalar, actualizar y eliminar software de manera consistente.

Los paquetes vienen de repositorios, que son servidores que contienen colecciones de software. Tu sistema Linux viene configurado con los repositorios oficiales de tu distribución, que contienen miles de paquetes probados y verificados. También puedes agregar repositorios de terceros para obtener software adicional, aunque debes ser cuidadoso con esto por seguridad.

Una gran ventaja de este sistema es que las actualizaciones son centralizadas. Con un solo comando puedes actualizar todo el software de tu sistema: el kernel, los drivers, las aplicaciones, todo. No necesitas actualizar cada programa individualmente. El sistema también maneja las dependencias durante las actualizaciones, asegurándose de que todo siga funcionando correctamente.

Cuando desinstalas un paquete, el sistema sabe exactamente qué archivos instaló y los elimina limpiamente. No quedan archivos basura regados por el sistema como puede pasar en otros sistemas operativos. Si otros paquetes dependían del que estás desinstalando, el sistema te advertirá.


## 8. SERVICIOS Y SYSTEMD

Los servicios son programas que se ejecutan en segundo plano proporcionando funcionalidades importantes al sistema. Son como los empleados de mantenimiento de un edificio: no los ves, pero están ahí asegurándose de que todo funcione. Un servidor web es un servicio que espera peticiones de páginas web. Un servidor SSH es un servicio que permite conexiones remotas. El servicio de impresión gestiona las impresoras.

En Linux moderno, estos servicios son gestionados por systemd, que es mucho más que un simple gestor de servicios: es el sistema de inicio y gestión del sistema completo. Systemd es el primer proceso que se ejecuta cuando arranca Linux (PID 1) y es responsable de iniciar todo lo demás en el orden correcto.

Systemd introdujo el concepto de "unidades". Una unidad puede ser un servicio, pero también puede ser un punto de montaje de disco, un dispositivo, un socket de red, o un temporizador. Todo en systemd es una unidad, lo que proporciona una forma uniforme de gestionar diferentes aspectos del sistema.

Los servicios en systemd pueden tener dependencias entre ellos. Por ejemplo, el servidor web puede depender del servicio de red. Systemd se asegura de iniciar los servicios en el orden correcto, respetando estas dependencias. Si un servicio falla, systemd puede intentar reiniciarlo automáticamente.

Una característica importante de systemd es el arranque en paralelo. Los sistemas antiguos iniciaban los servicios uno por uno, en secuencia. Systemd puede iniciar múltiples servicios al mismo tiempo, siempre que no dependan unos de otros. Esto hace que el sistema arranque mucho más rápido.

Systemd también introdujo el journal, un sistema de logging centralizado. Todos los mensajes del sistema, del kernel, de los servicios, se recopilan en un solo lugar. Puedes buscar en estos logs por tiempo, por servicio, por prioridad. Es una herramienta invaluable para diagnosticar problemas.

Los targets en systemd son como los antiguos runlevels: diferentes estados del sistema. Por ejemplo, el target multi-user.target es el sistema funcionando normalmente pero sin interfaz gráfica. El target graphical.target incluye la interfaz gráfica. El target rescue.target es un modo mínimo para reparar el sistema.

![Imágenes](https://upload.wikimedia.org/wikipedia/commons/thumb/3/35/Systemd_components.svg/500px-Systemd_components.svg.png)

## 9. REDES EN LINUX

Linux tiene capacidades de red integradas profundamente en el sistema. No es algo añadido después, sino parte fundamental del diseño. Linux implementa la pila completa de protocolos TCP/IP, los mismos protocolos que hacen funcionar Internet.

Una interfaz de red en Linux es el punto de conexión entre tu sistema y una red. Puede ser una tarjeta de red física (Ethernet), una tarjeta inalámbrica (WiFi), o incluso interfaces virtuales. La interfaz de loopback, llamada "lo", es especial: es una interfaz virtual que apunta al propio sistema. Su dirección es siempre 127.0.0.1, y se usa para que los programas puedan comunicarse entre sí dentro del mismo sistema.

Cada interfaz de red necesita configuración: una dirección IP que la identifica en la red, una máscara de red que define qué otras direcciones están en la misma red local, una puerta de enlace (gateway) que es por donde salen los paquetes destinados a otras redes, y servidores DNS que traducen nombres de dominio a direcciones IP.

Linux puede configurar las interfaces de red de manera estática (tú defines la dirección IP) o dinámica (obtiene la dirección automáticamente de un servidor DHCP). La configuración dinámica es más común en redes domésticas y oficinas, mientras que los servidores suelen usar configuración estática.

El firewall en Linux se implementa en el kernel mismo, usando un sistema llamado netfilter. La herramienta tradicional para configurar el firewall es iptables, aunque hay herramientas más modernas y simples como ufw o firewalld. El firewall puede filtrar paquetes basándose en dirección de origen, destino, puerto, protocolo, y muchos otros criterios.

Linux puede actuar como router, reenviando paquetes entre diferentes redes. Puede hacer NAT (Network Address Translation) para compartir una conexión a Internet entre múltiples dispositivos. Puede crear redes privadas virtuales (VPN). Puede servir como servidor de casi cualquier servicio de red: web, correo, DNS, DHCP, y muchos más.

La configuración de red se guarda en diferentes lugares según la distribución. Los archivos /etc/hostname y /etc/hosts son comunes a todas: el primero contiene el nombre del sistema, el segundo permite asociar nombres a direcciones IP localmente. El archivo /etc/resolv.conf contiene los servidores DNS a usar.

## 10. SEGURIDAD BÁSICA EN LINUX

La seguridad en Linux está construida en capas, como una cebolla. Cada capa añade protección adicional, y si una capa es comprometida, las otras siguen protegiendo el sistema. Esta defensa en profundidad es fundamental para mantener los sistemas seguros.

La primera capa es la separación entre el espacio del kernel y el espacio de usuario. Los programas normales no pueden acceder directamente al hardware ni a la memoria de otros programas. Si un programa tiene un error o es malicioso, el daño que puede hacer está limitado a sus propios recursos.

La segunda capa son los permisos de archivos que ya discutimos. Cada archivo tiene un dueño y permisos que controlan quién puede leerlo, modificarlo o ejecutarlo. Esto evita que los usuarios accedan a archivos que no deberían ver o modifiquen archivos importantes del sistema.

La tercera capa es la separación de privilegios. Los servicios del sistema ejecutan con usuarios especiales que tienen solo los permisos mínimos necesarios para su función. Si un atacante compromete un servicio, solo obtiene los privilegios limitados de ese servicio, no control total del sistema.

Además de estas capas básicas, Linux tiene sistemas de seguridad adicionales como SELinux o AppArmor. Estos son sistemas de control de acceso obligatorio (MAC) que añaden políticas de seguridad más estrictas. Pueden especificar exactamente qué puede hacer cada programa: qué archivos puede leer, qué puertos de red puede abrir, qué otros programas puede ejecutar.

Los logs o registros son fundamentales para la seguridad. Linux registra casi todo lo que ocurre en el sistema: quién inició sesión, qué comandos se ejecutaron, qué servicios se iniciaron o fallaron, intentos de acceso no autorizado. Estos logs se guardan en /var/log/ y son invaluables para detectar problemas o investigar incidentes de seguridad.

Las actualizaciones de seguridad son críticas. Cuando se descubre una vulnerabilidad, los desarrolladores crean parches para corregirla. En Linux, estas actualizaciones llegan a través del sistema de paquetes. Es importante instalar las actualizaciones de seguridad tan pronto como sea posible para mantener el sistema protegido.

El principio de menor privilegio es fundamental en la seguridad de Linux. Los usuarios deben tener solo los permisos mínimos necesarios para hacer su trabajo. No debes usar root para tareas diarias. Los servicios deben ejecutar con usuarios limitados. Los archivos deben tener los permisos más restrictivos posibles que aún permitan su función.

El hardening o endurecimiento es el proceso de hacer el sistema más seguro. Incluye desactivar servicios innecesarios (cada servicio es una posible puerta de entrada), configurar un firewall restrictivo, usar contraseñas fuertes, configurar actualizaciones automáticas de seguridad, y monitorear los logs regularmente.

