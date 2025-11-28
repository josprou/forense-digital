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

1. [Sistemas Operativos y Distribuciones](#1-sistemas-operativos-y-distribuciones)
2. [Adquisición de Evidencia (Copia Forense)](#2-adquisición-de-evidencia-copia-forense)
3. [Respuesta a Incidentes (First Responder)](#3-respuesta-a-incidentes-first-responder)
4. [Análisis Forense: General y Triage](#4-análisis-forense-general-y-triage)
5. [Análisis Específico: Windows y macOS](#5-análisis-específico-windows-y-macos)
6. [Análisis de Memoria y Metadatos](#6-análisis-de-memoria-y-metadatos)
7. [Recuperación de Datos (Data Recovery)](#7-recuperación-de-datos-data-recovery)
8. [Suite de Herramientas "DBX" (Utilidades Ligeras)](#8-suite-de-herramientas-dbx-utilidades-ligeras)
9. [Recursos y Mejores Prácticas](#9-recursos-y-mejores-prácticas)

---

## 1. Sistemas Operativos y Distribuciones

¿Por qué usar una Distro Forense Linux?

Permiten acceder a un PC y a sus datos sin alterar el estado original de la evidencia y sin arrancar el sistema operativo nativo del sospechoso, garantizando la integridad de la prueba (Write-blocking por software).

### 🐧 Distribuciones Linux Recomendadas

- **CSI Linux:** Enfocada en investigación cibernética completa.
- **CAINE (Computer Aided Investigative Environment):** Estándar de la industria, interfaz amigable y fuerte en bloqueo de escritura.
- **Tsurugi Linux:** Excelente para DFIR (Digital Forensics & Incident Response) y análisis de malware.
- **SANS SIFT Workstation:** La distribución de facto para análisis profundo y cursos SANS.
- **Kali Linux / Parrot Security OS:** Aunque ofensivas, tienen modos forenses (Forensic Mode) útiles.
- **Tails:** Para privacidad y anonimato extremo durante investigaciones OSINT.
- **AthenaOS / Predator-OS:** Alternativas emergentes en el sector.
- **Paladin Edge:** Basada en bootable USB, ideal para triage rápido.

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
