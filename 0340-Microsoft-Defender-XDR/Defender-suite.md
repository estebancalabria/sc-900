### 1. El Portal Central (Donde converge todo)

* **Microsoft 365 Defender (Consola Unificada):** No es un producto suelto, es el portal web principal (`security.microsoft.com`). Es el panel donde los analistas del SOC ven los incidentes correlacionados de todos los "Defender" que te detallo abajo.

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

* **Microsoft Defender for Identity (MDI)**
* **Qué protege:** Las identidades y la autenticación local. Detecta ataques basados en credenciales (movimientos laterales, ataques de fuerza bruta).
* **Dónde se encuentra/administra:** Se investiga en el portal de Defender, pero requiere instalar fícisamente un sensor (*MDI Sensor*) dentro de los **Domain Controllers (Controladores de Dominio)** locales de la empresa.
* Microsoft Defender for Identity es una solución de seguridad basada en la nube que recopila y analiza las señales y el tráfico de los controladores de dominio locales (Active Directory on-premises) para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones maliciosas dirigidas a la organización.
* Microsoft Defender for Identity se instala exclusivamente en los controladores de dominio locales (AD DS) para capturar el tráfico de red y los eventos de la oficina, pero envía esa información a la nube de Microsoft para su análisis y detección de amenazas.



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
