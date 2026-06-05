# Seguridad de Infraestructura en Microsoft Azure

## Introducción

A medida que las organizaciones migran hacia entornos híbridos y completamente basados en la nube, el perímetro de seguridad tradicional evoluciona constantemente. La protección de aplicaciones, recursos y datos requiere una estrategia de seguridad en capas capaz de enfrentar amenazas provenientes de distintos vectores.

Microsoft Azure implementa una estrategia basada en **Defense in Depth (Defensa en Profundidad)** y **Zero Trust**, utilizando múltiples servicios que trabajan conjuntamente para proteger redes, aplicaciones, máquinas virtuales, identidades y secretos.

Los principales servicios de seguridad de infraestructura son:

* Azure DDoS Protection
* Azure Firewall
* Web Application Firewall (WAF)
* Azure Virtual Network (VNet)
* Network Security Groups (NSG)
* Application Security Groups (ASG)
* Azure Bastion
* Azure Key Vault

---

# Azure DDoS Protection

## ¿Qué es un ataque DDoS?

Un ataque de Denegación de Servicio Distribuido (DDoS) intenta saturar aplicaciones o servicios mediante grandes cantidades de tráfico malicioso para impedir que usuarios legítimos puedan acceder.

## Tipos de ataques

### Volumétricos

Saturan el ancho de banda disponible mediante enormes cantidades de tráfico.

### De Protocolo

Explotan vulnerabilidades de las capas de red y transporte.

### De Aplicación

Atacan directamente aplicaciones y servicios web.

---

## Azure DDoS Protection

Servicio administrado diseñado para detectar y mitigar automáticamente ataques DDoS.

### Capas protegidas

* Capa 3 (Network)
* Capa 4 (Transport)

### Características

* Monitoreo continuo 24x7.
* Mitigación automática.
* Ajuste adaptativo del perfil de tráfico.
* Alertas automáticas.
* Integración con Azure Monitor.
* Telemetría avanzada y análisis de ataques.

### Beneficios

* Detección específica para cada aplicación.
* Umbrales personalizados.
* Métricas históricas.
* Alertas de inicio y finalización de ataques.

---

## Niveles

### DDoS Network Protection

Incluye:

* Protección avanzada para VNets.
* DDoS Rapid Response (DRR).
* Protección de costos.
* Beneficios adicionales relacionados con WAF.

### DDoS IP Protection

* Protección individual por IP pública.
* Modelo de pago por IP protegida.

---

## DDoS Rapid Response (DRR)

Disponible con DDoS Network Protection.

Permite acceso a especialistas de Microsoft para:

* Investigar ataques activos.
* Analizar incidentes.
* Brindar asistencia durante ataques complejos.

---

## Buenas Prácticas

* Combinar DDoS Protection con WAF.
* Diseñar aplicaciones resilientes.
* Configurar monitoreo y alertas.
* Tener un plan de respuesta a incidentes.

---

# Azure Firewall

## ¿Qué es Azure Firewall?

Firewall administrado, nativo de Azure y altamente disponible que permite controlar y filtrar tráfico de red mediante reglas centralizadas.

### Arquitectura Recomendada

Implementarlo en una VNet centralizada (Hub) para proteger:

* Redes virtuales Azure.
* Redes On-Premises.

---

## Características Principales

### Stateful Firewall

Mantiene el estado de las conexiones activas.

### Alta Disponibilidad

* Integrada.
* Escalado automático.
* Compatible con Availability Zones.

### Filtrado de Red y Aplicaciones

Permite reglas basadas en:

* Direcciones IP.
* Puertos.
* Protocolos.
* HTTP/HTTPS.
* FQDN.

### NAT

#### SNAT

Convierte IP privadas en públicas.

#### DNAT

Publica recursos internos mediante IP públicas.

### Threat Intelligence

Detecta y bloquea:

* Direcciones IP maliciosas.
* Dominios maliciosos.

### Logging y Monitorización

Integración con:

* Azure Monitor.
* Log Analytics.
* Event Hubs.

---

## Niveles

### Basic

* Orientado a PyMES.
* Throughput aproximado de 250 Mbps.

### Standard

* Filtrado de capas 3 a 7.
* Protección empresarial estándar.

### Premium

Incluye:

* IDPS (Intrusion Detection and Prevention System).
* Más de 67.000 firmas de amenazas.
* Protección contra malware, phishing y exploits.

---

## Azure Firewall Manager

Permite administrar múltiples firewalls mediante políticas centralizadas reutilizables.

---

## Integración con Security Copilot

Permite investigar tráfico bloqueado, amenazas y eventos IDPS utilizando lenguaje natural.

---

# Web Application Firewall (WAF)

## ¿Qué es WAF?

Web Application Firewall (WAF) proporciona protección centralizada para aplicaciones web frente a vulnerabilidades y ataques comunes de capa 7.

Permite proteger múltiples aplicaciones desde un único punto de administración.

---

## Amenazas que Mitiga

### SQL Injection

Inserción de código SQL malicioso para acceder o modificar información.

### Cross-Site Scripting (XSS)

Inyección de scripts maliciosos en navegadores de usuarios.

### HTTP Flood

Ataques DDoS de capa 7.

### Remote File Inclusion (RFI)

Intentos de ejecutar archivos remotos maliciosos.

---

## Basado en OWASP

Utiliza el OWASP Core Rule Set para detectar y bloquear amenazas conocidas.

---

## Opciones de Implementación

### Azure Application Gateway

Protección regional.

### Azure Front Door

Protección global.

### Azure CDN

Protección de contenido distribuido.

---

## Relación con Azure DDoS Protection

| Servicio              | Capas Protegidas |
| --------------------- | ---------------- |
| Azure DDoS Protection | 3 y 4            |
| Azure WAF             | 7                |

Ambos servicios deben utilizarse conjuntamente para lograr una estrategia de Defense in Depth.

---

## Integración con Security Copilot

Permite:

* Analizar eventos WAF.
* Investigar ataques.
* Revisar registros.
* Consultar información mediante lenguaje natural.

---

# Segmentación de Red en Azure

## Objetivos

* Agrupar recursos relacionados.
* Aplicar controles de seguridad.
* Limitar movimientos laterales.
* Aislar cargas de trabajo.

La segmentación es fundamental para:

* Zero Trust.
* Defense in Depth.

---

## Principio Assume Breach

Zero Trust asume que una brecha puede ocurrir.

La segmentación permite:

* Contener ataques.
* Reducir impacto.
* Evitar propagación lateral.

---

# Azure Virtual Network (VNet)

## ¿Qué es?

Es el bloque fundamental de red privada dentro de Azure.

Proporciona:

* Escalabilidad.
* Aislamiento.
* Alta disponibilidad.

---

## Características

### Aislamiento

Por defecto:

* No existe comunicación entre VNets.
* No existe acceso entrante desde Internet.

Toda comunicación debe configurarse explícitamente.

### Comunicación con Internet

Los recursos pueden realizar conexiones salientes.

### Comunicación entre Recursos Azure

Los recursos dentro de una misma VNet pueden comunicarse de forma privada.

### Conectividad On-Premises

Mediante:

* Site-to-Site VPN.
* Point-to-Site VPN.
* Azure ExpressRoute.

### Filtrado de Tráfico

Utiliza:

* NSG.
* Azure Firewall.

### Enrutamiento

Azure proporciona enrutamiento automático y rutas personalizadas.

---

# Subnets

## ¿Qué son?

Segmentos lógicos dentro de una VNet.

Permiten separar cargas de trabajo según sus requisitos de seguridad.

### Beneficios

* Aislamiento.
* Seguridad.
* Organización.
* Contención de incidentes.

---

# VNet Peering

## ¿Qué es?

Permite conectar dos VNets como si fueran una sola red.

### Características

* Comunicación privada.
* Baja latencia.
* Utiliza el backbone global de Microsoft.
* No utiliza Internet pública.

### Global VNet Peering

Permite conectar VNets ubicadas en distintas regiones.

---

# Azure Network Security Groups (NSG)

## ¿Qué es un NSG?

Servicio que filtra tráfico entrante y saliente hacia recursos de una VNet.

Puede asociarse a:

* Subnets.
* Interfaces de red (NIC).

---

## Componentes de una Regla

### Nombre

Identificador único.

### Prioridad

* Menor número = Mayor prioridad.
* La primera coincidencia finaliza la evaluación.

### Origen y Destino

* IP.
* Rangos IP.
* Service Tags.
* ASG.

### Protocolo

* TCP
* UDP
* ICMP
* Any

### Puerto

Individual o rango.

### Dirección

* Inbound.
* Outbound.

### Acción

* Allow.
* Deny.

---

## Reglas Predeterminadas

### Inbound

* AllowVNetInBound
* AllowAzureLoadBalancerInBound
* DenyAllInBound

### Outbound

* AllowVNetOutBound
* AllowInternetOutBound
* DenyAllOutBound

Estas reglas no pueden eliminarse, pero sí sobrescribirse mediante reglas con mayor prioridad.

---

# Application Security Groups (ASG)

## ¿Qué son?

Permiten agrupar máquinas virtuales según la función que cumplen dentro de una aplicación.

Ejemplos:

* WebServers
* AppServers
* DbServers

Las reglas NSG pueden aplicarse a grupos lógicos en lugar de direcciones IP.

---

## Beneficios

* Simplifican la administración.
* Facilitan el escalado.
* Reflejan la arquitectura de la aplicación.

---

# Diferencias entre NSG y Azure Firewall

| Característica      | NSG         | Azure Firewall |
| ------------------- | ----------- | -------------- |
| Alcance             | Distribuido | Centralizado   |
| Capas               | L3-L4       | L3-L7          |
| Threat Intelligence | No          | Sí             |
| NAT                 | No          | Sí             |
| FQDN                | No          | Sí             |
| Administración      | Local       | Centralizada   |

Microsoft recomienda utilizar ambos servicios para implementar Defense in Depth.

---

# Azure Bastion

## Problema que Resuelve

Tradicionalmente, para administrar máquinas virtuales era necesario exponer puertos de administración:

* RDP (3389)
* SSH (22)

Esto aumenta significativamente la superficie de ataque.

---

## ¿Qué es Azure Bastion?

Azure Bastion es un servicio PaaS administrado que proporciona acceso seguro a máquinas virtuales mediante:

* RDP
* SSH

Directamente desde:

* Azure Portal
* Navegador Web

Sin necesidad de exponer puertos de administración a Internet.

---

## Funcionamiento

Azure Bastion se implementa dentro de una VNet.

Una vez desplegado:

* Todas las VMs de la VNet pueden utilizarlo.
* También funciona con VNets conectadas mediante Peering.

La conexión se realiza mediante:

* TLS
* Puerto 443

---

## Beneficios

### Acceso desde Azure Portal

Conexión RDP y SSH con un clic.

### Sin IP Pública

Las máquinas virtuales utilizan únicamente IP privada.

### Sin Software Adicional

Cliente HTML5 integrado en el navegador.

### Protección contra Escaneo de Puertos

Los puertos SSH y RDP nunca quedan expuestos.

### Menor Administración

No requiere configuración compleja de NSGs para acceso remoto.

### Protección frente a Vulnerabilidades

Azure mantiene Bastion actualizado y endurecido frente a amenazas.

---

## Niveles

### Developer

* Gratuito.
* Infraestructura compartida.
* Desarrollo y pruebas.

### Basic

* Infraestructura dedicada.
* Funcionalidades básicas.

### Standard

Incluye:

* Escalabilidad.
* Native Client.
* Shareable Links.
* Transferencia de archivos.

### Premium

Incluye:

* Grabación de sesiones.
* Implementación Private-Only.
* Cumplimiento normativo y auditoría.

---

## Métodos de Conexión

### Browser-Based

Desde Azure Portal mediante HTML5.

### Native Client

Utiliza clientes SSH o RDP instalados localmente.

### Shareable Links

Permite compartir enlaces seguros de acceso.

---

# Azure Key Vault

## ¿Qué es Azure Key Vault?

Azure Key Vault es un servicio cloud diseñado para almacenar y administrar de forma segura:

* Secretos.
* Claves criptográficas.
* Certificados digitales.

Su objetivo es centralizar y proteger información sensible utilizada por aplicaciones y servicios.

---

## Problemas que Resuelve

### Secrets Management

Almacenamiento seguro de:

* Contraseñas.
* API Keys.
* Tokens.
* Connection Strings.
* Secretos de aplicaciones.

### Key Management

Administración de claves criptográficas utilizadas para cifrar datos.

### Certificate Management

Administración del ciclo de vida de certificados TLS/SSL:

* Aprovisionamiento.
* Renovación.
* Implementación.

---

## ¿Por qué Utilizar Key Vault?

### Centralización de Secretos

Los desarrolladores no necesitan almacenar credenciales dentro del código fuente.

Las aplicaciones recuperan secretos en tiempo de ejecución mediante identificadores únicos.

### Seguridad

El acceso requiere:

#### Autenticación

Realizada mediante Microsoft Entra ID.

#### Autorización

Puede realizarse mediante:

* Azure RBAC.
* Access Policies de Key Vault.

### Microsoft No Puede Ver los Secretos

Azure Key Vault está diseñado para que Microsoft no pueda acceder ni extraer:

* Secretos.
* Claves.
* Certificados.

---

## Monitoreo y Auditoría

Key Vault registra:

* Accesos.
* Operaciones.
* Intentos de uso.

Los logs pueden enviarse a:

* Azure Monitor.
* SIEM.
* Soluciones de almacenamiento.

Beneficios:

* Auditoría.
* Cumplimiento normativo.
* Investigación de incidentes.

---

## Alta Disponibilidad

Azure replica automáticamente el contenido:

* Dentro de la región.
* En una región secundaria.

No requiere intervención administrativa.

---

## Separación de Secretos

Es posible crear un Key Vault por:

* Aplicación.
* Equipo.
* Entorno.

Esto permite aplicar el principio de mínimo privilegio.

---

## Key Vault y Zero Trust

Azure Key Vault implementa directamente el principio:

### Least Privilege Access

Cada usuario o aplicación recibe acceso únicamente a los secretos necesarios.

Beneficios:

* Reduce el impacto de credenciales comprometidas.
* Limita la superficie de ataque.
* Mejora la seguridad general.

---

## Integración con Servicios Azure

### Azure Disk Encryption

Almacena claves utilizadas para cifrar discos de máquinas virtuales.

### Azure SQL Database

Administra claves de cifrado utilizadas para proteger bases de datos.

### Azure App Service

Permite obtener:

* API Keys.
* Connection Strings.
* Secretos.

Sin almacenarlos en código o archivos de configuración.

### Gestión de Certificados

Automatiza:

* Emisión.
* Renovación.
* Implementación.

De certificados TLS/SSL.

---

## Niveles de Azure Key Vault

### Standard

* Protección basada en software.
* Adecuado para la mayoría de los escenarios empresariales.

### Premium

Incluye:

* Hardware Security Module (HSM).
* Claves protegidas por hardware.
* Cumplimiento de requisitos regulatorios estrictos.

### ¿Qué es un HSM?

Un **Hardware Security Module** es un dispositivo especializado diseñado para:

* Generar claves criptográficas.
* Almacenar claves de forma segura.
* Evitar que las claves abandonen el hardware.

---

# Conceptos Clave para el Examen

## Azure DDoS Protection

* Protege capas 3 y 4.
* Network Protection incluye DRR.
* Debe combinarse con WAF.

## Azure Firewall

* Firewall administrado y stateful.
* Soporta SNAT y DNAT.
* Premium incluye IDPS.
* Utiliza Threat Intelligence.

## WAF

* Protege capa 7.
* Basado en OWASP.
* Mitiga SQL Injection, XSS, HTTP Flood y RFI.

## Azure Virtual Network

* Red privada fundamental de Azure.
* Aislamiento por defecto.
* Soporta VPN y ExpressRoute.

## NSG

* Filtra tráfico entrante y saliente.
* Se asocia a Subnets y NICs.
* Menor prioridad numérica = mayor prioridad.

## ASG

* Agrupa VMs según función.
* Simplifica reglas NSG.

## Azure Bastion

* Acceso seguro RDP/SSH.
* No requiere IP pública.
* Utiliza TLS sobre puerto 443.
* Evita exponer puertos 22 y 3389.

## Azure Key Vault

* Almacena secretos, claves y certificados.
* Utiliza Entra ID para autenticación.
* Soporta Azure RBAC y Access Policies.
* Implementa Least Privilege Access.
* Se integra con Azure Disk Encryption, SQL y App Service.
* Premium utiliza HSM.

# Resumen Final

La seguridad de infraestructura en Azure se basa en los principios de **Zero Trust** y **Defense in Depth**. Azure DDoS Protection protege las capas de red y transporte frente a ataques de denegación de servicio. Azure Firewall proporciona control centralizado del tráfico y protección avanzada mediante Threat Intelligence e IDPS. WAF protege aplicaciones web frente a ataques de capa 7. Las VNets, Subnets, NSG y ASG permiten segmentar y controlar las comunicaciones internas. Azure Bastion proporciona acceso remoto seguro sin exponer puertos de administración, mientras que Azure Key Vault centraliza la administración de secretos, claves y certificados aplicando el principio de mínimo privilegio. En conjunto, estos servicios crean una arquitectura segura, resiliente y alineada con las mejores prácticas de seguridad modernas.
