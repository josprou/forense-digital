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

- 💻 Una computadora portátil con herramientas de análisis  
- 💾 Dispositivos para copias de seguridad  
- 🌐 Hardware y cables de red  
- 📀 Dispositivos extraíbles (DVD, USB) para recopilar y transferir evidencias  

**Herramientas recomendadas para detección y análisis de malware:**

- 🧪 **Virtualización**: VirtualBox, VMware vSphere Hypervisor, Microsoft Virtual Server  
- 📸 **Imágenes forenses**: FTK Imager  
- 🧬 **Análisis de PE**: PEView, PeStudio, PEiD, PEBrowse  
- 🧾 **Snapshots de host**: Regshot, RegMon, FileMon, Total Commander  
- 🧠 **Volcado de memoria**: Scylla, OllyDumpEx  
- 🌐 **Rastreo de red**: Wireshark  
- 🌍 **Simulación de red**: iNetSim  
- 📊 **Procesos y monitorización**: Process Monitor, Process Explorer  
- 🔢 **Hex editors**: HexEditor, 010 Editor, Hexinator  
- 🐞 **Depuración**: OllyDbg, IDA Pro  
- 🧵 **Búsqueda de cadenas**: ResourcesExtract, Bintext, Hex Workshop  
- 🧩 **Dependencias**: Dependency Walker  

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

#### 🚨 Indicaciones de incidentes de malware

El malware se propaga muy rápido dentro de una organización, por lo que es crucial **detectarlo pronto** para limitar los equipos infectados y reducir el esfuerzo de recuperación.

Algunos indicadores:

- 🌐 Flujos de tráfico de red anormales  
- 📧 Correos rebotados inexplicables  
- 📢 Ventanas emergentes, alertas y anuncios irrelevantes  
- 📜 Registros con intentos de escaneo de puertos o acceso no autorizado  
- 🗂️ Modificación, eliminación o reubicación de archivos  
- 💀 Pantallas azules (BSOD)  
- 🧊 Congelamientos, apagados y bloqueos repentinos  
- 🐌 Ralentización general del sistema  
- ⛔ Incapacidad para instalar actualizaciones  
- 🔕 Programas de seguridad deshabilitados  
- 🌍 Cambios extraños en configuración del navegador  
- ⚙️ Programas no aprobados que se inician solos  
- 📩 Envío masivo de correos o publicaciones no deseadas  
- 🔐 Cuentas de usuario desconocidas  
- 🔄 Reinicios inesperados  
- 🖱️ Movimiento extraño del ratón o teclado congelado  
- ❗ Alertas antivirus constantes  
- 📁 Archivos/carpetas que desaparecen  
- 📦 Falta de espacio en disco sin motivo aparente  
- 🪟 Pop-ups y anuncios no deseados  

*(Lista resumida)*

---

#### 🧪 Técnicas de detección de malware

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

#### 🧪 Técnicas de detección de malware: sistema en vivo / análisis dinámico

El **análisis dinámico** (o de sistema en vivo) detecta malware basándose en **lo que hace** dentro del sistema:

- Archivos creados o modificados  
- Puertos usados  
- Procesos iniciados  
- Cambios de configuración  
- Conexiones a URLs sospechosas  

Se centra en monitorizar:

- 🔌 **Supervisión del puerto**  
- ⚙️ **Supervisión del proceso**  
- 🪟 **Supervisión del registro**  
- 🧩 **Servicios de Windows**  
- 🚀 **Programas de inicio**  
- 📜 **Registro de eventos**  
- 📦 **Instalaciones**  
- 📂 **Archivos y carpetas**  
- 🧮 **Controladores de dispositivo**  
- 🌐 **Tráfico de red**  
- 🧭 **Resolución de DNS**  
- 🧬 **Llamadas a API**  
- 🕒 **Tareas programadas**  
- 🌍 **Actividad del navegador**

---

#### 🌐 Análisis del sistema en vivo: monitoreo de puertos

*(Sección pendiente de desarrollo: aquí puedes añadir herramientas tipo `netstat`, `TCPView`, etc.)*

---

## 2. Adquisición de Evidencia (Copia Forense)

**Concepto:** La copia forense (imagen _bit-stream_) es la adquisición de datos que genera un duplicado exacto (bit a bit) de un dispositivo de almacenamiento a otro, asegurando que la evidencia original no se modifique.

### 💾 Herramientas de Imagen de Disco

- **FTK Imager:** El estándar gratuito en Windows. Permite crear imágenes, montar discos y visualizar contenido.
- **Guymager:** La mejor herramienta gráfica para Linux (rápida y robusta).
- **DC3DD / DCFLDD:** Versiones forenses del comando `dd` de Linux con hashing y logs de seguridad.
- **Fuji (Forensic Unattended Juicy Imaging):** Para automatizar imágenes.

### 🌐 Adquisición Web (OSINT y Preservación)

- **FAW (Forensic Acquisition of Websites):** Navegador forense para capturar páginas web con valor legal.
- **Httrack:** Para descargar sitios web completos.
- **Browser History Capturer / Chrome Cache View:** Herramientas de NirSoft para extraer historiales locales.

---

## 3. Respuesta a Incidentes (First Responder)

El rol del First Responder:

Es el primero en intervenir en la escena. Debe seguir protocolos estrictos para no alterar la situación (ni destruir pruebas, ni añadir rastros). Su objetivo es preservar la volatilidad de los datos.

### 🚑 Herramientas de Triage y Recolección en Vivo

- **Velociraptor / GRR Rapid Response:** Para caza de amenazas y monitoreo remoto a gran escala.
- **OSQuery:** Convierte el sistema operativo en una base de datos relacional para hacer consultas SQL sobre su estado.
- **UAC (Unix-like Artifacts Collector):** Recolector de artefactos para sistemas Linux/Unix.
- **MIG (Mozilla InvestiGator):** Plataforma de investigación remota.

---

## 4. Análisis Forense: General y Triage

El análisis implica la conversión, extracción e interpretación de datos para reconstruir la cronología: _quién, cómo, cuándo y qué_.

### 🔍 Suites de Análisis

- **Autopsy:** La interfaz gráfica de _The Sleuth Kit_. La herramienta open source más completa.
- **IPED (Indexador y Procesador de Evidencias Digitales):** Muy potente, usada por la policía federal de Brasil. Excelente para grandes volúmenes de datos.
- **Turbinia:** Automatización de análisis forense en la nube.
- **DFF (Digital Forensics Framework):** Entorno modular de análisis.

---

## 5. Análisis Específico: Windows y macOS

### 🪟 Windows Forensics

Es el campo más consolidado, enfocado en recuperar artefactos de usuario, registro y sistema en entornos corporativos.

- **NirSoft Tools:** Suite esencial de pequeñas utilidades.
- **PowerForensics:** Framework de análisis basado en PowerShell.

### 🍎 Mac Forensics

Requiere conocimiento profundo del sistema de archivos APFS y estructuras de Apple.

- **mac_apt (macOS Artifact Parsing Tool):** Imprescindible para parsear artefactos.
- **APFS Fuse:** Driver para montar discos APFS en Linux.
- **OSXAuditor / OSX Collect:** Herramientas de auditoría y recolección.
- **MacLocationsScraper / macMRUParser:** Para geolocalización y listas de archivos recientes.

---

## 6. Análisis de Memoria y Metadatos

**Análisis de Metadatos:** Los "datos sobre los datos". Revelan la historia del archivo (creación, modificación, acceso, autoría).

### 🧠 Memoria RAM y Procesos

- **Volatility:** El framework líder para analizar volcados de memoria RAM (detectar malware, contraseñas, conexiones).
- **Rekall:** Fork de Volatility, enfocado en análisis de memoria.
- **MemProcFS:** Visualiza la memoria física como un sistema de archivos virtual.

### 📋 Metadatos y Hashing

- **Hashlookup:** Servicio para verificar hashes contra bases de datos de archivos conocidos (NSRL).
- **Laika BOSS:** Escáner de objetos y archivos intrusivos.

---

## 7. Recuperación de Datos (Data Recovery)

Herramientas para recuperar archivos borrados o de discos dañados (File Carving).

- **PhotoRec / TestDisk:** Open source, muy potentes para recuperar particiones y archivos crudos.
- **R-Studio:** (Comercial) Considerado uno de los mejores para recuperación lógica compleja.
- **Recuva:** Básico, bueno para recuperaciones sencillas en Windows.
- **DiskGenius / EaseUS:** Suites "todo en uno" para gestión de discos y recuperación.

---

## 8. Suite de Herramientas "DBX" (Utilidades Ligeras)

_Colección de herramientas especializadas para tareas rápidas y precisas._

| Herramienta | Descripción y Funcionalidad |
| :--- | :--- |
| **dbxScreenshot** | **Captura Forense de Pantalla.** Captura con metadatos detallados (Timestamp UTC, Hash MD5/SHA, usuario, ID dispositivo) para preservar la cadena de custodia visual. |
| **dbxCsvViewer** | **Visor CSV Avanzado.** Soporta delimitadores complejos, carga rápida, ordenamiento y exportación directa a Excel (.xlsx). Ideal para logs masivos. |
| **dbxMetadata** | **Analizador de Atributos.** Muestra info del sistema de archivos (MAC times) y metadatos internos de diversos formatos. |
| **dbxSeqCheck** | _(En desarrollo)_ **Verificador de Secuencias.** Detecta huecos, duplicados o desorden en secuencias numéricas (útil para facturas, logs ID, etc.). |
| **dbxHashFile** | **Calculadora de Hashing.** Cálculo rápido y paralelo de hashes (MD5, SHA1, SHA256, etc.) para verificar integridad de ficheros. |

---

## 9. Recursos y Mejores Prácticas

### 📚 Guías y Protocolos (Must Read)

- **ENISA Digital Forensics Handbook:** La biblia europea de procedimientos.
- **SWGDE Best Practices:** Estándares del grupo de trabajo científico sobre evidencia digital.
- **Interpol Guidelines:** Guía para primeros intervinientes (First Responders).
- **RFC 3227:** Guía para la recolección de evidencia y orden de volatilidad.

### 🛠️ Herramientas Comerciales (Nivel Enterprise)

Si el presupuesto lo permite, estas son las herramientas estándar en cuerpos policiales y grandes firmas:

- **Cellebrite UFED:** Líder mundial en forense móvil.
- **Magnet AXIOM:** Excelente correlación de artefactos (móvil + PC + nube).
- **EnCase Forensic:** El software clásico de la industria, muy usado en entornos judiciales.

---

<div align="center">
  <br/>
  <p>
    <img src="https://img.shields.io/badge/Made%20with-❤️-FF5555?style=flat-square" alt="Love" />
    by <a href="https://github.com/Ph0e-Nyx"><strong>Ph0e-Nyx</strong></a>
  </p>
  <p>
    <em>"The truth is in the data."</em>
  </p>
  <p>
    <a href="#">Volver al inicio ⬆️</a>
  </p>
</div>
