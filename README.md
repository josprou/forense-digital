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

1. [Respuesta a incidentes de malware](#1-respuesta-a-incidentes-de-malware)
2. [Respuestas a incidentes de correo eletrónico](#2-respuestas-a-incidentes-de-correo-eletrónico)
3. [Respuesta a incidentes de red](#3-respuesta-a-incidentes-de-red)
4. [Respuesta a incidentes de aplicaciones web](#4-respuesta-a-incidentes-de-aplicaciones-web)
5. [Respuesta a incidentes en la nube](#5-respuesta-a-incidentes-en-la-nube)
6. [Recursos y Mejores Prácticas](#9-recursos-y-mejores-prácticas)

---

## 1. Respuesta a incidentes de seguridad de malware

El malware es software malintencionado creado para dañar sistemas, robar información o dar control al atacante. Incluye virus, gusanos, troyanos, rootkits, puertas traseras, ransomware, spyware, adware, botnets, keyloggers, crypters, etc.

Sus efectos pueden incluir:

- **Robo de datos personales o corporativos**
- **Ralentización del sistema**
- **Borrado de información**
- **Fallos del sistema o del hardware**
- **Uso del equipo infectado para atacar a otros**
- **Envío de spam o publicidad maliciosa**

### 🐧 Tipos principales de malware
#### 1. Troyano
Se oculta dentro de un programa legítimo y se activa con acciones del usuario. Da acceso total al atacante y puede borrar datos, robar contraseñas o usar la máquina para atacar a otros.
#### 2. Puerta trasera (Backdoor)
Permite acceder al sistema evitando autenticación o controles de seguridad. Se instala sin conocimiento del usuario y facilita control remoto continuo.
#### 3. Rootkit
Otorga privilegios de root y oculta actividades del atacante modificando componentes del sistema operativo. Permite instalar herramientas maliciosas sin ser detectado.
#### 4. Ransomware
Bloquea el ordenador o cifra archivos y exige un rescate para devolver el acceso. Suele propagarse por correos maliciosos o descargas inseguras.
#### 5. Adware
Muestra anuncios no deseados y puede redirigir a sitios maliciosos o descargar otros tipos de malware.
#### 6. Virus
Programa que se autorreplica infectando archivos. Requiere acción del usuario para propagarse y puede dañar o borrar datos.
#### 7. Gusano
Similar al virus pero no necesita intervención humana. Se propaga por la red, satura recursos y puede instalar puertas traseras.
#### 8. Spyware
Vigila en secreto la actividad del usuario, registrando pulsaciones de teclado, contraseñas, páginas visitadas y capturas de pantalla.
#### 9. Botnet
Red de equipos infectados controlados por un atacante para realizar ataques (DDoS), enviar spam, distribuir malware, etc.
#### 10. Crypters
Herramientas para cifrar malware y hacerlo indetectable para los antivirus.

### 🐧 Componentes del malware
Los atacantes desarrollan malware combinando distintos componentes especializados que les permiten robar datos, modificar sistemas, instalar puertas traseras o simplemente propagarse de forma encubierta. Estos elementos ayudan al malware a evadir detección, infectar, ocultarse y ejecutar acciones maliciosas.

Componentes principales del malware
- **Crypter**: oculta el malware cifrándolo para evitar que los antivirus lo detecten o analicen.
- **Downloader**: troyano que descarga desde Internet más malware al sistema comprometido.
- **Dropper**: instala el malware de forma encubierta y puede traer archivos adicionales necesarios para la infección.
- **Exploit**: código que aprovecha vulnerabilidades para comprometer el sistema, espiar o instalar malware.
- **Injector**: inserta código malicioso o exploits dentro de procesos legítimos para ocultar su actividad.
- **Obfuscator*: oculta o transforma el código malicioso para dificultar su análisis y detección.
- **Packer**: comprime y transforma el malware a un formato ilegible para hacer más difícil su identificación.
- **Payload (carga útil)**: la parte del malware que ejecuta la acción maliciosa (borrar datos, abrir puertos, modificar archivos, etc.).
- **Código malicioso**: instrucciones base del malware, que pueden aparecer como subprogramas Java, controles ActiveX, complementos de navegador o contenido embebido.

### 🐧 Métodos de propagación de malware
Los métodos más comunes que utilizan los atacantes para infectar un sistema con malware incluyen:  
- Aplicaciones de mensajería instantánea  
- Medios de hardware portátiles/dispositivos extraíbles  
- Errores de software del navegador y correo electrónico 
- Administración de parches insegura  
- Aplicaciones falsas/señuelo  
- Sitios no confiables y aplicaciones web/software gratuito  
- Descarga de archivos basados en Internet  
- Archivos adjuntos de correo electrónico  
- Propagación de red 
- Servicios para compartir archivos [sistema básico de entrada/salida de red (NetBIOS); protocolo de transferencia de archivos (FTP); bloque de mensajes del servidor (SMB)] 
- Instalación por otros malwares  
- Bluetooth y redes inalámbricas  
- Ejecutables infectados, archivos de biblioteca de vínculos dinámicos (DLL), macros, JavaScripts y Documentos 

### 🐧 Técnicas comunes que utilizan los atacantes para distribuir software malicioso en la Web  
Los atacantes utilizan varias técnicas para difundir malware aprovechando fallos, ingeniería social y manipulación de contenidos:
- **Black Hat SEO**: manipulan motores de búsqueda usando técnicas SEO agresivas para posicionar páginas que contienen malware.
- **Clickjacking social**: engañan a usuarios para que hagan clic en enlaces infectados dentro de sitios aparentemente legítimos.
- **Spear phishing web**: crean páginas falsas que imitan instituciones reales para robar contraseñas y datos bancarios.
- **Malvertising**: insertan anuncios maliciosos en plataformas de publicidad legítimas para infectar a usuarios.
- **Sitios legítimos comprometidos**: usan webs vulnerables para instalar malware cuando el usuario las visita.
- **Descargas automáticas (drive-by downloads)**: explotan vulnerabilidades del navegador para instalar malware sin interacción del usuario.
- **Correos con malware**: envían emails con adjuntos o enlaces infectados; es uno de los métodos más comunes hoy en día.

### 🐧 Caso de estudio
El siguiente caso de estudio muestra la importancia y la necesidad del malware IR para manejar de manera efectiva los incidentes de seguridad del malware: 

**Desafío**: 
Maria White, directora administrativa de la organización, encontró su sistema inaccesible y mostró la siguiente imagen. Entendiendo que fue algún tipo de ataque de malware, se puso en contacto con el equipo de RI para investigar el problema. Cuando llegaron los equipos de respuesta a incidentes, descubrieron que más de 30 sistemas de la organización se vieron afectados por un ataque de ransomware similar. 

**Proceso**: 
Los que respondieron separaron inmediatamente los sistemas afectados de la red en funcionamiento e informaron a la organización de Microsoft sobre el problema. Descubrieron que el problema había afectado a los sistemas a gran escala y era el resultado del uso de versiones más antiguas y vulnerables de los sistemas operativos Windows. 

Como los sistemas eran inaccesibles, los que respondieron extrajeron la memoria del disco duro de algunos sistemas. Los respondedores extrajeron los datos y los transfirieron al entorno de la caja de arena para iniciar el análisis. 

**Solución**: 
Los respondedores inmediatamente parchearon el sistema operativo con actualizaciones de Microsoft y comenzaron a analizar los datos. Durante el análisis, descubrieron que el malware había cifrado todos los archivos del sistema. Intentaron analizar estáticamente los archivos y descubrieron que el malware intentaba conectarse a un dominio no registrado y mostraba signos de falla de conexión. El equipo utilizó diferentes técnicas de análisis de malware, como buscar cadenas, buscar archivos ejecutables portátiles (PE) e identificar dependencias de archivos, pero todo fue en vano. 

Descubrieron que el malware estaba utilizando la solicitud de dominio como clave de descifrado y que cualquier respuesta del dominio podría liberar los sistemas. Luego, el equipo de respuesta utilizó servicios de simulación de red, como la suite de simulación de servicios de Internet (iNetSim), para simular la respuesta como si fuera del dominio solicitado por el malware. Al aplicar lo mismo, el ransomware desbloqueó el sistema. Los que respondieron inmediatamente utilizaron esta técnica en todos los sistemas y los parchearon con una actualización del fabricante. 

Los que respondieron también sugirieron que la empresa debe tener una política de actualización automática programada para evitar la explotación de las vulnerabilidades del sistema existente. 

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
