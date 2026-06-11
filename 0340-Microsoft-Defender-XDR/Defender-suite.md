### 1. El Portal Central (Donde converge todo)

**Microsoft 365 Defender (Consola Unificada):** No es un producto suelto, es el portal web principal (`security.microsoft.com`). Es el panel donde los analistas del SOC ven los incidentes correlacionados de todos los "Defender" que te detallo abajo.

* Soluciones
  * **Microsoft Defender for Endpoint (MDE)**
  * **Microsoft Defender for Cloud Apps (MDCA)**
  * **Microsoft Defender for Identity (MDI)**

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

### 3. Protección del Entorno de Productividad (SaaS, Correo y Colaboración)

* **Microsoft Defender for Office 365 (MDO)**
* **Qué protege:** El ecosistema de colaboración y mensajería de la empresa. Frena correos de phishing, archivos adjuntos maliciosos y links truchos. Protege **Exchange Online, Teams, SharePoint y OneDrive**.
* **Dónde se encuentra/administra:** Está integrado directamente de forma nativa en la nube de Microsoft 365. Se configura y gestiona desde la sección de *Email & Collaboration* del portal de Defender.


* **Microsoft Defender for Cloud Apps (MDCA)**
* **Qué protege:** La seguridad de las aplicaciones en la nube de terceros (SaaS). Es el "guardaespalda" (CASB) que vigila qué hacen los usuarios en plataformas como Salesforce, Google Drive, Dropbox o AWS para evitar la fuga de datos y el Shadow IT.
* **Dónde se encuentra/administra:** Se gestiona en el portal de Defender (en la sección *Cloud Apps*), y se nutre del tráfico de red reportado por las computadoras o los firewalls de la empresa.



---

### 4. Protección de Infraestructura de Nube (Servidores, Base de Datos y APIs)

Este bloque pertenece al mundo de **Azure** y la arquitectura multinube. Aunque sus alertas críticas pueden viajar al portal central de Defender, su panel nativo de configuración y control de postura está en la consola de **Microsoft Defender for Cloud** dentro del portal de Azure.

* **Microsoft Defender for Servers:** Protege máquinas virtuales que corren en Azure, AWS, Google Cloud o servidores físicos remotos.
* **Microsoft Defender for Storage:** Protege los datos guardados en cuentas de almacenamiento en la nube frente a malware o accesos indebidos.
* **Microsoft Defender for SQL / Databases:** Monitorea y detecta inyecciones de código o accesos anómalos en bases de datos virtuales.
* **Microsoft Defender for Containers:** Protege la infraestructura basada en Kubernetes y registros de imágenes de contenedores.
* **Microsoft Defender for APIs:** Audita y protege las interfaces de programación (endpoints de APIs) públicas expuestas ante ataques web o abusos de tokens.
