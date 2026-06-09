  # Take Away

* Azure Firewall se integra con Azure Security Center y Azure Policy para reforzar el cumplimiento y la gobernanza, mientras que Security Copilot permite analizar toda su actividad de red ejecutando tanto instrucciones predefinidas (built-in prompts) como peticiones personalizadas (custom prompts).

---

* Un Grupo de Seguridad de Red (NSG) se puede asociar a múltiples interfaces de red (NIC), aplicando reglas personalizadas que se procesan por orden numérico ascendente de prioridad sin necesidad de eliminar (ni poder borrar) las reglas de seguridad predeterminadas del sistema.

---

* Las botnets suelen estructurarse con equipos de usuarios comprometidos, mientras que en la arquitectura de red de Azure las subredes de una misma VNet se comunican de forma predeterminada, pudiendo restringirse mediante NSGs (aplicables a subredes o NICs) y protegerse de múltiples vulnerabilidades web complejas mediante Azure WAF.
  
---

## Firewall

Azure Firewall opera como un servicio de seguridad perimetral de alta disponibilidad con redundancia de zonas nativa que filtra tráfico de red y de aplicación basándose en reglas y en un motor automatizado de inteligencia de amenazas, permitiendo además la exportación flexible de sus registros diagnósticos hacia diversas plataformas de análisis y monitoreo centralizado.

---

## DDOS

* Para proteger una aplicación web frente a picos de tráfico anómalos que degradan su rendimiento sin activar la protección básica de la infraestructura, se debe implementar Azure DDoS Network Protection, el cual proporciona mitigación personalizada basada en el comportamiento de la aplicación y telemetría detallada.

---

* Azure DDoS Protection mitiga comúnmente tres categorías principales de ataques de denegación de servicio distribuido:
  * Ataques volumétricos (inundación de ancho de banda),
    * El objetivo: Saturar el ancho de banda de tu red. El atacante inunda las IPs públicas de tu Azure con una cantidad monstruosa de tráfico basura para que los usuarios legítimos no puedan pasar.
    * Ejemplos comunes: Inundaciones UDP (UDP floods), inundaciones ICMP, o ataques de amplificación NTP/DNS (donde usan servidores externos para multiplicar el peso del tráfico que golpea a Azure).
  * Ataques de protocolo a nivel de red (explotación de debilidades de la pila de protocolos)
    * El objetivo: Agotar la capacidad de procesamiento de tus dispositivos de red (como firewalls, balanceadores de carga o switches virtuales) explotando cómo funcionan los protocolos de internet.
    * Ejemplos comunes: * SYN Floods: El atacante inicia miles de conexiones TCP pero nunca las completa (no manda el ACK final). El servidor se queda esperando, manteniendo los sockets abiertos hasta que se queda sin memoria para atender a nadie más.
      *Ataques de fragmentación de paquetes IP.
  * Ataques a la capa de recursos o aplicación.
    * El objetivo: Apuntar directamente a los paquetes de la aplicación web de manera volumétrica para colapsar el servidor (Capa 4/7 transicional).
    * Cómo lo maneja Azure: Bloquea las inyecciones masivas de tráfico HTTP malformado o ráfagas extrañas que intentan agotar los recursos de cómputo (CPU/Memoria) de las instancias de tus aplicaciones web, actuando como escudo perimetral antes de que el tráfico toque tus servidores.

---


## WAF

* Para proteger una aplicación web en Azure frente a vulnerabilidades del OWASP Top 10 como inyección SQL y Cross-Site Scripting (XSS) mediante reglas administradas que se actualizan automáticamente con una configuración manual mínima, la solución idónea es implementar Azure Web Application Firewall (WAF).

* En Azure, tenés dos lugares principales donde podés colgar el WAF, dependiendo de tu arquitectura:
  * Azure Application Gateway: Si tu aplicación es regional (está en una sola zona/VNet y balanceás tráfico a nivel local).
  * Azure Front Door: Si tu aplicación es global (multiregión, con CDN y alta disponibilidad mundial).
