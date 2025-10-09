# INTRODUCCIÓN A LINUX
## Apuntes de Ciberseguridad para principiantes

---

## ÍNDICE

1. **Introducción y Contexto Histórico**
   - 1.1 ¿Qué es Linux?
   - 1.2 Historia y evolución
   - 1.3 Filosofía del Software Libre
   - 1.4 GNU/Linux vs Linux

2. **Arquitectura del Sistema Linux**
   - 2.1 Estructura en capas
   - 2.2 El Kernel
   - 2.3 Espacio de usuario (User Space)
   - 2.4 Llamadas al sistema (System Calls)

3. **Sistema de Archivos**
   - 3.1 Estructura jerárquica
   - 3.2 Directorios principales del FHS
   - 3.3 Tipos de archivos en Linux
   - 3.4 Inodos y metadatos

4. **Gestión de Procesos**
   - 4.1 ¿Qué es un proceso?
   - 4.2 Estados de un proceso
   - 4.3 Procesos padre e hijo
   - 4.4 Demonios (Daemons)

5. **Usuarios, Grupos y Permisos**
   - 5.1 Sistema multiusuario
   - 5.2 Usuarios y grupos
   - 5.3 Sistema de permisos
   - 5.4 Permisos especiales

6. **El Shell y la Terminal**
   - 6.1 Concepto de Shell
   - 6.2 Tipos de Shell
   - 6.3 Variables de entorno
   - 6.4 Redirección y tuberías

7. **Gestión de Software**
   - 7.1 Concepto de paquetes
   - 7.2 Gestores de paquetes
   - 7.3 Dependencias
   - 7.4 Repositorios

8. **Servicios y Systemd**
   - 8.1 Concepto de servicio
   - 8.2 Init System
   - 8.3 Systemd
   - 8.4 Runlevels y targets

9. **Conceptos de Red en Linux**
   - 9.1 Stack TCP/IP en Linux
   - 9.2 Interfaces de red
   - 9.3 Configuración de red
   - 9.4 Firewall y iptables

10. **Fundamentos de Seguridad**
    - 10.1 Modelo de seguridad de Linux
    - 10.2 SELinux y AppArmor
    - 10.3 Auditoría y logs
    - 10.4 Principios de hardening

---

## 1. INTRODUCCIÓN Y CONTEXTO HISTÓRICO

### 1.1 ¿Qué es Linux?

Linux es un kernel (núcleo) de sistema operativo de tipo Unix, libre y de código abierto. Es importante entender que cuando hablamos de "Linux" en el contexto cotidiano, generalmente nos referimos a todo el sistema operativo completo, aunque técnicamente Linux es solo el kernel.

**Características fundamentales:**
- **Multitarea**: Capaz de ejecutar múltiples procesos simultáneamente
- **Multiusuario**: Permite que múltiples usuarios trabajen en el sistema al mismo tiempo
- **Multiplataforma**: Funciona en diversas arquitecturas de hardware
- **Modular**: Su diseño permite agregar o quitar funcionalidades según necesidades

### 1.2 Historia y Evolución

**1969-1970**: Nace UNIX en los laboratorios Bell de AT&T, desarrollado por Ken Thompson y Dennis Ritchie. Este sistema sentó las bases filosóficas y técnicas que heredaría Linux.

**1983**: Richard Stallman inicia el proyecto GNU (GNU's Not Unix) con el objetivo de crear un sistema operativo completamente libre. Este proyecto desarrolló herramientas esenciales como el compilador GCC, el editor Emacs y las utilidades básicas del sistema.

**1991**: Linus Torvalds, estudiante finlandés de la Universidad de Helsinki, anuncia la primera versión de Linux (0.01) en el grupo de noticias comp.os.minix. Inicialmente era un proyecto personal para crear un kernel similar a MINIX pero libre.

**Evolución del kernel:**
- Versión 1.0 (1994): Primera versión estable
- Versión 2.0 (1996): Soporte multiprocesador
- Versión 2.4 (2001): Mejoras en escalabilidad
- Versión 2.6 (2003): Mejoras significativas en rendimiento
- Versión 3.0 (2011): Cambio de numeración
- Versión 4.0 (2015): Actualizaciones sin reinicio
- Versión 5.0 (2019): Soporte para hardware moderno
- Versión 6.0 (2022): Optimizaciones y nuevo hardware

### 1.3 Filosofía del Software Libre

El movimiento del software libre se basa en cuatro libertades fundamentales definidas por la Free Software Foundation:

**Libertad 0**: Ejecutar el programa con cualquier propósito
**Libertad 1**: Estudiar cómo funciona el programa y modificarlo
**Libertad 2**: Redistribuir copias del programa
**Libertad 3**: Distribuir copias de versiones modificadas

**Licencias principales:**
- **GPL (General Public License)**: Licencia copyleft que garantiza que las modificaciones también sean libres
- **MIT/BSD**: Licencias permisivas que permiten uso en software propietario
- **Apache**: Similar a MIT pero con protección de patentes

### 1.4 GNU/Linux vs Linux

**Linux**: Es únicamente el kernel del sistema operativo. Se encarga de:
- Gestión de memoria
- Gestión de procesos
- Control de dispositivos
- Comunicación entre hardware y software

**GNU/Linux**: Es el sistema operativo completo que incluye:
- El kernel Linux
- Las herramientas GNU (compiladores, shells, utilidades)
- Sistema de ventanas (opcional)
- Aplicaciones de usuario

---

## 2. ARQUITECTURA DEL SISTEMA LINUX

### 2.1 Estructura en Capas

Linux sigue una arquitectura en capas que proporciona abstracción y modularidad:

```
┌─────────────────────────────────┐
│     Aplicaciones de Usuario     │  Capa 4
├─────────────────────────────────┤
│        Shell/Terminal           │  Capa 3
├─────────────────────────────────┤
│    Bibliotecas del Sistema      │  Capa 2
├─────────────────────────────────┤
│          Kernel Linux           │  Capa 1
├─────────────────────────────────┤
│           Hardware              │  Capa 0
└─────────────────────────────────┘
```

Cada capa se comunica solo con las capas adyacentes, proporcionando:
- **Abstracción**: Las capas superiores no necesitan conocer detalles de implementación de las inferiores
- **Modularidad**: Se pueden modificar capas sin afectar a otras
- **Seguridad**: Control de acceso entre capas

### 2.2 El Kernel

El kernel es el núcleo del sistema operativo y tiene privilegios totales sobre el hardware. Opera en "modo kernel" o "modo privilegiado".

**Tipos de kernel:**
- **Monolítico**: Todo el código del kernel se ejecuta en un único espacio de memoria (Linux)
- **Microkernel**: Solo funciones esenciales en el kernel, resto como procesos de usuario
- **Híbrido**: Combinación de ambos enfoques

**Funciones principales del kernel Linux:**

1. **Gestión de memoria**:
   - Memoria virtual mediante paginación
   - Asignación y liberación de memoria
   - Intercambio (swap) con disco
   - Protección de memoria entre procesos

2. **Gestión de procesos**:
   - Creación y terminación de procesos
   - Planificación (scheduling) de CPU
   - Comunicación entre procesos (IPC)
   - Sincronización y exclusión mutua

3. **Sistema de archivos**:
   - Virtual File System (VFS) como capa de abstracción
   - Soporte para múltiples sistemas de archivos
   - Gestión de inodos y bloques
   - Cache de disco

4. **Gestión de dispositivos**:
   - Drivers para hardware
   - Abstracción de dispositivos como archivos
   - Gestión de interrupciones
   - DMA (Direct Memory Access)

5. **Redes**:
   - Implementación del stack TCP/IP
   - Sockets y protocolos de red
   - Filtrado de paquetes (netfilter)

### 2.3 Espacio de Usuario (User Space)

El espacio de usuario es donde se ejecutan todas las aplicaciones sin privilegios del kernel. Los procesos aquí:
- No pueden acceder directamente al hardware
- Tienen memoria protegida y aislada
- Deben solicitar servicios al kernel mediante system calls
- Pueden ser terminados sin afectar la estabilidad del sistema

**Componentes del espacio de usuario:**
- Bibliotecas estándar (glibc)
- Intérpretes y shells
- Utilidades del sistema
- Servicios y demonios
- Aplicaciones de usuario

### 2.4 Llamadas al Sistema (System Calls)

Las system calls son la interfaz entre el espacio de usuario y el kernel. Son el único mecanismo para que los programas soliciten servicios al kernel.

**Categorías principales:**
- **Control de procesos**: fork(), exec(), exit(), wait()
- **Gestión de archivos**: open(), read(), write(), close()
- **Gestión de dispositivos**: ioctl(), read(), write()
- **Mantenimiento de información**: getpid(), alarm(), sleep()
- **Comunicaciones**: pipe(), socket(), shmget()

**Proceso de una llamada al sistema:**
1. El programa invoca una función de biblioteca
2. La biblioteca prepara los parámetros
3. Se ejecuta una interrupción software (int 0x80 o syscall)
4. El CPU cambia a modo kernel
5. El kernel ejecuta el servicio solicitado
6. Se retorna al modo usuario con el resultado

---

## 3. SISTEMA DE ARCHIVOS

### 3.1 Estructura Jerárquica

Linux organiza todos los archivos en una única jerarquía en forma de árbol invertido, comenzando desde la raíz (/). Esta estructura difiere de sistemas como Windows que usan letras de unidad.

**Características fundamentales:**
- **Único árbol de directorios**: Todo se monta bajo /
- **Case-sensitive**: Distingue mayúsculas de minúsculas
- **Sin extensiones obligatorias**: El tipo de archivo no depende de la extensión
- **Todo es un archivo**: Dispositivos, procesos y recursos se representan como archivos

### 3.2 Directorios Principales del FHS

El Filesystem Hierarchy Standard (FHS) define la estructura estándar de directorios:

**/**: Directorio raíz, punto de inicio de toda la jerarquía

**/bin**: Binarios esenciales del sistema disponibles para todos los usuarios (ls, cp, mv)

**/boot**: Archivos necesarios para el arranque del sistema (kernel, initrd, GRUB)

**/dev**: Archivos de dispositivos (discos, terminales, dispositivos de entrada)
- Dispositivos de bloque: Acceso aleatorio (discos)
- Dispositivos de carácter: Acceso secuencial (terminales)

**/etc**: Archivos de configuración del sistema
- Configuración global del sistema
- No contiene binarios
- Generalmente archivos de texto plano

**/home**: Directorios personales de usuarios
- Cada usuario tiene su subdirectorio
- Almacena configuraciones personales y archivos

**/lib y /lib64**: Bibliotecas compartidas esenciales y módulos del kernel

**/media**: Punto de montaje para medios removibles (USB, CD-ROM)

**/mnt**: Punto de montaje temporal para sistemas de archivos

**/opt**: Software opcional y paquetes de terceros

**/proc**: Sistema de archivos virtual con información del kernel y procesos
- No existe en disco, se genera dinámicamente
- Información de procesos en /proc/[PID]
- Parámetros del kernel en /proc/sys

**/root**: Directorio home del usuario root

**/sbin**: Binarios del sistema para administración (solo root)

**/srv**: Datos servidos por el sistema (web, ftp)

**/sys**: Sistema de archivos virtual con información del kernel (sysfs)
- Información sobre dispositivos y drivers
- Interfaz para configurar parámetros del kernel

**/tmp**: Archivos temporales
- Generalmente se limpia en cada reinicio
- Todos los usuarios pueden escribir

**/usr**: Jerarquía secundaria con programas y datos de usuario
- /usr/bin: Comandos de usuario
- /usr/lib: Bibliotecas
- /usr/share: Datos independientes de arquitectura

**/var**: Datos variables
- /var/log: Archivos de log
- /var/spool: Colas de impresión y correo
- /var/cache: Cache de aplicaciones

### 3.3 Tipos de Archivos en Linux

Linux reconoce siete tipos de archivos:

1. **Archivos regulares (-)**: Contienen datos (texto, binarios, imágenes)
2. **Directorios (d)**: Contienen referencias a otros archivos
3. **Enlaces simbólicos (l)**: Apuntan a otro archivo o directorio
4. **Dispositivos de caracteres (c)**: Acceso secuencial a dispositivos
5. **Dispositivos de bloque (b)**: Acceso aleatorio a dispositivos
6. **Tuberías con nombre (p)**: FIFO para comunicación entre procesos
7. **Sockets (s)**: Comunicación entre procesos local o en red

### 3.4 Inodos y Metadatos

Un inodo (index node) es una estructura de datos que contiene metadatos sobre un archivo:

**Información almacenada en el inodo:**
- Tipo de archivo
- Permisos
- Número de enlaces duros
- Propietario (UID) y grupo (GID)
- Tamaño del archivo
- Timestamps (atime, mtime, ctime)
- Punteros a bloques de datos

**Conceptos importantes:**
- El nombre del archivo NO se almacena en el inodo
- Los directorios son listas que asocian nombres con números de inodo
- Enlaces duros: Múltiples nombres apuntando al mismo inodo
- Enlaces simbólicos: Archivo especial que contiene una ruta

---

## 4. GESTIÓN DE PROCESOS

### 4.1 ¿Qué es un Proceso?

Un proceso es un programa en ejecución junto con su entorno de ejecución. Es la unidad fundamental de trabajo en Linux.

**Componentes de un proceso:**
- **Código del programa**: Instrucciones a ejecutar
- **Espacio de memoria**: Stack, heap, segmento de datos
- **Contexto de ejecución**: Registros del CPU, program counter
- **Recursos asignados**: Archivos abiertos, señales pendientes
- **Información de estado**: PID, estado del proceso, propietario

**Identificadores de proceso:**
- **PID (Process ID)**: Identificador único del proceso
- **PPID (Parent Process ID)**: PID del proceso padre
- **UID/GID**: Usuario y grupo propietario del proceso

### 4.2 Estados de un Proceso

Los procesos en Linux pueden estar en diferentes estados durante su ciclo de vida:

**Estados principales:**

1. **Running (R)**: El proceso está ejecutándose o listo para ejecutarse
2. **Sleeping (S)**: Esperando por algún evento (I/O, señal)
   - Interruptible sleep (S): Puede ser despertado por señales
   - Uninterruptible sleep (D): No responde a señales
3. **Stopped (T)**: Detenido por una señal (SIGSTOP) o control de trabajos
4. **Zombie (Z)**: Proceso terminado pero su entrada en la tabla de procesos no ha sido reclamada por el padre

**Transiciones entre estados:**
```
         NEW → READY → RUNNING → TERMINATED
                ↑         ↓
                ← WAITING ←
```

### 4.3 Procesos Padre e Hijo

Linux utiliza una jerarquía de procesos donde cada proceso (excepto init/systemd) tiene un padre.

**Creación de procesos:**
- **fork()**: Crea una copia exacta del proceso padre
- **exec()**: Reemplaza el proceso actual con un nuevo programa
- **Modelo fork-exec**: Método estándar para crear nuevos procesos

**Árbol de procesos:**
- **init/systemd (PID 1)**: Primer proceso, padre de todos
- **Procesos huérfanos**: Adoptados por init cuando el padre muere
- **Procesos zombie**: Esperan que el padre lea su código de salida

**Comunicación entre procesos padre-hijo:**
- Herencia de variables de entorno
- Descriptores de archivo compartidos
- Señales para comunicación
- Código de salida del hijo al padre

### 4.4 Demonios (Daemons)

Los demonios son procesos que se ejecutan en segundo plano sin terminal asociada, generalmente proporcionando servicios.

**Características de los demonios:**
- Se ejecutan en background
- No tienen terminal de control
- Generalmente iniciados al arranque del sistema
- Tradicionalmente sus nombres terminan en 'd' (sshd, httpd, systemd)

**Proceso de creación de un demonio:**
1. Fork del proceso padre y terminar el padre
2. Crear una nueva sesión (setsid)
3. Fork de nuevo (opcional, para garantizar que no es líder de sesión)
4. Cambiar el directorio de trabajo a /
5. Cerrar descriptores de archivo innecesarios
6. Redirigir stdin, stdout, stderr a /dev/null

**Tipos de demonios:**
- **Sistema**: Servicios esenciales del sistema (systemd, cron)
- **Red**: Servicios de red (sshd, httpd, ftpd)
- **Hardware**: Gestión de dispositivos (udev)

---

## 5. USUARIOS, GRUPOS Y PERMISOS

### 5.1 Sistema Multiusuario

Linux es inherentemente multiusuario, permitiendo que múltiples usuarios accedan al sistema simultáneamente con aislamiento y protección entre ellos.

**Ventajas del sistema multiusuario:**
- Compartición eficiente de recursos
- Aislamiento de procesos y datos entre usuarios
- Control de acceso granular
- Auditoría y trazabilidad de acciones

**Archivos fundamentales:**
- **/etc/passwd**: Información de cuentas de usuario
- **/etc/shadow**: Contraseñas encriptadas
- **/etc/group**: Definición de grupos
- **/etc/gshadow**: Contraseñas de grupo

### 5.2 Usuarios y Grupos

**Tipos de usuarios:**

1. **Root (UID 0)**: 
   - Superusuario con privilegios totales
   - Puede acceder a todos los archivos y ejecutar cualquier comando
   - Puede cambiar la identidad a cualquier usuario

2. **Usuarios del sistema (UID 1-999)**:
   - Cuentas para servicios y demonios
   - Generalmente sin shell de login
   - Ejemplos: www-data, mysql, nobody

3. **Usuarios regulares (UID 1000+)**:
   - Cuentas para personas reales
   - Directorio home personal
   - Shell de login asignado

**Grupos:**
- **Grupo primario**: Cada usuario pertenece a un grupo primario (GID en /etc/passwd)
- **Grupos secundarios**: Usuario puede pertenecer a múltiples grupos adicionales
- **Propósito**: Facilitar la compartición de recursos entre usuarios

### 5.3 Sistema de Permisos

Linux utiliza un sistema de permisos basado en tres tipos de acceso para tres categorías de usuarios.

**Tipos de permisos:**
- **Read (r = 4)**: Leer archivo o listar contenido de directorio
- **Write (w = 2)**: Modificar archivo o crear/eliminar en directorio
- **Execute (x = 1)**: Ejecutar archivo o acceder a directorio

**Categorías de usuarios:**
- **Owner (u)**: Propietario del archivo
- **Group (g)**: Grupo propietario
- **Others (o)**: Todos los demás usuarios

**Representación de permisos:**
```
-rwxr-xr-- 
│└─┴─┴─┴─┴─┴─┘
│  │  │  └── Others: r-- (4)
│  │  └───── Group:  r-x (5)
│  └──────── Owner:  rwx (7)
└─────────── Tipo de archivo
```

**Notación octal**: 754 = rwxr-xr--

### 5.4 Permisos Especiales

Además de los permisos básicos, existen tres permisos especiales:

**1. SUID (Set User ID) - valor 4**:
- En archivos ejecutables: Se ejecuta con los privilegios del propietario
- Representación: s en el permiso de ejecución del owner
- Ejemplo: /usr/bin/passwd necesita SUID para modificar /etc/shadow

**2. SGID (Set Group ID) - valor 2**:
- En ejecutables: Se ejecuta con los privilegios del grupo
- En directorios: Los archivos creados heredan el grupo del directorio
- Representación: s en el permiso de ejecución del grupo

**3. Sticky Bit - valor 1**:
- En directorios: Solo el propietario puede eliminar sus archivos
- Común en directorios compartidos como /tmp
- Representación: t en el permiso de ejecución de others

**Máscara de creación (umask)**:
- Define los permisos por defecto al crear archivos y directorios
- Se resta de los permisos máximos (666 para archivos, 777 para directorios)
- Ejemplo: umask 022 → archivos creados con 644, directorios con 755

---

## 6. EL SHELL Y LA TERMINAL

### 6.1 Concepto de Shell

El shell es un intérprete de comandos que actúa como interfaz entre el usuario y el kernel del sistema operativo.

**Funciones principales del shell:**
- **Intérprete de comandos**: Ejecuta comandos del usuario
- **Lenguaje de programación**: Permite crear scripts
- **Entorno de trabajo**: Gestiona variables y configuración de sesión
- **Interfaz con el kernel**: Traduce comandos a llamadas al sistema

**Proceso de interpretación:**
1. Lee el comando ingresado
2. Analiza la sintaxis (parsing)
3. Expande variables y comodines
4. Localiza el comando en el PATH
5. Crea un proceso hijo (fork)
6. Ejecuta el comando (exec)
7. Espera finalización y muestra resultado

### 6.2 Tipos de Shell

**Shells más comunes en Linux:**

1. **Bash (Bourne Again Shell)**:
   - Shell por defecto en la mayoría de distribuciones
   - Compatible con sh original
   - Características avanzadas de scripting
   - Autocompletado y historial de comandos

2. **Sh (Bourne Shell)**:
   - Shell original de UNIX
   - Sintaxis básica que otros shells mantienen
   - Presente en todos los sistemas UNIX/Linux

3. **Zsh (Z Shell)**:
   - Altamente personalizable
   - Mejoras en autocompletado
   - Temas y frameworks (Oh My Zsh)

4. **Fish (Friendly Interactive Shell)**:
   - Diseñado para ser user-friendly
   - Autosugerencias inteligentes
   - Sintaxis de colores automática

5. **Dash**:
   - Shell minimalista y rápido
   - Usado como /bin/sh en Debian/Ubuntu
   - Optimizado para scripts

### 6.3 Variables de Entorno

Las variables de entorno son valores dinámicos que afectan el comportamiento de procesos y programas.

**Variables importantes:**
- **PATH**: Directorios donde buscar comandos ejecutables
- **HOME**: Directorio personal del usuario
- **USER/LOGNAME**: Nombre del usuario actual
- **SHELL**: Shell por defecto del usuario
- **PWD**: Directorio de trabajo actual
- **LANG/LC_***: Configuración de idioma y localización
- **PS1**: Formato del prompt del shell
- **LD_LIBRARY_PATH**: Rutas para bibliotecas dinámicas

**Ámbito de las variables:**
- **Variables locales**: Solo disponibles en el shell actual
- **Variables de entorno**: Heredadas por procesos hijos
- **Variables de shell**: Configuración específica del shell

### 6.4 Redirección y Tuberías

La redirección y las tuberías son mecanismos fundamentales para el flujo de datos entre comandos.

**Descriptores de archivo estándar:**
- **stdin (0)**: Entrada estándar (teclado por defecto)
- **stdout (1)**: Salida estándar (pantalla por defecto)  
- **stderr (2)**: Salida de errores (pantalla por defecto)

**Operadores de redirección:**
- **>**: Redirige stdout a archivo (sobrescribe)
- **>>**: Redirige stdout a archivo (añade)
- **<**: Redirige stdin desde archivo
- **2>**: Redirige stderr a archivo
- **&>**: Redirige stdout y stderr
- **2>&1**: Redirige stderr a donde apunte stdout

**Tuberías (Pipes):**
- **|**: Conecta stdout de un comando con stdin del siguiente
- Permite encadenar comandos creando pipelines
- Ejemplo conceptual: `comando1 | comando2 | comando3`

**Here documents:**
- **<<**: Permite introducir múltiples líneas como entrada
- **<<<**: Here string, una línea como entrada

---

## 7. GESTIÓN DE SOFTWARE

### 7.1 Concepto de Paquetes

Un paquete es una unidad de software precompilada que contiene archivos ejecutables, configuración, documentación y metadatos necesarios para instalar un programa.

**Componentes de un paquete:**
- **Binarios**: Archivos ejecutables del programa
- **Bibliotecas**: Librerías compartidas necesarias
- **Archivos de configuración**: Configuración por defecto
- **Documentación**: Manuales, README, licencias
- **Metadatos**: Información sobre versión, dependencias, descripción
- **Scripts**: Pre/post instalación, eliminación

**Ventajas del sistema de paquetes:**
- Instalación y desinstalación automatizada
- Gestión de dependencias
- Actualizaciones centralizadas
- Verificación de integridad
- Control de versiones

### 7.2 Gestores de Paquetes

Los gestores de paquetes automatizan la instalación, actualización y eliminación de software.

**Niveles de gestión:**

1. **Gestores de bajo nivel**:
   - **dpkg** (Debian/Ubuntu): Maneja paquetes .deb
   - **rpm** (RedHat/Fedora): Maneja paquetes .rpm
   - Funciones: Instalar, eliminar, consultar paquetes locales
   - No resuelven dependencias automáticamente

2. **Gestores de alto nivel**:
   - **APT** (Debian/Ubuntu): Advanced Package Tool
   - **YUM/DNF** (RedHat/Fedora): Yellowdog Updater Modified
   - **Zypper** (openSUSE)
   - **Pacman** (Arch Linux)
   - Funciones: Resuelven dependencias, acceden a repositorios

**Formatos de paquetes principales:**
- **.deb**: Debian y derivados
- **.rpm**: RedHat y derivados  
- **.tar.xz**: Arch Linux
- **Snap**: Paquetes universales con dependencias incluidas
- **Flatpak**: Aplicaciones sandboxed
- **AppImage**: Aplicaciones portables

### 7.3 Dependencias

Las dependencias son otros paquetes que un software necesita para funcionar correctamente.

**Tipos de dependencias:**
- **Obligatorias**: Imprescindibles para el funcionamiento
- **Recomendadas**: Mejoran funcionalidad pero no son críticas
- **Sugeridas**: Funcionalidades opcionales adicionales
- **Conflictos**: Paquetes incompatibles entre sí

**Resolución de dependencias:**
1. El gestor analiza los requisitos del paquete
2. Busca las dependencias en los repositorios
3. Calcula el árbol de dependencias completo
4. Descarga e instala en orden correcto
5. Configura los paquetes instalados

**Problemas comunes:**
- **Dependency hell**: Conflictos complejos entre versiones
- **Dependencias circulares**: A depende de B, B depende de A
- **Bibliotecas huérfanas**: Dependencias ya no necesarias

### 7.4 Repositorios

Los repositorios son servidores que almacenan colecciones de paquetes de software organizados y accesibles.

**Tipos de repositorios:**
- **Oficiales**: Mantenidos por la distribución
- **Comunidad**: Mantenidos por la comunidad
- **Terceros**: PPA, COPR, AUR
- **Locales**: Mirrors o repositorios privados

**Estructura de repositorios:**
- **Índices**: Listas de paquetes disponibles con metadatos
- **Paquetes**: Archivos de software comprimidos
- **Firmas**: Verificación de integridad y autenticidad
- **Metadatos**: Información sobre versiones y dependencias

**Gestión de repositorios:**
- Archivos de configuración (/etc/apt/sources.list, /etc/yum.repos.d/)
- Prioridades entre repositorios
- Actualización de índices
- Verificación de firmas GPG

---

## 8. SERVICIOS Y SYSTEMD

### 8.1 Concepto de Servicio

Un servicio es un programa que se ejecuta en segundo plano, generalmente iniciado al arranque del sistema, proporcionando funcionalidad continua.

**Características de los servicios:**
- Ejecución en background sin interacción directa
- Inicio automático al arrancar el sistema
- Gestión centralizada (start, stop, restart, status)
- Logs centralizados
- Respuesta a señales del sistema

**Tipos de servicios:**
- **Servicios de red**: SSH, HTTP, FTP, DNS
- **Servicios del sistema**: Cron, logging, printing
- **Servicios de base de datos**: MySQL, PostgreSQL
- **Servicios de monitorización**: Monitoring, backup

### 8.2 Init System

El sistema init es el primer proceso (PID 1) que se ejecuta en el arranque y es responsable de inicializar el sistema.

**Evolución de los sistemas init:**

1. **SysV Init** (tradicional):
   - Basado en scripts de shell
   - Arranque secuencial
   - Runlevels numéricos (0-6)
   - Scripts en /etc/init.d/

2. **Upstart**:
   - Arranque basado en eventos
   - Paralelización parcial
   - Usado en Ubuntu antiguas versiones

3. **Systemd** (moderno):
   - Arranque paralelo
   - Gestión unificada de servicios
   - Dependencias complejas
   - Estándar actual en mayoría de distribuciones

### 8.3 Systemd

Systemd es el sistema init y gestor de servicios moderno adoptado por la mayoría de distribuciones Linux actuales.

**Componentes de systemd:**
- **systemd**: Gestor del sistema y servicios
- **systemctl**: Comando para gestionar servicios
- **journald**: Sistema de logging
- **logind**: Gestión de sesiones de usuario
- **networkd**: Gestión de red (opcional)
- **resolved**: Resolución DNS (opcional)

**Unidades (Units) en systemd:**
- **.service**: Servicios del sistema
- **.socket**: Sockets de comunicación
- **.target**: Agrupación de unidades (similar a runlevels)
- **.timer**: Tareas programadas (como cron)
- **.mount**: Puntos de montaje
- **.path**: Monitorización de rutas

**Estructura de un archivo .service:**
```ini
[Unit]
Description=Descripción del servicio
After=network.target
Requires=dependency.service

[Service]
Type=simple|forking|oneshot|notify
ExecStart=/ruta/al/ejecutable
Restart=on-failure
User=usuario

[Install]
WantedBy=multi-user.target
```

**Estados de servicios:**
- **Active (running)**: Ejecutándose normalmente
- **Active (exited)**: Proceso completado exitosamente
- **Inactive (dead)**: No ejecutándose
- **Failed**: Falló al iniciar o terminó con error
- **Activating/Deactivating**: En transición

### 8.4 Runlevels y Targets

Los runlevels son estados de operación del sistema que definen qué servicios están activos.

**Runlevels tradicionales (SysV):**
- **0**: Halt (apagado)
- **1**: Single user (modo rescate)
- **2**: Multi-user sin red
- **3**: Multi-user con red (sin GUI)
- **4**: No usado/personalizable
- **5**: Multi-user con GUI
- **6**: Reboot

**Targets en systemd (equivalentes):**
- **poweroff.target**: Runlevel 0
- **rescue.target**: Runlevel 1
- **multi-user.target**: Runlevel 3
- **graphical.target**: Runlevel 5
- **reboot.target**: Runlevel 6

**Targets especiales:**
- **default.target**: Target por defecto al arrancar
- **emergency.target**: Modo emergencia mínimo
- **network.target**: Red configurada
- **basic.target**: Sistema básico listo

---

## 9. CONCEPTOS DE RED EN LINUX

### 9.1 Stack TCP/IP en Linux

Linux implementa completamente el modelo TCP/IP de cuatro capas para comunicaciones de red.

**Capas del modelo TCP/IP:**

1. **Capa de Enlace** (Link Layer):
   - Ethernet, Wi-Fi, PPP
   - Direcciones MAC
   - ARP (Address Resolution Protocol)

2. **Capa de Internet** (Internet Layer):
   - Protocolo IP (IPv4/IPv6)
   - ICMP (mensajes de control)
   - Enrutamiento de paquetes

3. **Capa de Transporte** (Transport Layer):
   - TCP: Transmisión confiable, orientada a conexión
   - UDP: Transmisión no confiable, sin conexión
   - Control de flujo y congestión

4. **Capa de Aplicación** (Application Layer):
   - HTTP/HTTPS, SSH, FTP, DNS
   - Protocolos específicos de aplicaciones

**Implementación en el kernel:**
- Netfilter: Framework para filtrado de paquetes
- Socket API: Interfaz para programación de red
- Network namespaces: Aislamiento de stack de red

### 9.2 Interfaces de Red

Una interfaz de red es el punto de conexión entre el sistema y una red.

**Tipos de interfaces:**

1. **Físicas**:
   - **ethX/enpXsY**: Ethernet cableada
   - **wlanX/wlpXsY**: Wireless (Wi-Fi)
   - Nomenclatura: Predictable Network Interface Names

2. **Virtuales**:
   - **lo**: Loopback (127.0.0.1)
   - **tunX/tapX**: Túneles VPN
   - **vethX**: Virtual Ethernet (contenedores)
   - **brX**: Bridge (puente de red)
   - **bondX**: Bonding (agregación de enlaces)

**Información de interfaces:**
- Dirección IP (IPv4/IPv6)
- Máscara de subred
- Dirección MAC (hardware)
- Estado (UP/DOWN)
- Estadísticas de tráfico

### 9.3 Configuración de Red

La configuración de red puede ser estática o dinámica, temporal o persistente.

**Métodos de configuración:**

1. **Archivos de configuración**:
   - **/etc/network/interfaces** (Debian/Ubuntu tradicional)
   - **/etc/sysconfig/network-scripts/** (RedHat/CentOS)
   - **Systemd-networkd**: Configuración moderna
   - **NetworkManager**: Gestión dinámica

2. **Configuración IP**:
   - **Estática**: IP fija definida manualmente
   - **Dinámica (DHCP)**: IP asignada automáticamente
   - **APIPA**: Auto-configuración (169.254.x.x)

**Elementos de configuración:**
- **Dirección IP**: Identificador único en la red
- **Máscara de red**: Define el segmento de red
- **Gateway**: Puerta de enlace por defecto
- **DNS**: Servidores de resolución de nombres

**Archivos importantes:**
- **/etc/hostname**: Nombre del host
- **/etc/hosts**: Resolución estática de nombres
- **/etc/resolv.conf**: Configuración DNS
- **/etc/nsswitch.conf**: Orden de resolución de nombres

### 9.4 Firewall y iptables

El firewall en Linux se implementa mediante Netfilter en el kernel, gestionado tradicionalmente con iptables.

**Conceptos de Netfilter/iptables:**

**Tablas principales:**
- **filter**: Filtrado de paquetes (tabla por defecto)
- **nat**: Network Address Translation
- **mangle**: Modificación de paquetes
- **raw**: Procesamiento de paquetes antes del connection tracking

**Cadenas (Chains) en tabla filter:**
- **INPUT**: Paquetes destinados al sistema local
- **OUTPUT**: Paquetes originados en el sistema local
- **FORWARD**: Paquetes que atraviesan el sistema

**Políticas y reglas:**
- **Políticas por defecto**: ACCEPT, DROP, REJECT
- **Reglas**: Condiciones y acciones específicas
- **Orden de evaluación**: Primera coincidencia gana

**Flujo de paquetes:**
```
Entrada → PREROUTING → ┬→ INPUT → Proceso Local
                       │
                       └→ FORWARD → POSTROUTING → Salida
```

**Herramientas modernas:**
- **firewalld**: Gestión dinámica de firewall (RedHat/Fedora)
- **ufw**: Uncomplicated Firewall (Ubuntu)
- **nftables**: Reemplazo moderno de iptables

---

## 10. FUNDAMENTOS DE SEGURIDAD

### 10.1 Modelo de Seguridad de Linux

Linux implementa múltiples capas de seguridad basadas en el principio de menor privilegio.

**Principios fundamentales:**

1. **Discretionary Access Control (DAC)**:
   - Control basado en propietario
   - Permisos tradicionales (rwx)
   - El propietario decide el acceso

2. **Principio de menor privilegio**:
   - Procesos ejecutan con mínimos privilegios necesarios
   - Escalación de privilegios solo cuando es necesaria
   - Separación de privilegios entre servicios

3. **Separación de espacios**:
   - Espacio de kernel vs espacio de usuario
   - Memoria protegida entre procesos
   - Namespaces para aislamiento

**Mecanismos de seguridad básicos:**
- **Autenticación**: Verificación de identidad (login, su, sudo)
- **Autorización**: Control de acceso a recursos
- **Auditoría**: Registro de eventos de seguridad
- **Integridad**: Verificación de no modificación

### 10.2 SELinux y AppArmor

Son sistemas de Mandatory Access Control (MAC) que proporcionan seguridad adicional sobre DAC.

**SELinux (Security-Enhanced Linux):**

Desarrollado por NSA, proporciona control de acceso obligatorio basado en políticas.

**Conceptos clave:**
- **Contextos de seguridad**: Etiquetas en archivos y procesos
- **Políticas**: Reglas que definen accesos permitidos
- **Dominios**: Contextos para procesos
- **Tipos**: Contextos para archivos

**Modos de operación:**
- **Enforcing**: Aplica políticas y deniega accesos no autorizados
- **Permissive**: Registra violaciones pero no las bloquea
- **Disabled**: SELinux desactivado

**AppArmor:**

Alternativa a SELinux, más simple de configurar, usado en Ubuntu/SUSE.

**Características:**
- Basado en rutas de archivos
- Perfiles por aplicación
- Más fácil de configurar que SELinux
- Modos: Enforce y Complain

### 10.3 Auditoría y Logs

El sistema de logging es fundamental para la seguridad, monitorización y resolución de problemas.

**Sistemas de logging:**

1. **Syslog tradicional**:
   - Demonio rsyslog o syslog-ng
   - Archivos en /var/log/
   - Facilidades y prioridades

2. **Systemd journal**:
   - journald integrado con systemd
   - Logs binarios estructurados
   - Rotación automática
   - Búsquedas avanzadas

**Archivos de log importantes:**
- **/var/log/syslog o messages**: Log general del sistema
- **/var/log/auth.log o secure**: Autenticación y autorización
- **/var/log/kern.log**: Mensajes del kernel
- **/var/log/boot.log**: Mensajes de arranque
- **/var/log/dmesg**: Buffer de mensajes del kernel
- **/var/log/apache2/ o nginx/**: Logs de servidores web

**Auditoría con auditd:**
- Sistema de auditoría del kernel
- Registro detallado de eventos de seguridad
- Reglas personalizables
- Cumplimiento normativo (PCI-DSS, HIPAA)

### 10.4 Principios de Hardening

El hardening es el proceso de asegurar un sistema reduciendo su superficie de ataque.

**Medidas de hardening básicas:**

1. **Gestión de usuarios y accesos**:
   - Eliminar cuentas innecesarias
   - Contraseñas fuertes y políticas de cambio
   - Configurar sudo en lugar de acceso root directo
   - Limitar acceso SSH (sin root, con claves)

2. **Servicios y puertos**:
   - Deshabilitar servicios innecesarios
   - Cerrar puertos no utilizados
   - Configurar firewall restrictivo
   - Usar conexiones cifradas (SSH, HTTPS)

3. **Actualizaciones y parches**:
   - Mantener sistema actualizado
   - Aplicar parches de seguridad
   - Suscribirse a avisos de seguridad
   - Actualizaciones automáticas para parches críticos

4. **Sistema de archivos**:
   - Particiones separadas (/tmp, /var, /home)
   - Opciones de montaje seguras (noexec, nosuid)
   - Permisos restrictivos en archivos sensibles
   - Cifrado de particiones sensibles

5. **Kernel y boot**:
   - Parámetros de kernel seguros
   - Proteger GRUB con contraseña
   - Deshabilitar módulos innecesarios
   - Activar protecciones del kernel (ASLR, DEP)

6. **Monitorización**:
   - Sistemas de detección de intrusos (IDS)
   - Monitorización de integridad (AIDE, Tripwire)
   - Análisis de logs
   - Alertas de eventos sospechosos

**Herramientas de seguridad comunes:**
- **fail2ban**: Bloqueo automático de IPs maliciosas
- **rkhunter/chkrootkit**: Detección de rootkits
- **lynis**: Auditoría de seguridad
- **OSSEC**: HIDS (Host Intrusion Detection System)

---

## CONCLUSIÓN

Esta introducción a Linux ha cubierto los conceptos fundamentales necesarios para comprender la arquitectura y funcionamiento del sistema operativo. Los conocimientos aquí presentados son la base sobre la cual se construyen habilidades más avanzadas en administración de sistemas y, particularmente, en ciberseguridad.

**Próximos pasos recomendados:**
1. Práctica con comandos básicos en un entorno Linux
2. Profundización en scripting con Bash
3. Estudio de herramientas específicas de seguridad
4. Configuración y hardening de servicios
5. Análisis de logs y forense en Linux

La comprensión profunda de estos conceptos teóricos es esencial para poder aplicar medidas de seguridad efectivas, realizar análisis de vulnerabilidades y responder a incidentes de seguridad en entornos Linux.
