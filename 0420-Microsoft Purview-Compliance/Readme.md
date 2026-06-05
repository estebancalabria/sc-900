### Microsoft Purview – Resumen completo (Compliance Manager + Communication Compliance + eDiscovery + Audit + Data Lifecycle Management + Records Management)

Microsoft Purview es un conjunto integral de soluciones accesibles desde el portal de Microsoft Purview, diseñado para ayudar a las organizaciones a gobernar, proteger y gestionar los datos en todo su entorno de información. Incluye capacidades de cumplimiento, seguridad, auditoría y gestión del ciclo de vida de los datos que permiten reducir riesgos, cumplir regulaciones y responder a incidentes legales o de seguridad.

---

## Microsoft Purview Portal

El **portal de Microsoft Purview** es la plataforma unificada para acceder a todas las soluciones, organizadas en cuatro áreas principales:

* **Core**: Audit, Data Map, Settings y Workflows.
* **Risk & Compliance**: Communication Compliance, Compliance Manager, eDiscovery, Information Barriers y Records Management.
* **Data Governance**: Data Catalog, Data Lifecycle Management y Data Policy.
* **Data Security**: Data Loss Prevention, Information Protection e Insider Risk Management.

---

# Compliance Manager (Risk & Compliance)

Permite evaluar y gestionar el cumplimiento en entornos multicloud.

### Objetivo

* Identificar riesgos de cumplimiento
* Implementar controles
* Cumplir normativas
* Reportar postura de cumplimiento

### Capacidades

* Evaluaciones predefinidas y personalizadas
* Flujos de trabajo guiados
* Acciones de mejora
* Controles compartidos (Microsoft + cliente)
* **Compliance Score**

### Compliance Score

* Puntos del cliente + Microsoft
* Permite medir, priorizar y reportar progreso

### Elementos clave

* Controles
* Assessments
* Regulations (360+ plantillas, incluidas IA)
* Improvement Actions

---

# Communication Compliance (Insider Risk Management)

Detecta y gestiona comunicaciones inapropiadas o riesgosas.

### Objetivo

* Prevenir riesgos internos
* Detectar incumplimientos de políticas
* Reducir riesgos regulatorios

### Alcance

* Teams, Outlook, Viva Engage
* Microsoft 365 Copilot
* Apps externas

### Flujo

Configure → Investigate → Remediate → Maintain

### Integraciones

* Insider Risk Management
* Microsoft Security Copilot

---

# eDiscovery (Risk & Compliance)

Permite identificar, preservar y analizar evidencia electrónica para casos legales.

### Objetivo

Apoyar investigaciones legales y regulatorias.

### Servicios

* Exchange Online
* Teams
* SharePoint
* OneDrive
* Viva Engage

### Workflow

* Escalación de caso
* Creación de caso
* Búsqueda y análisis
* Holds, exportación y review sets
* Revisión final

### Premium

* Review Sets
* OCR
* Conversation threading
* Decryption

### Integraciones

* Insider Risk Management
* Microsoft Security Copilot

---

# Audit in Microsoft Purview

Registra actividades de usuarios y administradores en Microsoft 365 mediante el **Unified Audit Log**.

### Actividades registradas

* Exchange (emails, reenvíos, borrados)
* SharePoint / OneDrive (accesos, descargas, compartición)
* Teams (mensajes, reuniones)
* Entra ID (sign-ins, roles, políticas)
* Copilot (prompts y respuestas)
* Otros servicios Microsoft 365

### Uso

* Investigaciones forenses
* Respuesta a incidentes
* Cumplimiento normativo
* Análisis de impacto

### Acceso

* Portal Purview
* Graph API
* PowerShell
* APIs de actividad (SIEM)

---

## Tipos de auditoría

### Audit (Standard)

* Activado por defecto
* Retención: 180 días
* Búsqueda en portal
* Exportación CSV

### Audit (Premium)

* Retención extendida (hasta 10 años)
* Políticas de retención personalizadas
* Insights avanzados
* Mayor capacidad API

---

## Copilot auditing

* Microsoft 365 Copilot: registro automático de prompts y respuestas
* Security Copilot: requiere habilitación (opt-in) y registra acciones y resultados

---

# Microsoft Purview Data Lifecycle Management

Permite retener lo necesario y eliminar lo innecesario para reducir riesgos y cumplir regulaciones.

---

## Retention policies y retention labels

### Objetivo

* Cumplimiento normativo
* Reducción de riesgo
* Mantener contenido relevante

### Acciones

* **Retain-only**: conservar
* **Delete-only**: eliminar
* **Retain then delete**: conservar y luego eliminar

### Funcionamiento

* El contenido permanece en su ubicación
* Las copias eliminadas se conservan en almacenamiento seguro
* Transparente para el usuario

---

## Retention policies vs labels

### Policies

* Aplicación a nivel sitio o buzón
* Herencia por contenedor
* No siguen el contenido fuera del tenant

### Labels

* Aplicación a nivel ítem
* Pueden moverse dentro del tenant
* Manual o automática
* Soportan revisión antes de eliminación

---

## Capacidades adicionales

* Mailbox archiving (incluye auto-expanding)
* Inactive mailboxes (retención de ex-empleados)
* Adaptive Protection (integración con Insider Risk Management)
* Retención de interacciones de IA (Copilot incluido en Exchange mailbox)

---

# Microsoft Purview Records Management

Extiende Data Lifecycle Management para controlar **registros críticos legales, regulatorios y de negocio**.

---

## Objetivo

* Cumplimiento legal y regulatorio
* Reducción de riesgos
* Gestión de registros de alto valor

---

## Diferencia con Data Lifecycle Management

* DLM: retención general del contenido
* Records Management: control estricto de contenido crítico (registros)

---

## Funcionalidades principales

* Etiquetado como registro
* Políticas de retención dentro del registro
* Retención basada en eventos
* Revisión de disposición
* Evidencia de eliminación (proof of disposition)
* Exportación de registros eliminados

---

## Tipos de registros

* Records
* Regulatory records (más restrictivos)

### Regulatory records

* No se puede quitar la etiqueta (ni por admins globales)
* No se puede reducir el período de retención
* Requiere habilitación especial (PowerShell)

---

## Event-based retention

El conteo de retención inicia desde un evento, no una fecha fija.

### Ejemplos

* Fin de empleo
* Fin de contrato
* Retiro de producto

---

## Disposition reviews

* Revisión antes de eliminar contenido
* Permite aprobar o extender retención
* Genera evidencia de cumplimiento (auditabilidad)

---

## File plan

Permite estructurar la gestión de retención:

* Importar planes de retención existentes
* Centralizar etiquetas
* Agregar metadatos (autoridad regulatoria, función de negocio)

---

## Casos de uso

* Aplicación manual de retención
* Aplicación automática de políticas
* Configuración por bibliotecas o sitios
* Reglas de Outlook para retención

---

## Buenas prácticas

* Capacitación a usuarios
* Consistencia en aplicación de etiquetas
* Definición clara de políticas organizacionales

---

# Cierre general

Microsoft Purview ofrece una plataforma unificada para gobernar datos, asegurar cumplimiento, investigar incidentes, auditar actividades y gestionar el ciclo de vida completo de la información. Con Compliance Manager, Communication Compliance, eDiscovery, Audit, Data Lifecycle Management y Records Management, las organizaciones pueden controlar riesgos, cumplir regulaciones y administrar información crítica de forma estructurada, automatizada y escalable.
