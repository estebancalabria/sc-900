# Take Away

* La plataforma unificada de operaciones de seguridad en el portal de Microsoft Defender unifica las herramientas de Microsoft Sentinel, Defender XDR y Security Copilot, permitiéndoles compartir características avanzadas de búsqueda de amenazas (advanced hunting), gestión de incidentes y asistencia basada en inteligencia artificial generativa.

<img width="2256" height="1076" alt="image" src="https://github.com/user-attachments/assets/c57b5053-6d27-456e-b502-a2f9362a0e23" />

---
## Opciones de Menu

* Home
    * Vistazo general rápido: Es el panel de control principal de la consola.
    * Qué se hace: Muestra un resumen del estado de seguridad de la organización mediante tarjetas con alertas críticas, tareas pendientes y accesos rápidos operativos.
* Exposure management
    * Gestión proactiva del riesgo: Se enfoca en prevenir ataques antes de que ocurran analizando la superficie expuesta.
    * Qué se hace: Monitorear métricas de riesgo como el **Exposure score** para bajar el nivel de vulnerabilidad y el **Secure score** para subir las defensas.
    * Acciones clave: Descubrir qué configuraciones o parches faltan en tus dispositivos, identidades y nubes para cerrar las brechas de seguridad.
* Investigation & response
    * Gestión activa de incidentes: Es el centro de operaciones donde se manejan las amenazas detectadas en tiempo real.
    * Subsección de Incidentes y alertas: Analizar y resolver incidentes, que agrupan alertas relacionadas en una sola historia, y revisar la lista cruda de alertas individuales.
    * Subsección de Hunting: Realizar búsquedas de amenazas proactivas mediante consultas de datos en toda la organización.
    * Subsección de Acciones y sumisiones: Ejecutar acciones de remediación como aislar un equipo infectado o borrar un mail malicioso, y enviar muestras de archivos sospechosos a Microsoft para su análisis.
* Threat intelligence
    * Contexto global de atacantes: El módulo de investigación profunda basado en datos de inteligencia mundial.
    * Qué se hace: Rastrear el comportamiento, herramientas y tácticas de grupos de hackers conocidos, y analizar la reputación de direcciones IP, dominios o archivos sospechosos en internet.
* Assets
    * Inventario centralizado de la empresa: El mapa de todos los recursos que la consola está vigilando de forma activa.
    * Qué se hace: Ver las fichas técnicas, el estado de salud, conexiones y el nivel de riesgo de tus dispositivos, usuarios y aplicaciones.
* Microsoft Sentinel
    * Puente con el SIEM: Integración directa con la torre de control de seguridad global.
    * Qué se hace: Visualizar eventos correlacionados que van más allá del ecosistema de Microsoft, consolidando datos de firewalls locales o nubes de terceros en un único panel operativo.
* Identities
    * Seguridad de cuentas de usuario: Foco exclusivo en los intentos de autenticación y accesos del personal.
    * Qué se hace: Detectar comportamientos anómalos en los inicios de sesión, sospechas de robo de contraseñas o ataques de fuerza bruta contra las cuentas de la organización.
* Email & collaboration
    * Protección del entorno de productividad: Seguridad para el tráfico de mensajería y archivos compartidos.
    * Qué se hace: Configurar y revisar políticas contra phishing o malware transmitido por correo electrónico, Microsoft Teams, SharePoint y OneDrive.
* Cloud apps
    * Control de aplicaciones de terceros: El módulo que supervisa el software como servicio (SaaS).
    * Qué se hace: Auditar qué aplicaciones en la nube usan los empleados para evitar el Shadow IT, detectar transferencias masivas de datos confidenciales y bloquear accesos sospechosos.
* Cloud security
    * Blindaje de la infraestructura de nube: Foco en servidores, contenedores y servicios en entornos virtuales.
    * Qué se hace: Monitorear la postura de seguridad y defender las cargas de trabajo, como máquinas virtuales o bases de datos, que corren en entornos de nube pública.
* SOC optimization
    * Eficiencia del equipo de seguridad: Análisis del rendimiento del Centro de Operaciones de Seguridad.
    * Qué se hace: Evaluar la velocidad de respuesta ante alertas, optimizar las reglas de detección y limpiar falsos positivos para reducir la fatiga de alertas.
* Reports
   * Datos analíticos y ejecutivos: Tableros de control con estadísticas históricas.
   * Qué se hace: Generar informes sobre tendencias de ataques detectados, parches críticos pendientes y niveles de riesgo generales de la empresa para la gerencia.
* Learning hub
      * Capacitación técnica: Acceso a material de entrenamiento integrado en el portal.
      * Qué se hace: Acceder a tutoriales, guías y entrenamientos oficiales para aprender a manejar las herramientas de la plataforma.
* Trials
      * Evaluación de características: Espacio para probar nuevas soluciones.
      * Qué se hace: Activar versiones de prueba de otros módulos o licencias de seguridad avanzados que la empresa aún no tenga contratados.


* More resources
* Enlaces externos: Conexión con el ecosistema de seguridad global de Microsoft.
* Qué se hace: Consultar comunidades de seguridad, blogs técnicos de respuesta a incidentes y documentación externa.


* System
* Configuraciones globales: El panel de administración técnica de la consola.
* Qué se hace: Asignar permisos y roles para los analistas (RBAC), gestionar la configuración general del portal y administrar los conectores de datos entrantes.

---

# Thread Intelligence

* Visión general de Threat intelligence
   * Qué es: Es el módulo especializado en inteligencia de amenazas globales dentro del portal de Microsoft Defender.
   * Función principal: Sirve como un centro de investigación profunda que recopila, indexa y estructura datos sobre atacantes, infraestructuras maliciosas y vulnerabilidades a nivel mundial para ayudar a los analistas a entender el contexto de las amenazas externas.
* Threat analytics
   * Qué es: El panel de análisis e informes de amenazas emergentes.
   * Función clave: Proporciona reportes curados por expertos sobre campañas de ataque activas en internet, detallando el nivel de exposición e impacto real que tienen esas amenazas específicas dentro de tu propia organización.
* Intel management
   * Qué es: El centro de control operativo de tus propios datos de inteligencia.
   * Función clave: Permite administrar, configurar e integrar tus propios indicadores de compromiso (IoCs), fuentes personalizadas y reglas de inteligencia para alimentar los motores de detección.
* Intel profiles
   * Qué es: El catálogo estructurado de perfiles de ciberseguridad.
   * Función clave: Contiene información técnica y detallada sobre actores de amenazas conocidos (grupos de hackers), familias de malware asociadas, tácticas utilizadas y las vulnerabilidades que suelen explotar de forma frecuente.
* Intel explorer
   * Qué es: El motor de búsqueda avanzado del portal.
   * Función clave: Permite a los analistas realizar búsquedas directas de indicadores específicos (direcciones IP, dominios, hashes de archivos), códigos de vulnerabilidades conocidas (CVEs) o palabras clave para dar soporte a investigaciones en curso.
* Intel projects
   * Qué es: El espacio de organización de investigaciones o casos.
   * Función clave: Permite agrupar y organizar indicadores de compromiso (IoCs), artefactos encontrados y analistas colaboradores dentro de un mismo contenedor para llevar un seguimiento estructurado de investigaciones a largo plazo.
---

* La administración de incidentes (incidents) en el portal de Microsoft 365 Defender permite correlacionar múltiples alertas relacionadas para identificar de forma centralizada qué dispositivos, usuarios u otros activos específicos de la organización se ven afectados por un evento de seguridad.

## Soc Optimization (Security Operations Center)

La característica de SOC Optimization dentro del portal unificado de Microsoft Defender entrega recomendaciones basadas en datos para maximizar la eficiencia técnica y el valor operativo de las herramientas de seguridad, ayudando al equipo del SOC a perfeccionar la cobertura de detección frente a amenazas en constante evolución.

### Flujo metodológico de investigación en el SOC

Para entender la lógica cronológica detrás de este ordenamiento, el proceso sigue el ciclo estándar de clasificación, enriquecimiento, análisis profundo y remediación dentro del portal unificado de seguridad:

Paso 1: Triage Inicial (View incident): Todo flujo comienza con la detección y la apertura del caso desde la cola centralizada de Incidents & Alerts. Es el punto de partida obligado para el analista.

Paso 2: Enriquecimiento Contextual Automatizado (Review incident summary): Antes de profundizar manualmente, si la organización cuenta con Security Copilot, se lee el resumen ejecutivo de IA generativa para comprender en segundos la historia general del ataque (línea de tiempo, criticidad e impacto estimado).

Paso 3: Análisis de Evidencia (Analyze alerts & assets): Con el panorama macro claro, el analista realiza el zoom técnico: inspecciona el árbol de alertas relacionadas, revisa qué dispositivos, identidades o buzones de correo (assets) están comprometidos y correlaciona los artefactos preliminares.

Paso 4: Investigación Avanzada (Launch advanced hunting): Si los datos de la alerta no bastan para determinar el alcance total del compromiso, se escala a la búsqueda proactiva usando consultas KQL en Advanced Hunting para desenterrar conexiones ocultas o persistencias del atacante en los logs históricos.

Paso 5: Contención y Remediación (Take response actions): Una vez determinado el veredicto, se aplican las acciones correctivas (aislar un endpoint, suspender un usuario, borrar correos maliciosos). Estas acciones de mitigación se consolidan y ejecutan a través del Action Center.
---

## General

( Microsoft Defender Threat Intelligence (Defender TI) centraliza e indexa la telemetría global de infraestructuras maliciosas expuestas en internet, facilitando a los analistas de seguridad las tareas de búsqueda proactiva de amenazas (threat hunting) y la investigación profunda durante el ciclo de incident response directamente integradas en su consola unificada.

---

* Dentro del portal de Microsoft Defender, la pestaña de activos (Assets) centraliza la visualización de los dispositivos e identidades de la organización, mientras que el centro de aprendizaje (Learning Hub) ofrece un acceso directo a documentación y guías formativas integradas de Microsoft Learn.

---

* Para investigar el alcance total de una campaña de phishing coordinada y ejecutar acciones directas de remediación dentro de Microsoft 365, el equipo de seguridad debe utilizar el Explorador de Amenazas (Threat Explorer), el cual proporciona visibilidad detallada en tiempo real de los correos maliciosos y permite su eliminación o cuarentena.

---

* Microsoft Security Exposure Management consolida la visibilidad de la postura de seguridad dentro del portal de Defender al permitir la simulación y el mapeo de rutas de ataque (attack paths) para identificar debilidades críticas, además de unificar el puntaje de seguridad (Secure Score) global para realizar un seguimiento continuo de las acciones de mejora.

<img width="147" height="169" alt="image" src="https://github.com/user-attachments/assets/4e4b0a10-7ba2-40dd-88fd-faaebb95a8fe" />

---

* Las capacidades de Microsoft Defender Vulnerability Management permiten descubrir y monitorear activos heterogéneos, priorizar de forma inteligente los riesgos mediant inteligencia de amenazas, enviar tareas de remediación automatizadas hacia herramientas externas (como Intune), evaluar el cumplimiento de líneas base de seguridad y consolidar todas las vulnerabilidades (CVEs) detectadas en una página unificada de debilidades.
  
## Asset Discovery and Monitoring (Descubrimiento y Monitoreo de Activos)
      * En el portal de Defender (security.microsoft.com), vas a Assets (Activos) > Devices (Dispositivos). Si entrás a cualquier máquina del inventario y hacés clic en la pestaña Software inventory, vas a ver una lista exacta de programas, versiones y hasta qué extensiones de Chrome o Edge tiene instaladas ese usuario.
      
## Risk-Based Intelligent Prioritization (Priorización Inteligente Basada en Riesgo)

## Remediation and Tracking (Remediación y Seguimiento)
      * Cuando estás viendo una vulnerabilidad en Defender, seleccionás el botón Remediation options. Ahí podés elegir Enviar una tarea de soporte directamente a Microsoft Intune (para que al administrador de TI le aparezca una alerta de "Hay que actualizar el parche de Windows en estas 50 máquinas"). O, en casos críticos, usar la opción de Block application para prohibir que el software vulnerable se ejecute en los endpoints hasta que se actualice.
      
## Baseline Assessments (Evaluaciones de Línea Base)

## Weaknesses Page (Página de Debilidades)
      
           
---
## Microsoft Defender for Endpoint

Microsoft Defender for Endpoint permite interactuar y probar sus capacidades mediante API Explorer, configurar políticas de seguridad de dispositivos basadas en riesgo, e implementar mecanismos preventivos de protección de próxima generación basados en heurística y comportamiento, complementados con capacidades de detección y respuesta en endpoints (EDR) que van más allá del control meramente preventivo.

---

Las capacidades de Endpoint Detection and Response (EDR) integradas en Microsoft Defender para Endpoint permiten a los analistas del SOC realizar análisis forenses avanzados, visualizar la correlación completa de alertas asociadas a una brecha de seguridad y ejecutar acciones de respuesta inmediatas ante comportamientos anómalos como el movimiento lateral entre dispositivos.

--

### Capacidades Oficiales de Microsoft Defender For Endpoint

* Threat and Vulnerability Management (Gestión de Vulnerabilidades): Automática en el descubrimiento. Escanea de forma continua y automática todo el software desactualizado de los equipos y calcula el inventario. Sin embargo, la remediación (instalar el parche de Windows o actualizar Chrome) no es automática por defecto; te genera las tareas para que las ejecutes vos o tu equipo de IT.

* Attack Surface Reduction (ASR): Automática una vez configurada. Las reglas en sí no vienen activadas "de fábrica" porque podrían bloquear programas legítimos de la empresa si no se prueban primero. Vos tenés que entrar al portal y activarlas (ej: "Bloquear macros de Office"). Una vez que las pasás al modo Block, su ejecución es 100% automática e intercepta el ataque en el acto.

* Next-Generation Protection (El Antivirus): 100% Automática. Viene activa por defecto a nivel de sistema operativo. Monitorea el disco en tiempo real, consulta la inteligencia artificial de la nube de Microsoft y manda a cuarentena los archivos infectados al instante sin que nadie tenga que mover un dedo.

* Endpoint Detection and Response (EDR): Automática en grabación y detección, manual en la respuesta base. El EDR graba la "caja negra" de procesos y te dibuja el mapa del incidente de forma totalmente automática. Pero las acciones drásticas de respuesta (como hacer clic en el botón de Isolate Device para aislar una notebook de la red) las tiene que decidir y ejecutar un analista humano.

* Automated Investigation and Remediation (AIR): 100% Automática. Este es justamente el motor diseñado para automatizar lo que el EDR deja en manos humanas. Si el EDR detecta una alerta pesada a las 3 de la mañana, AIR se despierta solo, corre un árbol de investigación virtual, analiza la memoria, busca el virus en otras máquinas y lo limpia de forma autónoma.

* Microsoft Threat Experts: Humana (No automática). Como es un servicio de soporte y hunting compuesto por ingenieros y analistas humanos de Microsoft que revisan casos complejos o responden a tus consultas, no entra en la categoría de automatización por software.
