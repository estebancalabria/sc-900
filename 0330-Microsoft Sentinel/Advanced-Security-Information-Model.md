# ¿Qué tablas tiene el ASIM?

Para entender qué tablas tiene, primero recuerda el problema que resuelve: si tenés un firewall Cisco, uno Palo Alto y un Azure Firewall, cada uno guarda el log de una conexión de red con nombres de columnas distintos (SrcIP, source_ip, ip_origen). ASIM (Advanced Security Information Model) unifica esto.

ASIM no crea tablas físicas nuevas con nombres extraños; lo que hace es usar Vistas o Funciones de consulta (Parsers) que transforman los logs heterogéneos y los exponen bajo esquemas (schemas) normalizados.

Cuando haces consultas KQL en Sentinel utilizando ASIM, usas estos nombres de esquemas principales (que actúan como si fuesen tablas unificadas):

imNetworkSession: Unifica todo el tráfico de red (Firewalls, Proxies, VPC logs).

imAuditLogs: Unifica auditorías de sistemas (quién creó qué, cambios de configuración).

imAuthentication: Unifica los inicios de sesión (exitosos o fallidos) de cualquier sistema operativo o proveedor de identidad.

imProcess: Unifica la creación y ejecución de procesos en servidores y endpoints.

imFileEvent: Unifica la actividad sobre archivos (creación, borrado, modificación).

imDns: Unifica las consultas y respuestas de servidores DNS (clave para detectar malware que habla con servidores de comando y control).

💡 Tip de examen: La "im" al principio de estos nombres significa Information Model. Al usar imNetworkSession en tu query, buscas en los logs de Cisco, Palo Alto y Azure Firewall al mismo tiempo sin importar cómo formatee cada uno.
