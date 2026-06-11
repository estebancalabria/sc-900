### 1. El Portal Central (Donde converge todo)

**Microsoft 365 Defender (Consola Unificada):** No es un producto suelto, es el portal web principal (`security.microsoft.com`). Es el panel donde los analistas del SOC ven los incidentes correlacionados de todos los "Defender" que te detallo abajo.

* Soluciones
  * **Microsoft Defender for Endpoint (MDE)**
  * **Microsoft Defender for Cloud Apps (MDCA)**
  * **Microsoft Defender for Identity (MDI)**
  * **Microsoft Defender for Office 365 (MDO)**
  * **Microsoft Defender for Cloud (MDfC)**

---

### **Microsoft Defender for Endpoint (MDE)**

Microsoft Defender for Endpoint ofrece capacidades avanzadas de protección para dispositivos que incluyen la investigación y remediación automatizada de alertas de seguridad, así como reglas de reducción de la superficie de ataque (attack surface reduction) para minimizar los vectores vulnerables en los endpoints de la organización.

*  Protección del Puesto de Trabajo e Infraestructura Local (Endpoints e Identidad)

* **Qué protege:** Las computadoras de los usuarios (Windows, Mac, Linux), celulares (Android, iOS) y servidores corporativos. Es el antivirus avanzado (EDR). Se instala una aplicacion en el dispositivo que queda registrado en security.microsoft.com

* **Dónde se encuentra/administra:** Las alertas e investigaciones se hacen en el portal de Defender, pero las políticas de instalación y configuración de los agentes se empujan masivamente desde **Microsoft Intune**.
 
* Key Words
  * Attack Surface Reduction (ASR)
    * Reglas que bloquean comportamientos maliciosos comunes
  * Next-generation protection
    * Antivirus basado en ML y análisis en la nube
  * Endpoint Detection and Response (EDR)
    * Detección de amenazas avanzadas y respuesta post-breach
  * Auto investigation and remediatio
    * Investigación automática de alertas sin intervención manual
  * Threat and Vulnerability Management (TVM)
    * Inventario de vulnerabilidades y recomendaciones de hardening
 

---

**Microsoft Defender for Cloud Apps (MDCA)**

Microsoft Defender for Cloud Apps es un Cloud Access Security Broker (CASB) que actúa como intermediario de seguridad entre los usuarios y los servicios en la nube. Permite descubrir aplicaciones no autorizadas (Shadow IT), controlar sesiones en tiempo real y proteger datos sensibles en entornos SaaS de terceros.

- Protección del Uso de Aplicaciones Cloud (SaaS y Shadow IT)
- Qué protege: Las aplicaciones cloud que usan los empleados, tanto autorizadas (Microsoft 365, Salesforce, ServiceNow) como no autorizadas (Dropbox personal, Google Drive, apps desconocidas). Detecta comportamiento anómalo de usuarios en esas apps.
- Dónde se encuentra/administra: Se administra en **security.microsoft.com → Cloud apps**. Se integra con Defender for Endpoint para capturar tráfico de dispositivos, o con firewalls/proxies para análisis de logs.
- Key Words
   - **Cloud Access Security Broker (CASB)**
      - Intermediario de seguridad entre usuarios y servicios cloud
   - **Shadow IT Discovery**
      - Descubrimiento automático de apps no autorizadas usadas por empleados
   - **Conditional Access App Control**
      - Control de sesiones en tiempo real integrado con Entra ID (ej: bloquear descarga de archivos desde dispositivos no corporativos)
   - **Cloud DLP**
      - Escaneo y clasificación de archivos sensibles en nubes de terceros como Google Drive o Dropbox
   - **UEBA - User and Entity Behavior Analytics**
      - Detección de anomalías como descargas masivas, viajes imposibles o logins inusuales
   - **App Governance**
      - Control de apps OAuth de terceros que piden permisos a Microsoft 365
   - **SSPM - SaaS Security Posture Management**
      - Recomendaciones de hardening para configuraciones inseguras en apps SaaS como Salesforce o Microsoft 365

---

**Microsoft Defender for Identity (MDI)**

Microsoft Defender for Identity es una solución de seguridad basada en la nube que recopila y analiza señales y tráfico de los controladores de dominio locales (Active Directory on-premises) para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones maliciosas dirigidas a la organización.

- **Qué protege:** Las identidades y la autenticación local en Active Directory. Detecta ataques basados en credenciales como movimientos laterales, ataques de fuerza bruta y pass-the-hash.
- **Dónde se encuentra/administra:** Las alertas e investigaciones se hacen en **security.microsoft.com**, pero requiere instalar físicamente un **MDI Sensor** dentro de los Domain Controllers (Controladores de Dominio) del **Active Directory Domain Services (AD DS)** on-premises. El sensor captura el tráfico localmente y lo envía a la nube de Microsoft para su análisis.
- Key Words
   - **MDI Sensor**
      - Agente instalado físicamente en los Domain Controllers para capturar tráfico de red y eventos de autenticación
   - **Lateral Movement Detection**
      - Detección de movimientos laterales entre equipos usando credenciales comprometidas
   - **Pass-the-Hash / Pass-the-Ticket**
      - Detección de ataques que roban y reutilizan hashes de contraseñas o tickets de Kerberos
   - **Reconnaissance Detection**
      - Detección de enumeración de usuarios, grupos y equipos del dominio (fase previa al ataque)
   - **Compromised Identity**
      - Identificación de cuentas de Active Directory que están siendo usadas de forma maliciosa
   - **Impossible Travel**
      - Detección de logins desde ubicaciones geográficamente imposibles para el mismo usuario
   - **Integration con Active Directory (AD DS)**
      - Se instala exclusivamente en entornos con Active Directory on-premises, no aplica a entornos 100% cloud

---

**Microsoft Defender for Office 365 (MDO)**

Microsoft Defender for Office 365 es una solución de seguridad basada en la nube que protege a las organizaciones contra amenazas avanzadas en el correo electrónico y las herramientas de colaboración de Microsoft 365, incluyendo phishing, malware, links maliciosos y archivos adjuntos peligrosos.

- **Qué protege:** El correo electrónico (Exchange Online), Teams, SharePoint y OneDrive. Analiza emails entrantes y salientes, archivos adjuntos y links en busca de contenido malicioso antes de que lleguen al usuario.
- **Dónde se encuentra/administra:** Se administra en **security.microsoft.com → Email & collaboration**. No requiere instalación de agentes, opera directamente sobre los servicios de Microsoft 365 en la nube.
- Key Words
   - **Safe Attachments**
      - Abre los archivos adjuntos en un entorno aislado (sandbox) antes de entregarlos al usuario para detectar malware
   - **Safe Links**
      - Reescribe y verifica los links de emails y documentos en tiempo real al momento del clic
   - **Anti-phishing**
      - Detección de suplantación de identidad (impersonation) de usuarios y dominios conocidos
   - **Anti-malware**
      - Escaneo de emails y archivos en busca de malware conocido
   - **Attack Simulation Training**
      - Simulaciones de phishing controladas para entrenar y concientizar a los usuarios
   - **Threat Explorer**
      - Herramienta de investigación para analizar emails maliciosos detectados en el tenant
   - **Zero-hour Auto Purge (ZAP)**
      - Elimina retroactivamente emails ya entregados cuando se detecta que son maliciosos después de la entrega

---

**Microsoft Defender for Cloud (MDfC)**

Microsoft Defender for Cloud es una plataforma de protección de aplicaciones nativa de la nube (CNAPP) que combina gestión de postura de seguridad y protección de workloads para entornos Azure, multicloud (AWS, GCP) y on-premises, proporcionando visibilidad centralizada y protección activa contra amenazas en toda la infraestructura.

- **Qué protege:** Infraestructura cloud y on-premises: máquinas virtuales, contenedores, bases de datos, storage, App Service, Key Vault y recursos de AWS y GCP. No protege usuarios ni emails, protege **recursos e infraestructura**.
- **Dónde se encuentra/administra:** Se administra en **portal.azure.com → Microsoft Defender for Cloud**. No requiere instalación manual en recursos Azure, pero requiere instalar el **Azure Monitor Agent** en servidores on-premises o VMs para extender la cobertura.
- Key Words
   - **CSPM - Cloud Security Posture Management**
      - Evalúa configuraciones inseguras en suscripciones Azure, AWS y GCP y genera un Secure Score
   - **CWP - Cloud Workload Protection**
      - Protección activa contra amenazas para VMs, contenedores, bases de datos y storage
   - **Secure Score**
      - Métrica central que mide la postura de seguridad de la infraestructura y prioriza mejoras
   - **Regulatory Compliance**
      - Dashboard que mapea la postura del tenant contra estándares como PCI-DSS, ISO 27001 y NIST
   - **Just-in-Time VM Access (JIT)**
      - Bloquea puertos RDP/SSH y los abre solo cuando se solicitan explícitamente, reduciendo superficie de ataque
   - **Defender CSPM (paid)**
      - Plan avanzado que agrega Attack Path Analysis y Cloud Security Explorer
   - **Hybrid Security**
      - Extiende la protección a servidores on-premises mediante Azure Arc
   - **Attack Path Analysis**
      - Identifica rutas que un atacante podría usar para moverse lateralmente entre recursos cloud


---

### 4. Protección de Infraestructura de Nube (Servidores, Base de Datos y APIs)

Este bloque pertenece al mundo de **Azure** y la arquitectura multinube. Aunque sus alertas críticas pueden viajar al portal central de Defender, su panel nativo de configuración y control de postura está en la consola de **Microsoft Defender for Cloud** dentro del portal de Azure.

* **Microsoft Defender for Servers:** Protege máquinas virtuales que corren en Azure, AWS, Google Cloud o servidores físicos remotos.
* **Microsoft Defender for Storage:** Protege los datos guardados en cuentas de almacenamiento en la nube frente a malware o accesos indebidos.
* **Microsoft Defender for SQL / Databases:** Monitorea y detecta inyecciones de código o accesos anómalos en bases de datos virtuales.
* **Microsoft Defender for Containers:** Protege la infraestructura basada en Kubernetes y registros de imágenes de contenedores.
* **Microsoft Defender for APIs:** Audita y protege las interfaces de programación (endpoints de APIs) públicas expuestas ante ataques web o abusos de tokens.
