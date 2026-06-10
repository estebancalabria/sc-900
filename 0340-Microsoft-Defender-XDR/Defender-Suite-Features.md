* **MDE - Microsoft Defender for Endpoint**
    * **EDR - Endpoint Detection and Response**
        * Detección de ataques avanzados en tiempo real basados en el comportamiento del sistema.
        * Línea de tiempo del dispositivo (*Device Timeline*) para forense digital detallado.
        * Acciones de respuesta inmediata como aislar la PC de la red o bloquear archivos.    
    * **NGP - Next-Generation Protection**
        * Antivirus basado en la nube con Machine Learning para amenazas de día cero.
        * Escaneo heurístico permanente de archivos locales.    
    * **AIR - Automated Investigation and Remediation**
        * Motor de Inteligencia Artificial que investiga alertas imitando a un analista humano.
        * Mitigación autónoma que pone malware en cuarentena sin intervención manual.    
    * **ASR - Attack Surface Reduction**
        * Reglas de endurecimiento (*hardening*) del sistema operativo para bloquear vectores comunes de malware.
        * Protección de red (*Network Protection*) para bloquear tráfico saliente hacia IPs maliciosas.
    * **MDVM - Microsoft Defender Vulnerability Management**
        * Inventario de software en tiempo real de todos los dispositivos de la empresa.
        * Detección automática de vulnerabilidades y priorización de parches según el nivel de riesgo.    
    * **AH - Advanced Hunting**
        * Consola de búsqueda proactiva de amenazas mediante consultas en lenguaje KQL.
* **MDI - Microsoft Defender for Identity**
    * **DPI - Deep Packet Inspection**
        * Captura y análisis del tráfico de red que entra y sale de los Controladores de Dominio.
        * Inspección de protocolos críticos de identidad local como Kerberos, NTLM, DNS y RPC.    
    * **EVL - Event Log Analysis**
        * Análisis y correlación directa de los logs de eventos de Windows Server (Active Directory).
    * **UEBA - User and Entity Behavior Analytics**
        * Creación de un perfil de comportamiento habitual para cada usuario y máquina del dominio.
        * Asignación de un puntaje de riesgo dinámico (*User Investigation Priority score*) para identificar usuarios bajo sospecha.
    * **LMD - Lateral Movement Detection**
        * Detección de técnicas de movimiento lateral dentro de la red privada (ej: *Pass-the-Hash* o *Pass-the-Ticket*).  
    * **DDD - Domain Dominance Detection**
        * Alertas tempranas ante intentos de tomar el control total del Active Directory (ej: ataques *Golden Ticket* o modificaciones de permisos *DCShadow*).
    * **ISPM - Identity Security Posture Management**
        * Evaluaciones de seguridad que exponen debilidades del Active Directory local (ej: cuentas con contraseñas que no expiran).
    
    
    * **IDR - Identity Direct Remediation**
    * Capacidad de deshabilitar cuentas o forzar el cambio de contraseña de un usuario local directamente desde el portal en la nube.
