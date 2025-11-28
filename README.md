<div align="center">
  <img src="assets/banner.png" alt="Digital Forensics Banner" width="100%" />
</div>

<div align="center">
  <h1>🕵️‍♂️ Guía Maestra de Informática Forense y Respuesta a Incidentes</h1>
  <p>
    <strong>Tu referencia definitiva para herramientas, técnicas y procedimientos en DFIR.</strong>
  </p>
  <p>
    <img src="https://img.shields.io/badge/DFIR-Expert-00C7B7?style=for-the-badge&logo=linux&logoColor=white" alt="DFIR" />
    <img src="https://img.shields.io/badge/Forensics-Investigation-FF5555?style=for-the-badge&logo=windows&logoColor=white" alt="Forensics" />
    <img src="https://img.shields.io/badge/Security-Blue%20Team-BD93F9?style=for-the-badge&logo=security&logoColor=white" alt="Security" />
  </p>
</div>

<br/>

## 📑 Índice de Contenidos

1. [🛡️ Respuesta a incidentes de malware](#1-respuesta-a-incidentes-de-seguridad-de-malware)
2. [📨 Respuestas a incidentes de correo electrónico](#2-respuestas-a-incidentes-de-correo-electrónico)
3. [🌐 Respuesta a incidentes de red](#3-respuesta-a-incidentes-de-red)
4. [🕸️ Respuesta a incidentes de aplicaciones web](#4-respuesta-a-incidentes-de-aplicaciones-web)
5. [☁️ Respuesta a incidentes en la nube](#5-respuesta-a-incidentes-en-la-nube)
6. [📚 Recursos y Mejores Prácticas](#6-recursos-y-mejores-prácticas)

---

## 1. 🛡️ Respuesta a incidentes de seguridad de malware

### 1.1 🔎 Descripción general de la respuesta ante incidentes de malware

El **malware** es software malintencionado creado para dañar sistemas, robar información o dar control al atacante. Incluye **virus, gusanos, troyanos, rootkits, puertas traseras, ransomware, spyware, adware, botnets, keyloggers, crypters**, etc.

Sus efectos pueden incluir:

- 🕵️‍♂️ **Robo de datos personales o corporativos**
- 🐌 **Ralentización del sistema**
- ❌ **Borrado de información**
- ⚠️ **Fallos del sistema o del hardware**
- 🔁 **Uso del equipo infectado para atacar a otros**
- 📩 **Envío de spam o publicidad maliciosa**

---

### 🦠 Tipos principales de malware

| Tipo        | Descripción breve                                                                                   | Impacto típico                                   |
|-------------|------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| Troyano     |Se oculta dentro de programas legítimos y se activa con acciones del usuario.                       | Robo de datos, control remoto, instalación de más malware. |
| Puerta trasera (Backdoor) | Permite acceso remoto al sistema saltándose autenticación y controles de seguridad.           | Acceso persistente, movimiento lateral en la red. |
| Rootkit     | Modifica componentes del sistema operativo para ocultar la presencia del atacante.                  | Ocultación de malware, control total del sistema. |
| Ransomware  | Cifra archivos o bloquea el sistema y exige un rescate para restaurar el acceso.                    | Pérdida de disponibilidad, extorsión económica.   |
| Adware      | Muestra anuncios no deseados; puede redirigir a sitios maliciosos o descargar más malware.         | Molestias, riesgo de nuevas infecciones.          |
| Virus       | Se autorreplica infectando archivos y requiere acción del usuario para propagarse.                 | Corrupción o borrado de datos, inestabilidad del sistema. |
| Gusano      | Se propaga automáticamente por la red sin intervención humana.                                      | Saturación de red, propagación masiva, instalación de backdoors. |
| Spyware     | Espía la actividad del usuario (teclas, pantallas, sitios visitados, credenciales, etc.).         | Robo de credenciales, espionaje, violación de privacidad. |
| Botnet      | Red de equipos infectados controlados de forma centralizada por un atacante.                       | Ataques DDoS, envío de spam, distribución de malware. |
| Crypter     | Cifra/empaca el malware para ocultarlo de soluciones antivirus y sistemas de análisis.             | Evasión de detección, persistencia de otras amenazas. |

---

### 🧩 Componentes del malware

Los atacantes desarrollan malware combinando distintos componentes especializados que les permiten robar datos, modificar sistemas, instalar puertas traseras o simplemente propagarse de forma encubierta. Estos elementos ayudan al malware a **evadir detección**, **infectar**, **ocultarse** y **ejecutar acciones maliciosas**.

#### 🔧 Componentes principales del malware

| Componente         | Descripción                                                                                                                |
|--------------------|----------------------------------------------------------------------------------------------------------------------------|
| Crypter            | Oculta el malware cifrándolo para evitar que los antivirus lo detecten o analicen.                                         |
| Downloader         | Troyano que descarga desde Internet más malware o archivos maliciosos al sistema comprometido.                            |
| Dropper            | Instala el malware de forma encubierta y puede traer archivos adicionales necesarios para la infección.                   |
| Exploit            | Código que aprovecha vulnerabilidades para comprometer el sistema, espiar o instalar malware.                             |
| Injector           | Inyecta código malicioso o exploits dentro de procesos legítimos para ocultar su actividad.                               |
| Obfuscator         | Oculta o transforma el código malicioso para dificultar su análisis y detección.                                          |
| Packer             | Comprime y transforma el malware a un formato ilegible para complicar su identificación.                                   |
| Payload (carga útil)| Parte del malware que ejecuta la acción maliciosa, como borrar archivos, abrir puertos o modificar configuraciones.      |
| Código malicioso   | Instrucciones base del malware (subprogramas Java, ActiveX, complementos de navegador, contenido incrustado, etc.).       |

---

### 🌍 Métodos de propagación de malware

Los métodos más comunes que utilizan los atacantes para infectar un sistema con malware incluyen:

- 💬 Aplicaciones de mensajería instantánea  
- 💾 Medios de hardware portátiles / dispositivos extraíbles  
- 🌐 Errores de software del navegador y correo electrónico  
- 🩹 Administración de parches insegura  
- 🎭 Aplicaciones falsas / señuelo  
- ⚠️ Sitios no confiables y aplicaciones web / software gratuito  
- 📥 Descarga de archivos basados en Internet  
- 📎 Archivos adjuntos de correo electrónico  
- 🌐 Propagación de red  
- 🔗 Servicios para compartir archivos (NetBIOS, FTP, SMB)  
- 🧬 Instalación por otros malwares  
- 📡 Bluetooth y redes inalámbricas  
- 🧠 Ejecutables infectados, DLL, macros, JavaScript y documentos  

---

### 🌐 Técnicas comunes que utilizan los atacantes para distribuir software malicioso en la Web

Los atacantes utilizan varias técnicas para difundir malware aprovechando fallos, ingeniería social y manipulación de contenidos:

- 🎯 **Black Hat SEO**: manipulan motores de búsqueda usando técnicas SEO agresivas para posicionar páginas que contienen malware.  
- 🖱️ **Clickjacking social**: engañan a usuarios para que hagan clic en enlaces infectados dentro de sitios aparentemente legítimos.  
- 🏦 **Spear phishing web**: crean páginas falsas que imitan instituciones reales para robar contraseñas y datos bancarios.  
- 📢 **Malvertising**: insertan anuncios maliciosos en plataformas de publicidad legítimas para infectar a usuarios.  
- 🕸️ **Sitios legítimos comprometidos**: usan webs vulnerables para instalar malware cuando el usuario las visita.  
- ⚙️ **Descargas automáticas (drive-by downloads)**: explotan vulnerabilidades del navegador para instalar malware sin interacción del usuario.  
- 📧 **Correos con malware**: envían emails con adjuntos o enlaces infectados; es uno de los métodos más comunes hoy en día.

---

### 📚 Caso de estudio

> 💼 **Desafío**  
> Maria White, directora administrativa de la organización, encontró su sistema inaccesible tras un ataque de ransomware. El equipo de respuesta descubrió que más de **30 sistemas** estaban afectados.

> 🛠️ **Proceso**  
> - Aislaron los sistemas afectados de la red.  
> - Informaron a Microsoft del problema.  
> - Extrajeron discos y datos para analizarlos en una sandbox.  
> - Descubrieron que el malware cifraba todos los archivos del sistema.  

> ✅ **Solución**  
> - Parcharon los sistemas con actualizaciones de Microsoft.  
> - Analizaron el malware (cadenas, PE, dependencias).  
> - Descubrieron que usaba una solicitud de dominio como clave de descifrado.  
> - Simularon la respuesta del dominio con **iNetSim** y lograron desbloquear los sistemas.  
> - Aplicaron la técnica a todos los equipos y recomendaron **políticas de actualización automática**.

---

### 1.2 🧰 Preparación para manejar los incidentes de malware

#### 🛠️ Herramientas de software

El kit de herramientas de malware debe incluir:

- Una computadora portátil con herramientas de análisis  
- Dispositivos para copias de seguridad  
- Hardware y cables de red  
- Dispositivos extraíbles (DVD, USB) para recopilar y transferir evidencias  

**Herramientas recomendadas para detección y análisis de malware:**

- **Virtualización**: VirtualBox, VMware vSphere Hypervisor, Microsoft Virtual Server  
- **Imágenes forenses**: FTK Imager  
- **Análisis de PE**: PEView, PeStudio, PEiD, PEBrowse  
- **Snapshots de host**: Regshot, RegMon, FileMon, Total Commander  
- **Volcado de memoria**: Scylla, OllyDumpEx  
- **Rastreo de red**: Wireshark  
- **Simulación de red**: iNetSim  
- **Procesos y monitorización**: Process Monitor, Process Explorer  
- **Hex editors**: HexEditor, 010 Editor, Hexinator  
- **Depuración**: OllyDbg, IDA Pro  
- **Búsqueda de cadenas**: ResourcesExtract, Bintext, Hex Workshop  
- **Dependencias**: Dependency Walker  

**Herramientas de máquina virtual:**

- Hyper-V  
- Parallels Desktop  
- Boot Camp  

**Captura de pantalla y grabación:**

- SnagIt, Jing, Camtasia, Ezvid  

**Simulación de red e Internet:**

- ns-3, Riverbed Modeler, QualNet  

**Imágenes y backup del SO:**

- Genie Backup Manager Pro  
- Macrium Reflect Server  
- R-Drive Image  
- O&O DiskImage  

---

### 1.3 🛰️ Detección de incidentes de malware

### 🚨 Indicaciones de incidentes de malware

El malware se propaga muy rápido dentro de una organización, por lo que es crucial **detectarlo pronto** para limitar los equipos infectados y reducir el esfuerzo de recuperación.

Algunos indicadores:

- Flujos de tráfico de red anormales  
- Correos rebotados inexplicables  
- Ventanas emergentes, alertas y anuncios irrelevantes  
- Registros con intentos de escaneo de puertos o acceso no autorizado  
- Modificación, eliminación o reubicación de archivos  
- Pantallas azules (BSOD)  
- Congelamientos, apagados y bloqueos repentinos  
- Ralentización general del sistema  
- Incapacidad para instalar actualizaciones  
- Programas de seguridad deshabilitados  
- Cambios extraños en configuración del navegador  
- Programas no aprobados que se inician solos  
- Envío masivo de correos o publicaciones no deseadas  
- Cuentas de usuario desconocidas  
- Reinicios inesperados  
- Movimiento extraño del ratón o teclado congelado  
- Alertas antivirus constantes  
- Archivos/carpetas que desaparecen  
- Falta de espacio en disco sin motivo aparente  
- Pop-ups y anuncios no deseados  

*(Lista resumida)*

---

### 🧪 Técnicas de detección de malware

Tras los primeros avisos de actividad sospechosa, el equipo de respuesta debe:

- Analizar red y sistemas para encontrar archivos maliciosos.  
- Verificar si el malware se ha propagado a otros dispositivos.  
- Identificar tipo de malware, comportamiento, zonas afectadas y firma.  

Técnicas principales:

- 🔄 **Análisis dinámico / sistema en vivo**: analizar sistemas en ejecución.  
- 🧱 **Análisis estático / volcado de memoria**: revisar binarios y dumps.  
- 📊 **Análisis de intrusiones**: revisar logs, SIEM, IDS, firewalls.

Se recomienda combinar las tres para entender mejor la funcionalidad del malware.

---

### 🧪 Técnicas de detección de malware: sistema en vivo / análisis dinámico

El **análisis dinámico** (o de sistema en vivo) detecta malware basándose en **lo que hace** dentro del sistema:

- Archivos creados o modificados  
- Puertos usados  
- Procesos iniciados  
- Cambios de configuración  
- Conexiones a URLs sospechosas  

Se centra en monitorizar:

- **Supervisión de puertos**  
- **Supervisión de procesos**  
- **Supervisión del registro**  
- **Servicios de Windows**  
- **Programas de inicio**  
- **Registro de eventos**  
- **Instalaciones**  
- **Archivos y carpetas**  
- **Controladores de dispositivo**  
- **Tráfico de red**  
- **Resolución de DNS**  
- **Llamadas a API**  
- **Tareas programadas**  
- **Actividad del navegador**

---

### 🌐 Análisis del sistema en vivo: monitoreo de puertos

El malware puede **corromper el sistema** y **abrir puertos de entrada/salida** para comunicarse con servidores remotos, propagar infecciones o crear **puertas traseras**.  
Estos puertos abiertos actúan como canales de control y permiten que el atacante mantenga acceso al sistema.  
Por ello, **identificar puertos sospechosos** es una técnica clave en el análisis dinámico del sistema.

Durante un análisis en vivo, los respondedores pueden usar herramientas de monitoreo para observar:
- Protocolo
- Dirección local / remota
- Estado de la conexión
- PID y proceso asociado

#### 🛠️ Herramientas principales

#### **1. netstat (línea de comandos)**  
Muestra:
- Conexiones TCP activas  
- Puertos TCP/UDP en escucha  
- Estadísticas de red (Ethernet, IP, TCP, UDP)  
- Tabla de enrutamiento  

**Sintaxis:**

netstat [-a] [-e] [-n] [-o] [-p protocolo] [-r] [-s] [intervalo]

**Parámetros útiles:**
- `-a` → mostrar todas las conexiones y puertos en escucha  
- `-e` → estadísticas de Ethernet  
- `-n` → mostrar direcciones y puertos numéricos  
- `-o` → incluir el PID del proceso  
- `-p` → filtrar por protocolo (TCP, UDP, TCPv6, UDPv6…)  
- `-s` → estadísticas por protocolo  
- `-r` → tabla de enrutamiento  

**Ejemplo:**

netstat -an

#### **2. TCPView (GUI)**  
Fuente: https://docs.microsoft.com  

TCPView ofrece una vista gráfica de:
- Puntos finales TCP/UDP  
- Direcciones locales y remotas  
- Estado de cada conexión  
- Resolución DNS automática  

Incluye **TCPVCon**, versión por línea de comandos.

### 📦 Otras herramientas de monitoreo de puertos

| Herramienta            | Enlace |
|------------------------|--------|
| CurrPorts              | https://www.nirsoft.net |
| dotcom-monitor         | https://www.dotcom-monitor.com |
| PortExpert             | http://www.kcsoftwares.com |
| PRTG Network Monitor   | https://www.paessler.com |
| Nagios Port Monitor    | https://exchange.nagios.org |

---

### 🌐 Análisis del sistema en vivo: monitoreo de procesos

El malware puede entrar en un sistema a través de archivos descargados (imágenes, música, videos, etc.) y **camuflarse como procesos o servicios legítimos** de Windows para evitar su detección.  
Algunos malwares se inyectan en procesos comunes como `explorer.exe` o navegadores web utilizando técnicas PE o métodos estilo **rootkit**, lo que les permite evadir antivirus y firewalls.

El **monitoreo de procesos** permite identificar estos comportamientos analizando:
- Procesos iniciados por el malware
- Procesos padre/hijo
- DLL cargadas
- Funciones ejecutadas
- Cambios antes/después de ejecutar el malware

Este enfoque ayuda a detectar:
- Procesos ocultos o disfrazados  
- Inyección de código  
- Actividad sospechosa en procesos legítimos  

Herramientas como **Process Monitor** son clave para este tipo de análisis.

#### 🛠️ Process Monitor (Sysinternals)

Fuente: https://docs.microsoft.com  

**Process Monitor** muestra en tiempo real:
- Actividad del sistema de archivos  
- Actividad del registro (Registry)  
- Procesos e hilos (threads)  
- Eventos del sistema  

Combina las funciones de Filemon y Regmon con mejoras avanzadas.

**Características destacadas:**
- Captura detallada de entradas/salidas de cada operación  
- Filtros no destructivos  
- Captura de *call stacks* de hilos  
- Información completa del proceso (ruta, usuario, PID, línea de comandos)  
- Columnas configurables  
- Registro de millones de eventos  
- Vista jerárquica de procesos  
- Formato de registro propio para análisis posterior  

### 🔍 Otras herramientas de monitoreo de procesos

| Herramienta | Enlace |
|------------|--------|
| Process Explorer | https://docs.microsoft.com |
| M/Monit | https://mmonit.com |
| ESET SysInspector | https://www.eset.com |
| System Explorer | http://systemexplorer.net |
| Security Task Manager | https://www.neuber.com |
| HiJackThis | https://sourceforge.net |
| YAPM (Yet Another Process Monitor) | http://yaprocmon.sourceforge.net |
| Process Network Monitor | https://securityxploded.com |
| OpManager | https://www.manageengine.com |

---

### 🧩 Análisis del sistema en vivo: Monitoreo del Registro de Windows

El **Registro de Windows** almacena configuraciones del sistema y programas.  
Cuando un malware se instala, suele **modificar el registro** para:

- Garantizar su ejecución automática al iniciar el sistema  
- Mantener persistencia  
- Ejecutar acciones maliciosas sin intervención del usuario  

Estos cambios pueden provocar síntomas como:
- Ralentización del sistema  
- Aparición constante de anuncios  
- Programas que se inician solos  

### 📌 Claves del registro usadas frecuentemente por malware

Windows ejecuta automáticamente instrucciones ubicadas en:

Run
RunServices
RunOnce
RunServicesOnce
HKEY_CLASSES_ROOT\exefile\shell\open\command "%1" %*

Los atacantes insertan entradas maliciosas en estas rutas para mantener persistencia y ejecutar el malware en cada arranque.

Para detectarlo, es importante revisar estas claves y buscar **entradas desconocidas o sospechosas**.

### 🛠️ Herramientas para monitorear y analizar el registro

#### **Jv16 Power Tools 2017**
Fuente: https://www.macecraft.com  
Software de utilidad que permite:

- Escanear y monitorear el registro  
- Detectar entradas creadas por malware  
- Limpiar restos, entradas corruptas y archivos temporales  
- Optimizar el sistema corrigiendo errores del registro  

### 🔍 Otras herramientas de monitoreo del registro

| Herramienta | Enlace |
|------------|--------|
| Regshot | https://sourceforge.net |
| Reg Organizer | https://www.chemtable.com |
| Registry Viewer | https://accessdata.com |
| RegScanner | http://www.nirsoft.net |
| Registrar Registry Manager | https://www.resplendence.com |
| Active Registry Monitor | https://www.devicelock.com |
| MJ Registry Watcher | https://www.jacobsm.com |
| Buster Sandbox Analyzer | https://bsa.isoftware.nl |

---

### 🧩 Monitoreo de servicios de Windows para detectar malware

Los atacantes suelen diseñar malware que **se instala y ejecuta como un servicio de Windows**, aprovechando que los servicios se ejecutan en segundo plano y pasan desapercibidos.  
Esto les permite:

- Mantener persistencia  
- Ejecutar acciones maliciosas sin intervención del usuario  
- Controlar el sistema de forma remota  
- Ejecutarse con privilegios elevados (como `SYSTEM`)  

El malware también cambia el nombre de sus procesos/servicios para parecer legítimos, e incluso usa técnicas **rootkit** para ocultarse manipulando claves como:

HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services

Detectar servicios maliciosos es fundamental en un análisis dinámico o de respuesta a incidentes.

### 🛠️ Herramienta principal: Windows Service Manager (SrvMan)

Fuente: http://tools.sysprogs.org  

SrvMan permite visualizar, crear, eliminar y gestionar servicios de Windows, tanto desde GUI como desde línea de comandos.  
Útil para identificar servicios sospechosos generados por malware.

#### 📌 Comandos principales

**Crear un servicio**

srvman.exe add <file.exe/file.sys> [service name] [display name] [/type:<service type>] [/start:<start mode>] [/interactive:no] [/overwrite:yes]

**Eliminar un servicio**

srvman.exe delete <service name>

**Iniciar / detener / reiniciar servicios**

srvman.exe start <service name> [/nowait] [/delay:<msec>]
srvman.exe stop <service name> [/nowait] [/delay:<msec>]
srvman.exe restart <service name> [/delay:<msec>]

**Instalar y ejecutar un driver**

srvman.exe run <driver.sys> [service name] [/copy:yes] [/overwrite:no] [/stopafter:<msec>]

### 🔍 Otras herramientas de monitoreo de servicios

| Herramienta | Enlace |
|------------|--------|
| Advanced Windows Service Manager | https://securityxploded.com |
| Netwrix Service Monitor | https://www.netwrix.com |
| AnVir Task Manager | https://www.anvir.com |
| Service+ | https://www.activeplus.com |
| Easy Windows Service Manager | https://archive.codeplex.com |
| Nagios XI | https://www.nagios.com |
| Windows Service Monitor | https://www.manageengine.com |
| PC Services Optimizer | https://www.smartpcutilities.com |
| SMART Utility | https://www.volitans-software.com |

---

### 🚀 Análisis del sistema en vivo: supervisión de programas de inicio 

Muchos tipos de malware se añaden al **inicio automático del sistema** para ejecutarse cada vez que Windows arranca.  
Modificar el startup les permite mantener **persistencia**, ejecutar acciones maliciosas desde el primer segundo y evadir la detección.

Por eso, revisar manualmente los programas de inicio o utilizar herramientas especializadas como **Autoruns para Windows** es fundamental en un análisis dinámico o durante una respuesta a incidentes.

---

## 🔎 Pasos para detectar manualmente malware oculto en el inicio

### **1️⃣ Revisar las entradas del registro relacionadas con el inicio**

Los programas y drivers configurados para ejecutarse en el arranque pueden encontrarse en varias claves del registro.

#### 📌 *Windows Startup*

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\RunOnce

#### 📌 *Explorer Startup*

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Shell Folders, Common Startup
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders, Common Startup
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Shell Folders, Startup
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\User Shell Folders, Startup

#### 📌 *Internet Explorer Startup*

HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\URLSearchHooks
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Internet Explorer\Toolbar
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Internet Explorer\Extensions
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\MenuExt

### **2️⃣ Revisar controladores cargados automáticamente**
Verificar drivers en:

C:\Windows\System32\drivers

### **3️⃣ Revisar configuración de arranque (boot.ini/bcd)**

Usar:

bcdedit

para listar las entradas del gestor de arranque.

### **4️⃣ Verificar servicios que inician automáticamente**

Abrir:

services.msc

Ordenar por *Tipo de inicio* y revisar servicios configurados como **Automático**, especialmente si no se reconocen.

### **5️⃣ Revisar carpetas de inicio**

Carpetas que ejecutan programas al iniciar sesión:

C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup
C:\Users<User>\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup

Acceso rápido:
1. `Win + R`
2. Escribir `shell:startup`

## 🛠️ Herramienta principal: Autoruns para Windows

Fuente: https://docs.microsoft.com  

Autoruns permite ver absolutamente **todo lo que se ejecuta al inicio**, incluyendo:

- Programas
- Drivers
- Tareas programadas
- Servicios
- Extensiones del navegador
- DLLs cargadas
- Shell extensions
- Winlogon notifications

Además, la opción **"Hide Microsoft entries"** permite mostrar solo software de terceros, facilitando encontrar malware.

## 🧰 Otras herramientas para analizar inicio automático

| Herramienta | Enlace |
|-------------|--------|
| WinPatrol | https://www.winpatrol.com |
| Autorun Organizer | https://www.chemtable.com |
| Quick Startup | https://www.glarysoft.com |
| StartEd Pro | https://www.outertech.com |
| Chameleon Startup Manager | http://www.chameleon-managers.com |
| BootRacer | http://www.greatis.com |
| WinTools.net Startup Manager | http://www.wintools.net |
| EF StartUp Manager | http://www.efsoftware.com |
| PC Startup Master | https://www.smartpcutilities.com |
| CCleaner | https://www.piriform.com |
| Startup Delayer | https://www.r2.com.au |

---

### 📜 Monitoreo de registros de eventos (Event Logs) — Análisis del sistema en vivo

El análisis de registros (logs) es esencial para detectar actividad maliciosa en un sistema, ya que permite identificar:

- Troyanos y gusanos
- Intentos de acceso no autorizado
- Backdoors de día cero
- Fallos de autenticación
- Actividad anómala en servicios, aplicaciones o red

Los logs son una **fuente primaria de evidencia** en un análisis de malware o intrusión y permiten encontrar brechas de seguridad revisando eventos en firewalls, IDS/IPS, servidores web, autenticación, etc.

En Windows, los registros se revisan desde el **Visor de eventos (Event Viewer)**.

## 📁 Ubicación de los registros en Windows

### **Registros del sistema**

Inicio → Herramientas administrativas de Windows → Visor de eventos → Registros de Windows

### **Registros de seguridad**

Inicio → Herramientas administrativas de Windows → Visor de eventos → Registros de Windows → Seguridad

### **Registros de aplicaciones y servicios**

Inicio → Herramientas administrativas de Windows → Visor de eventos → Registros de aplicaciones y servicios

## ⌨️ Monitoreo del historial de comandos

Algunos malware usan el **Símbolo del sistema** para:

- Escalar privilegios  
- Acceder a rutas restringidas  
- Enumerar otros equipos  
- Ejecutar operaciones maliciosas  

Por ello, revisar el historial de comandos es crucial.

### 📌 Recuperar historial de comandos activo

doskey /history

Este comando muestra los comandos ejecutados en las ventanas de CMD abiertas.

## 🛠️ Herramienta principal: Loggly

Fuente: https://www.loggly.com  

Loggly detecta automáticamente formatos de registro y ofrece análisis estructurado en tiempo real. Permite monitorizar actividades sospechosas, correlacionar eventos y obtener visión completa del comportamiento del sistema.

### ⭐ Características principales
- Seguimiento del cumplimiento de SLA  
- Detección de anomalías y eventos sospechosos  
- Transmisión segura de datos de registro  
- Monitorización proactiva  
- Vista consolidada y en tiempo real de los logs  

## 🔍 Otras herramientas de análisis de registros

| Herramienta | Enlace |
|-------------|--------|
| SolarWinds Log & Event Manager | https://www.solarwinds.com |
| Netwrix Event Log Manager | https://www.netwrix.com |
| LogFusion | https://www.logfusion.ca |
| Alert Logic Log Manager | https://www.alertlogic.com |
| EventTracker Log Manager | https://www.eventtracker.com |
| Process Lasso Pro | https://bitsum.com |
| Splunk | https://www.splunk.com |

### 📦 Monitoreo de instalación — Análisis del sistema en vivo

Durante la instalación o desinstalación de software, el sistema puede dejar rastros como carpetas, archivos o entradas de registro que no se eliminan correctamente.  
El malware aprovecha esto para **instalarse en segundo plano**, dejando cambios que pasan desapercibidos.

El monitoreo de la instalación permite:

- Detectar instalaciones ocultas de malware  
- Identificar carpetas o archivos creados/modificados  
- Encontrar restos de aplicaciones que no deberían estar presentes  
- Ver qué recursos utiliza un programa (CPU, memoria, disco, etc.)

Herramientas especializadas permiten rastrear todos los cambios realizados por instaladores y detectan comportamiento anómalo.

## 🛠️ Herramienta principal: Mirekusoft Install Monitor

Fuente: https://www.mirekusoft.com  

Mirekusoft Install Monitor supervisa automáticamente los programas instalados en el sistema, registrando:

- Archivos creados o modificados  
- Entradas de registro generadas  
- Espacio en disco utilizado  
- Uso de CPU y memoria  
- Programas instalados en conjunto  

Es útil para identificar **instalaciones maliciosas**, restos de software y aplicaciones inesperadas.

## 🔍 Otras herramientas de monitoreo de instalación

| Herramienta | Enlace |
|-------------|--------|
| SysAnalyzer | https://www.aldeid.com |
| Advanced Uninstaller PRO | https://www.advanceduninstaller.com |
| Revo Uninstaller Pro | https://www.revouninstaller.com |
| Comodo Programs Manager | https://www.comodo.com |

### 📂 Monitoreo de archivos y carpetas — Análisis del sistema en vivo

El malware puede **crear, modificar o usar archivos y carpetas** del sistema para almacenar información, ejecutar código oculto o mantener persistencia.  
Por ello, es crucial analizar:

- Archivos creados por el malware  
- Carpetas modificadas recientemente  
- Archivos abiertos por usuarios remotos  
- Contenido del portapapeles  
- Archivos de captación previa (prefetch)  
- Controladores sin firmar  
- Hashes y cambios en la integridad de archivos  

La supervisión de estos elementos permite detectar comportamientos sospechosos y reconstruir la actividad del malware.

## 📌 Archivos abiertos por procesos remotos

Para ver archivos abiertos actualmente en el sistema:

openfiles

Útil para identificar archivos usados por malware o atacantes remotos.

## 📁 Archivos de captación previa (Prefetch)

Windows crea archivos *prefetch* para optimizar el inicio de aplicaciones.  
Estos archivos revelan:

- Programas ejecutados por el atacante  
- DLLs y rutas utilizadas  
- Tiempos de ejecución del malware  
- Herramientas usadas para borrar rastros (ej: CCleaner)

### Herramienta recomendada
**WinPrefetchView** — Permite visualizar y analizar archivos prefetch.

## 🛡️ Verificación de integridad y búsqueda de archivos sospechosos

Para detectar cambios en archivos del sistema, troyanos instalados o modificaciones maliciosas, se utilizan herramientas de integridad como:

- SIGVERIF  
- FCIV  
- Fastsum  
- WinMD5  
- Tripwire  

Estas herramientas comparan hashes, firmas y modificaciones para identificar manipulaciones.

## 🛠️ Herramienta principal: SIGVERIF

Fuente: https://support.microsoft.com  

**SIGVERIF** es una herramienta integrada en Windows que detecta controladores del sistema **no firmados**, los cuales pueden ser parte de rootkits o malware.

### Cómo usar SIGVERIF

1. Abrir `Inicio → Ejecutar`  
2. Escribir:

SIGVERIF

3. Clic en **Avanzado** → "Buscar otros archivos sin firmar"
4. Seleccionar:

C:\Windows\System32\drivers

5. Revisar el reporte generado:

C:\Windows\Sigverif.txt

## 🔍 Otras herramientas de verificación de integridad de archivos

| Herramienta | Enlace |
|-------------|--------|
| Tripwire File Integrity Manager | https://www.tripwire.com |
| Netwrix Auditor | https://www.netwrix.com |
| Verisys | https://www.ionx.co.uk |
| PA File Sight | https://www.poweradmin.com |
| CSP File Integrity Checker | https://www.cspsecurity.com |
| NNT Change Tracker | https://www.newnettechnologies.com |
| AFICK | http://afick.sourceforge.net |
| Fsum Frontend | http://fsumfe.sourceforge.net |
| OSSEC | https://www.ossec.net |
| IgorWare Hasher | https://www.igorware.com |

---

### 🧩 Monitoreo de controladores de dispositivos — Análisis del sistema en vivo

El malware puede instalarse **junto con controladores de dispositivos** descargados desde fuentes no confiables.  
Al ejecutarse como drivers, los atacantes obtienen:

- Mayor sigilo (los drivers se ejecutan a bajo nivel)
- Persistencia
- Capacidades de rootkit
- Ejecución antes de muchos servicios del sistema

Por ello, revisar los controladores de dispositivo es esencial durante un análisis dinámico.

## 📁 Ubicación de controladores del sistema en Windows

Para listar controladores del sistema:

Ejecutar → msinfo32 → Entorno de software → Controladores del sistema

## 🛠️ Herramienta principal: DriverView

Fuente: https://www.nirsoft.net  

**DriverView** muestra todos los controladores de dispositivos cargados actualmente, junto con:

- Dirección de carga  
- Descripción  
- Versión  
- Nombre del producto  
- Empresa/desarrollador  

Es una herramienta ligera, portable y muy útil para detectar drivers sospechosos o no firmados que podrían estar relacionados con malware.

## 🔍 Otras herramientas de análisis de controladores

| Herramienta | Enlace |
|-------------|--------|
| Driver Booster | https://www.iobit.com |
| Driver Reviver | https://www.reviversoft.com |
| Driver Easy | https://www.drivereasy.com |
| Driver Fusion | https://treexy.com |
| Driver Genius | http://www.driver-soft.com |
| Unknown Device Identifier | http://www.zhangduo.com |
| Driver Magician | http://www.drivermagician.com |
| DriverHive | http://www.driverhive.com |
| InstalledDriversList | https://www.nirsoft.net |
| My Drivers | http://www.zhangduo.com |
| Driver Agent Plus | https://scan.driverguide.com |
| DriverPack | https://drp.su |

### 🌐 Monitoreo del tráfico de red — Análisis del sistema en vivo

El análisis de red consiste en **capturar y examinar el tráfico** para identificar actividad maliciosa.  
El malware suele depender de la red para:

- Propagarse  
- Descargar payloads adicionales  
- Enviar información confidencial al atacante  
- Mantener canales de control remoto  
- Escalar privilegios dentro de la red  

Por ello, monitorizar el tráfico aumenta significativamente la capacidad de detectar:

- Conexiones sospechosas  
- Paquetes anómalos  
- Artefactos de malware  
- Comunicación con C2 (Command & Control)  
- Filtración de datos (exfiltration)  

Herramientas como **Capsa Network Analyzer** y **Wireshark** permiten capturar tráfico en vivo mientras se ejecuta un programa sospechoso.

## 🛠️ Herramienta principal: Capsa Network Analyzer

Fuente: https://www.colasoft.com  

Capsa es un analizador de red avanzado que ofrece:

### ⭐ Características principales
- Captura de paquetes en tiempo real  
- Monitorización 24/7 en LAN y WLAN  
- Análisis y decodificación profunda de protocolos  
- Identificación de tráfico sospechoso (“Top Talkers”)  
- Supervisión de tráfico de email y mensajería instantánea  
- Mapas de hosts por IP y MAC  
- Detección de hosts anómalos  
- Diagnóstico experto de problemas de red  

Es especialmente útil para identificar signos de troyanos, conexiones C2 y comportamientos anormales.

## 🔍 Otras herramientas de monitoreo de tráfico de red

| Herramienta | Enlace |
|-------------|--------|
| Wireshark | https://www.wireshark.org |
| Nessus | https://www.tenable.com |
| NetResident | https://www.tamos.com |
| PRTG Network Monitor | https://kb.paessler.com |
| GFI LanGuard | https://www.gfi.com |
| NetFort LANGuardian | https://www.netfort.com |
| CapMon | https://www.capmon.dk |
| Nagios XI | https://www.nagios.com |
| Total Network Monitor | https://www.softinventive.com |

---

### 🌐 Monitoreo y resolución de DNS — Análisis del sistema en vivo

Algunos tipos de malware, como **DNSChanger**, modifican la configuración DNS del sistema para redirigir al usuario a sitios fraudulentos, interceptar navegación web o manipular tráfico.  
Esto permite al atacante:

- Redirigir a páginas falsas (phishing)  
- Controlar qué sitios puede visitar la víctima  
- Alterar consultas DNS  
- Realizar ataques MITM  
- Desplegar publicidad maliciosa  
- Impedir acceso a sitios legítimos (antivirus, bancos, etc.)  

Por ello, durante un análisis dinámico es esencial revisar si el malware:

- Cambia los servidores DNS configurados  
- Realiza consultas DNS sospechosas  
- Se comunica con servidores C2 mediante dominios  
- Recurre a técnicas como *fast flux* o *domain generation algorithms (DGA)*

## 🛠️ Herramienta principal: DNSQuerySniffer

Fuente: https://www.nirsoft.net  

**DNSQuerySniffer** es una utilidad de rastreo que captura todas las consultas DNS realizadas desde el sistema.

### 📌 Información mostrada por consulta DNS
- Nombre de host  
- Puerto  
- ID de consulta  
- Tipo de registro (A, AAAA, NS, MX, etc.)  
- Tiempo de solicitud  
- Tiempo de respuesta  
- Duración de la consulta  
- Código de respuesta  
- Número de registros devueltos  
- Contenido de cada registro  

Además, permite exportar resultados en:
- CSV  
- HTML  
- TSV  
- Copiar directamente al portapapeles para Excel

## 🔍 Otras herramientas de monitoreo/resolución DNS

| Herramienta | Enlace |
|-------------|--------|
| DNSstuff | https://www.dnsstuff.com |
| DNS Lookup Tool | https://www.ultratools.com |
| Sonar | https://constellix.com |

---

### 🧵 Monitoreo de llamadas API — Análisis del sistema en vivo

Las **API del sistema operativo** permiten que las aplicaciones interactúen con Windows para acceder a:

- Archivos y sistemas de almacenamiento  
- Procesos e hilos  
- Registros  
- Kernel y funciones internas  
- Servicios de red  
- Sitios web y tráfico de Internet  
- Eventos del sistema  
- Interfaz gráfica (mouse, botones, ventanas)

El malware también utiliza estas API para:

- Manipular archivos del sistema  
- Inyectarse en otros procesos  
- Modificar configuraciones  
- Crear persistencia  
- Ejecutar código malicioso  
- Evasión de defensas  

Por ello, supervisar las **llamadas API** de un ejecutable sospechoso es clave para entender su comportamiento.

## 🛠️ Herramienta principal: API Monitor

Fuente: https://www.apimonitor.com  

**API Monitor** permite capturar y visualizar todas las llamadas Win32 API realizadas por un programa.

### ⭐ Información que muestra API Monitor
- Nombre de la función llamada  
- Secuencia de llamadas  
- Parámetros de entrada  
- Valores de salida  
- Valores devueltos por la función  
- Módulo que realiza la llamada  
- Tiempo de ejecución  

Es una de las mejores herramientas para comprender cómo interactúa una aplicación (o malware) con Windows.

## 🔍 Otras herramientas de monitoreo de API

| Herramienta | Enlace |
|-------------|--------|
| APImetrics | https://apimetrics.io |
| Runscope | https://www.runscope.com |
| AlertSite | https://smartbear.com |

---

### ⏰ Monitoreo de tareas programadas — Análisis del sistema en vivo

Muchos tipos de malware crean o modifican **tareas programadas** en Windows para garantizar su ejecución automática.  
Esto permite que el malware:

- Se active en una fecha específica (bombas lógicas)  
- Se ejecute tras un evento (inicio de sesión, arranque del sistema, conexión a red)  
- Mantenga persistencia incluso tras reinicios  
- Oculte su actividad al ejecutarse solo en ciertos momentos  
- Reactivarse automáticamente si el usuario lo elimina

Por ello, revisar las tareas programadas es esencial en un análisis dinámico.

## 🛠️ Cómo detectar tareas programadas sospechosas

### ✔️ Línea de comandos
Puedes listar todas las tareas programadas con:

schtasks

Esto muestra:

- Nombre de la tarea  
- Ubicación  
- Usuario que la ejecuta  
- Estado  
- Trigger/Programación  
- Acción (programa ejecutado)

### ✔️ Interfaz gráfica
También puedes usar la herramienta integrada:

**Programador de tareas**  
> Panel de control → Herramientas administrativas → Programador de tareas

## 🔍 Herramientas adicionales para monitorear tareas programadas

| Herramienta | Enlace |
|-------------|--------|
| Monitoring Task Scheduler Tool (MoTaSh) | https://github.com |
| ADAudit Plus | https://www.manageengine.com |
| CronitorCLI | https://cronitor.io |
| SolarWinds Windows Scheduled Task Monitor | https://www.solarwinds.com |

---

### 🌐 Análisis del sistema en vivo: Monitoreo de la actividad del navegador

El malware puede utilizar los **navegadores web** para comunicarse con servidores de comando y control (C&C), descargar archivos maliciosos o conectarse a sitios peligrosos.  
Por ello, es esencial revisar su actividad para identificar compromisos.

## 🔍 Qué revisar en la actividad del navegador

Los respondedores deben inspeccionar:

- **Historial de navegación**  
- **Historial de descargas**
- **Cachés web**
- **Extensiones instaladas**
- **Conexiones a puertos inusuales** (distintos de 80/443/8080)
- **Registros de firewalls/SWG** para:
  - URLs sospechosas  
  - Cadena maliciosas  
  - Dominios desconocidos  
  - Intentos de conexión a C&C  

También se pueden analizar patrones de navegación anómalos o acceso a dominios relacionados con malware.

## 🛠️ Herramientas recomendadas

### ✔️ Wireshark
**Fuente:** https://www.wireshark.org  

Wireshark es el analizador de protocolos más utilizado para investigar tráfico web malicioso.  
Permite capturar, filtrar y analizar paquetes en detalle.

#### Componentes principales
- **Barra de menú**: funciones principales  
- **Barra de herramientas**: accesos rápidos  
- **Barra de filtro**: filtrado avanzado de tráfico  
- **Panel de lista de paquetes**: vista general  
- **Panel de detalles**: breakdown por capas/protocolo  
- **Panel de bytes**: vista en hexadecimal

#### Características clave
- Inspección profunda de cientos de protocolos  
- Captura en vivo y análisis offline  
- Navegador de tres paneles  
- Multiplataforma (Windows, Linux, macOS, BSD, Solaris…)  
- Herramienta CLI: **TShark**

## 🔧 Herramientas adicionales de monitoreo de tráfico web

| Herramienta | Enlace |
|-------------|--------|
| Colasoft Network Analyzer | https://www.colasoft.com |
| OmniPeek | https://www.savvius.com |
| Observer Analyzer | https://www.viavisolutions.com |
| PRTG Network Monitor | https://www.paessler.com |
| NetFlow Analyzer | https://www.manageengine.com |

---

### 🧊 Técnicas de detección de malware: Volcado de memoria / Análisis estático

El **análisis estático** consiste en examinar un archivo sospechoso **sin ejecutarlo**, para identificar su funcionalidad, estructura interna y posibles comportamientos maliciosos.  
Es seguro, pero debe hacerse en un entorno controlado porque algunos malwares pueden activarse sin instalación.

Este análisis permite:
- Identificar **código malicioso**, estructuras de datos y funciones internas.
- Obtener **indicadores técnicos** (nombre, hashes, tamaño, tipo de archivo).
- Detectar **ofuscación, packers** y métodos usados para evadir análisis.
- Analizar **dependencias**, llamadas a funciones y gráficos de llamadas.
- Comprender la **arquitectura e impacto** del malware en el sistema.

### 🔧 Técnicas comunes de análisis estático
- **Huellas digitales** (MD5, SHA1, SHA256)  
- **Escaneo local/online** con motores antivirus  
- **Búsqueda de cadenas** dentro del binario  
- **Detección de packers / ofuscadores**  
- **Análisis de estructura PE** (en ejecutables Windows)  
- **Revisión de dependencias**  
- **Desensamblado del código**  

Estas técnicas ayudan a entender cómo opera el malware antes de ejecutar un análisis dinámico.

---

### 🧊 Análisis de volcado de memoria: Huellas digitales de archivos

La **toma de huellas digitales de archivos** consiste en calcular valores hash de binarios sospechosos para:
- Identificar y rastrear archivos en una red.
- Comparar su código con otros binarios previamente analizados.
- Detectar posibles modificaciones durante el análisis.
- Reconocer funciones o algoritmos criptográficos usados dentro del malware.

Los hashes permiten **identificar de forma única un archivo**, aunque no funcionan bien con archivos cifrados o protegidos con contraseña (como imágenes, audio o vídeo cifrado).

Las funciones hash más usadas en análisis de malware son:
- **MD5**
- **SHA-1**
- **SHA-256** (preferido actualmente por seguridad)

### 🔧 Herramienta destacada: HashMyFiles
HashMyFiles permite calcular múltiples hashes (MD5, SHA1, CRC32, SHA-256, SHA-384, SHA-512) y mostrar información útil del archivo:
- Ruta completa  
- Fechas de creación/modificación  
- Tamaño  
- Atributos y versión  

Esto facilita comparar binarios y detectar variaciones o copias maliciosas.

### 🧰 Otras herramientas para huellas digitales
- Hashtab — http://implbits.com  
- HashCalc — http://www.slavasoft.com  
- md5deep — http://md5deep.sourceforge.net  
- MD5sums — http://www.pc-tools.net  
- tools4noobs (hash online) — https://www.tools4noobs.com  
- Cryptomathic — http://extranet.cryptomathic.com  

---

## 🧊 Análisis de volcado de memoria: Escaneo de malware local y en línea

El **escaneo de malware** permite analizar binarios sospechosos utilizando motores antivirus locales o servicios online.  
Si el archivo pertenece a una familia conocida, estos servicios pueden identificarlo rápidamente y proporcionar documentación existente, acelerando el análisis.

### 🔍 Escaneo local
Se realiza con antivirus instalados en el sistema.  
Ayuda a detectar si el binario coincide con malware ya identificado previamente por los fabricantes.

### 🌐 Escaneo online: VirusTotal
VirusTotal permite subir archivos o URLs sospechosas y analizarlos con **decenas de motores antivirus simultáneamente**.  
Detecta malware comparando los **hashes** del archivo con bases de datos de amenazas conocidas.

**Información que proporciona VirusTotal:**
- Motores que detectan el archivo como malicioso  
- Nombre o familia del malware  
- Hashes (MD5, SHA-1, SHA-256)  
- Tipo de archivo y arquitectura  
- Timestamp de compilación  
- Secciones PE, DLL utilizadas  
- Direcciones IP y conexiones asociadas  
- Recursos y metadatos del binario  

### 🧰 Otras plataformas de escaneo online
### 🧰 Otras plataformas de escaneo (tabla)

| Plataforma / Servicio                 | URL                                           | Descripción breve |
|--------------------------------------|-----------------------------------------------|--------------------|
| **Jotti**                            | https://virusscan.jotti.org                   | Escáner multi-antivirus gratuito. |
| **Metadefender**                     | https://metadefender.opswat.com               | Escaneo avanzado con análisis de archivos y desinfección. |
| **Fortiguard Online Scanner**        | https://www.fortiguard.com                    | Escáner online de Fortinet. |
| **IObit Cloud**                      | https://cloud.iobit.com                       | Análisis de archivos en la nube. |
| **ThreatExpert**                     | https://www.symantec.com                      | Sistema automatizado de análisis de malware. |
| **Malwr**                            | https://malwr.com                             | Sandbox online para ejecutar y analizar malware. |
| **Valkyrie (Comodo)**                | https://valkyrie.comodo.com                   | Análisis basado en comportamiento y reputación. |
| **Dr.Web Online Scanner**            | https://vms.drweb.com                         | Escaneo antivirus online de Dr.Web. |
| **UploadMalware**                    | http://www.uploadmalware.com                  | Subida y análisis colaborativo de muestras. |
| **ThreatAnalyzer**                   | https://www.threattrack.com                   | Análisis dinámico especializado en malware. |
| **Payload Security**                 | https://www.payload-security.com              | Plataforma de sandbox automatizado. |
| **Anubis**                            | https://sourceforge.net                        | Motor de análisis automático de malware. |
| **Windows Defender Security Intelligence** | https://www.microsoft.com                    | Base de datos de inteligencia de amenazas de Microsoft. |
| **Bitdefender Quickscan**           | https://www.bitdefender.com                   | Escaneo rápido usando motores de Bitdefender. |

---

### 🧊 Análisis de volcado de memoria: Búsqueda de cadenas

La **búsqueda de cadenas** consiste en extraer texto incrustado dentro de binarios para descubrir información oculta o funciones internas del programa.  
Estas cadenas pueden revelar:

- URLs usadas por el malware  
- Comandos internos o argumentos sospechosos  
- Mensajes ocultos o strings cifradas  
- Indicadores de comportamiento malicioso  
- Rutas de archivos, procesos o claves de registro  

Durante el análisis estático, examinar estas cadenas ayuda a identificar posibles acciones dañinas sin ejecutar el malware.

### 🔧 Herramienta destacada: BinText
BinText permite extraer:

- Cadenas ASCII  
- Cadenas Unicode  
- Cadenas embebidas en recursos  

Las cadenas pueden exportarse a un archivo de texto para facilitar su análisis.

### 🧰 Otras herramientas de búsqueda de cadenas

| Herramienta | URL | Descripción |
|------------|-----|-------------|
| **FLOSS** | https://www.fireeye.com | Extrae cadenas, incluso las ofuscadas, de binarios maliciosos. |
| **ResourceExtract** | http://www.resourceextract.com | Extrae recursos (iconos, texto, binarios) de ejecutables. |
| **Hex Workshop** | http://www.hexworkshop.com | Editor hexadecimal avanzado con análisis de cadenas. |
| **Strings** | https://docs.microsoft.com | Herramienta clásica de Sysinternals para extraer cadenas ASCII/Unicode. |

---

### 🧊 Análisis de volcado de memoria: Identificación de métodos de empaquetado / ofuscación

Los atacantes utilizan **empaquetadores** y **técnicas de ofuscación** para comprimir, cifrar o modificar ejecutables con el fin de evadir la detección antivirus y dificultar la ingeniería inversa.  
Al ejecutarse un programa empaquetado, un pequeño *stub* se encarga de **descomprimir o descifrar** el contenido real antes de ejecutarlo, ocultando la lógica interna del malware.

Detectar estos métodos es esencial para:

- Identificar si el binario está protegido o modificado  
- Elegir la herramienta adecuada para desempaquetar  
- Reconstruir el código malicioso desde el volcado de memoria  
- Facilitar el análisis estático del malware  

### 🔧 Herramienta destacada: PEiD

PEiD permite identificar:

- Empaquetadores comunes  
- Cifradores  
- Compiladores  
- Puntos de entrada, secciones PE y metadatos útiles  

Incluye firmas para más de **600 empaquetadores y compiladores**.

### 🧰 Otras herramientas de empaquetado / ofuscación

| Herramienta | URL | Descripción |
|------------|-----|-------------|
| **UPX** | https://upx.github.io | Empaquetador de ejecutables muy utilizado; permite empaquetar y desempaquetar. |
| **Exeinfo PE** | http://exeinfo.atwebpages.com | Identifica empaquetadores, compresores, compiladores y técnicas de ofuscación. |
| **ASPack** | http://www.aspack.com | Empaquetador comercial diseñado para reducir tamaño y ocultar código. |

---

### 🧊 Análisis de volcado de memoria: Búsqueda de información de ejecutables portátiles (PE)

Los archivos **PE (Portable Executable)** son el formato utilizado por Windows para ejecutables, DLL y otros binarios.  
Contienen tanto el **código ejecutable** como **metadatos esenciales** para que el sistema operativo cargue y ejecute el programa correctamente.

Analizar un archivo PE permite obtener información clave para la identificación de malware, como:

- Tiempos de creación/modificación  
- Funciones importadas y exportadas  
- Dependencias DLL  
- Compilador y timestamp  
- Recursos (iconos, menús, cadenas, imágenes)  
- Estructura del archivo y secciones internas  

### 📦 Secciones típicas en un archivo PE

| Sección | Contenido |
|--------|-----------|
| **.text** | Código ejecutable que ejecuta la CPU |
| **.rdata** | Import/export, datos de solo lectura |
| **.data** | Variables globales y datos accesibles por el programa |
| **.rsrc** | Recursos: iconos, imágenes, cadenas, menús, etc. |

Estas secciones ayudan a identificar comportamientos sospechosos, recursos manipulados o anomalías en el binario.

### 🔧 Herramienta destacada: PE Explorer

PE Explorer permite:

- Ver, analizar y editar ejecutables PE (EXE, DLL, ActiveX, SYS, CPL, SCR, etc.)  
- Examinar recursos y secciones internas  
- Descubrir dependencias y metadatos del archivo  

### 🧰 Otras herramientas de análisis PE

| Herramienta | URL | Descripción |
|------------|-----|-------------|
| **pescan (Portable Executable Scanner)** | https://tzworks.net | Analiza PE para detectar anomalías y estructura interna. |
| **Resource Hacker** | http://www.angusj.com | Permite ver y extraer recursos incrustados en ejecutables. |
| **PEView** | https://www.aldeid.com | Muestra los encabezados y secciones PE para análisis estático. |

---

### 🧩 Análisis de volcado de memoria: Identificación de dependencias de archivos

Los programas dependen de **bibliotecas del sistema (DLL)** para ejecutar funciones específicas.  
Durante el análisis de malware, revisar estas dependencias permite descubrir:

- Qué funciones utiliza el binario  
- Qué bibliotecas carga y con qué propósito  
- Si usa DLL legítimas o manipuladas  
- Qué capacidades podría tener (red, UI, kernel, criptografía, etc.)

Analizar dependencias es clave porque los binarios maliciosos suelen apoyarse en DLL comunes para ocultarse como software legítimo.

### 📚 DLL habituales en Windows

| DLL | Función |
|-----|---------|
| **Kernel32.dll** | Acceso a memoria, archivos y hardware |
| **Advapi32.dll** | Seguridad, registro y Service Manager |
| **User32.dll** | Interfaz gráfica (botones, ventanas, input del usuario) |
| **Gdi32.dll** | Generación y manipulación de gráficos |
| **Ntdll.dll** | Interfaz interna del kernel de Windows |
| **WSock32.dll / Ws2_32.dll** | Funciones de red y sockets |
| **Wininet.dll** | Funciones de red de alto nivel (HTTP/FTP) |

### 🔧 Herramienta destacada: Dependency Walker

**Dependency Walker** permite:

- Ver todas las DLL cargadas por un ejecutable  
- Identificar funciones importadas/exportadas  
- Detectar módulos faltantes o incompatibles  
- Visualizar el árbol jerárquico de dependencias  
- Detectar problemas de carga que pueden revelar comportamiento malicioso  

### 🧰 Otras herramientas para análisis de dependencias

| Herramienta | URL | Uso principal |
|-------------|-----|----------------|
| **Snyk** | https://snyk.io | Detecta vulnerabilidades en dependencias y librerías. |
| **Hakiri** | https://hakiri.io | Análisis de seguridad en ecosistemas de dependencias. |
| **Retire.js** | https://retirejs.github.io | Detecta librerías JS vulnerables o abandonadas. |

---

## 🛠️ Análisis de volcado de memoria: Desmontaje de malware

El desmontaje (disassembly) es una fase del análisis estático donde se convierte el binario sospechoso en **código ensamblador legible**.  
Esto permite a los respondedores comprender:

- La lógica interna del programa  
- Las funciones API utilizadas  
- El lenguaje y las técnicas empleadas por el atacante  
- Si el malware intenta conectarse a servidores C&C  
- Si contiene mecanismos anti–ingeniería inversa  

El desmontaje es esencial porque los atacantes suelen ocultar la lógica maliciosa mediante empaquetadores, ofuscación o técnicas anti-debug.

### 🔧 Herramienta principal: IDA Pro

**IDA Pro** es el desensamblador profesional más utilizado en análisis de malware.

**Funciones clave:**

- Desensambla binarios y genera mapas completos de ejecución  
- Permite visualizar instrucciones en ensamblador igual que la CPU las ejecuta  
- Incluye un depurador interactivo que ayuda a analizar el comportamiento real  
- Permite saltar mecanismos de ofuscación y analizar código hostil en profundidad  

### 🧰 Otras herramientas de depuración / desmontaje

| Herramienta | URL | Descripción |
|-------------|-----|-------------|
| **OllyDbg** | http://www.ollydbg.de | Depurador x86 muy usado en análisis de malware. |
| **WinDbg** | http://www.windbg.org | Depurador avanzado de Microsoft para kernel y user-mode. |
| **objdump** | https://sourceware.org | Desensamblador de línea de comandos para múltiples arquitecturas. |
| **ProcDump** | https://docs.microsoft.com | Genera volcados de procesos para análisis posterior. |
| **KD** | https://docs.microsoft.com | Kernel Debugger para análisis profundo del sistema. |
| **CDB** | https://docs.microsoft.com | Depurador ligero de Microsoft. |
| **NTSD** | https://docs.microsoft.com | Depurador sin interfaz gráfica para procesos en Windows. |

---

### 🧠 Análisis de volcado de memoria con Volatility

El análisis de volcado de memoria permite investigar sistemas comprometidos sin arrancarlos, evitando que el malware cambie su estado, elimine evidencia o se propague. Para ello se utilizan frameworks forenses como **Volatility**, una herramienta en Python ampliamente usada para extraer artefactos de memoria y detectar actividad maliciosa.

Volatility permite identificar:

- Procesos y servicios maliciosos  
- Conexiones de red activas  
- Inyecciones de código  
- Entradas de registro cargadas  
- Actividad anómala en memoria  
- Persistencia y rootkits  

### 🧩 Pasos básicos para analizar un volcado con Volatility

1. **Crear un volcado de memoria**  
   Guardarlo como `.dd` o `.mem` (por ejemplo, `memdump.mem`).

2. **Usar un entorno seguro**  
   Preferiblemente una **máquina virtual Linux** aislada.

3. **Instalar Volatility**  
   ```bash
   sudo apt-get install volatility
4. Mover el volcado al sistema de análisis
Copiar memdump.mem a la máquina de análisis.

5. Ejecutar Volatility desde su directorio
```bash
cd /usr/share/volatility
Sintaxis general del comando
