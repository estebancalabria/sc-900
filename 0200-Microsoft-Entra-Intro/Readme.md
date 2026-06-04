# SC-900: Microsoft Entra y Microsoft Entra ID

## Introducción

Las organizaciones modernas ya no pueden depender únicamente del perímetro de red para proteger sus recursos. Con la adopción de servicios en la nube, trabajo remoto, colaboración externa y agentes impulsados por IA, la **identidad** se ha convertido en el nuevo perímetro de seguridad.

**Microsoft Entra** es la familia de soluciones de Microsoft para la administración de identidades y acceso (IAM), diseñada para implementar estrategias **Zero Trust** y proteger usuarios, dispositivos, aplicaciones, cargas de trabajo y agentes de inteligencia artificial.

---

# Microsoft Entra

Microsoft Entra es una familia de productos organizada según distintos escenarios de acceso seguro.

| Categoría                                | Objetivo                                                                                  |
| ---------------------------------------- | ----------------------------------------------------------------------------------------- |
| Establish Zero Trust access controls     | Identidad, autenticación y servicios de dominio administrados                             |
| Secure access for employees              | Gobierno de identidad, protección de identidad, acceso seguro y credenciales verificables |
| Secure access for customers and partners | Colaboración externa y CIAM                                                               |
| Secure access in any cloud               | Identidades para aplicaciones, servicios y cargas de trabajo                              |
| Secure access for AI agents              | Identidades y gobierno para agentes de IA                                                 |

---

# Productos de Microsoft Entra

## Microsoft Entra ID

Servicio de administración de identidades y acceso basado en la nube de Microsoft.

Permite que:

* Empleados
* Invitados
* Aplicaciones
* Cargas de trabajo
* Agentes de IA

puedan autenticarse y acceder de forma segura a recursos internos y externos.

### Recursos protegidos

#### Recursos internos

* Aplicaciones corporativas
* Intranet
* Recursos on-premises
* Aplicaciones desarrolladas por la organización

#### Recursos externos

* Microsoft 365
* Azure Portal
* Dynamics 365
* Aplicaciones SaaS

### Capacidades principales

* Autenticación
* Autorización
* Single Sign-On (SSO)
* Control de acceso
* Gobierno de identidad
* Protección de identidades

### Beneficios

* Sistema único de identidad para nube y on-premises
* Integración con Active Directory
* Soporte para dispositivos personales (BYOD)
* Colaboración segura con socios y clientes
* Administración centralizada de identidades

---

## Microsoft Entra Domain Services

Proporciona servicios de dominio administrados compatibles con Active Directory tradicional.

Permite ejecutar aplicaciones heredadas en la nube sin administrar controladores de dominio.

---

## Microsoft Entra Private Access

Permite acceso seguro a aplicaciones y recursos privados sin necesidad de VPN.

Características:

* Acceso remoto seguro
* Compatible con entornos híbridos y multicloud
* Acceso a recursos internos desde cualquier ubicación

---

## Microsoft Entra Internet Access

Protege el acceso a Internet y aplicaciones SaaS.

Funciones:

* Seguridad web
* Protección para Microsoft 365
* Filtrado de contenido
* Control de acceso basado en dominios y categorías

---

## Microsoft Entra ID Governance

Automatiza la administración de identidades y permisos.

Permite:

* Solicitudes de acceso
* Asignación automática de permisos
* Revisiones de acceso
* Gestión del ciclo de vida de identidades

---

## Microsoft Entra ID Protection

Detecta riesgos relacionados con identidades.

Funciones:

* Usuarios riesgosos
* Inicios de sesión sospechosos
* Evaluación continua de riesgos
* Integración con Conditional Access

---

## Microsoft Entra Verified ID

Servicio de credenciales verificables basado en estándares DID (Decentralized Identity).

Permite emitir y validar:

* Diplomas
* Certificaciones
* Credenciales digitales

---

## Microsoft Entra External ID

Permite administrar identidades externas para clientes, socios, proveedores e invitados.

Incluye:

* B2B Collaboration
* B2B Direct Connect
* Customer Identity and Access Management (CIAM)

---

## Microsoft Entra Workload ID

Administra identidades para:

* Aplicaciones
* Servicios
* APIs
* Contenedores
* Automatizaciones

Permite autenticación y autorización para cargas de trabajo.

---

## Microsoft Entra Agent ID

Extiende la administración de identidades a agentes de inteligencia artificial.

Permite:

* Autenticar agentes
* Autorizar acciones
* Aplicar Conditional Access
* Gestionar riesgos
* Auditar actividades
* Gobernar identidades no humanas

---

# Identity Secure Score

Identity Secure Score es una métrica incluida en Microsoft Entra ID.

Mide qué tan alineada está una organización con las mejores prácticas de seguridad recomendadas por Microsoft.

Características:

* Disponible en todas las ediciones
* Expresado como porcentaje
* Incluye recomendaciones personalizadas
* Permite medir la evolución de la postura de seguridad

---

# Terminología fundamental

## Tenant

Instancia de Microsoft Entra ID que representa una organización.

Contiene:

* Usuarios
* Grupos
* Dispositivos
* Aplicaciones
* Políticas
* Configuraciones de cumplimiento

Características:

* Tenant ID único
* Dominio asociado
* Límite administrativo y de seguridad

Ejemplo:

```text
contoso.onmicrosoft.com
```

---

## Directory

Contenedor lógico que almacena los objetos de identidad.

Incluye:

* Usuarios
* Grupos
* Aplicaciones
* Dispositivos

Un Tenant contiene un único Directory.

---

## Multi-Tenant

Organización que utiliza múltiples instancias de Microsoft Entra ID.

Casos comunes:

* Subsidiarias
* Unidades de negocio
* Fusiones y adquisiciones
* Requisitos regulatorios regionales

---

# Tipos de identidades

Microsoft Entra ID permite asignar identidades a:

| Categoría           | Ejemplos                              |
| ------------------- | ------------------------------------- |
| Human Identities    | Usuarios                              |
| Device Identities   | PCs, móviles, servidores, IoT         |
| Workload Identities | Aplicaciones, servicios, contenedores |
| Agent Identities    | Agentes de IA                         |

Las identidades de dispositivos y cargas de trabajo suelen agruparse como **Machine Identities**.

---

# Identidades de usuario

Representan personas que necesitan acceder a recursos.

Ejemplos:

* Empleados
* Clientes
* Consultores
* Proveedores
* Socios

## Según autenticación

### Internal Authentication

El usuario se autentica mediante el Tenant de la organización.

### External Authentication

El usuario se autentica mediante:

* Otro Tenant de Microsoft Entra
* Redes sociales
* Proveedores de identidad externos

---

## Según UserType

### Member

Usuario miembro de la organización.

### Guest

Usuario externo con permisos limitados.

---

## Escenarios de usuarios

| Tipo            | Autenticación | UserType |
| --------------- | ------------- | -------- |
| Internal Member | Interna       | Member   |
| External Guest  | Externa       | Guest    |
| External Member | Externa       | Member   |
| Internal Guest  | Interna       | Guest    |

---

# Workload Identities

Identidades asignadas a software.

Ejemplos:

* Aplicaciones
* APIs
* Servicios
* Contenedores
* Automatizaciones

Permiten autenticación segura sin utilizar cuentas de usuario.

---

## Application Object

Representa la definición global de una aplicación registrada.

Contiene:

* Configuración
* Permisos
* Métodos de autenticación

---

## Service Principal

Representa la identidad de una aplicación dentro de un Tenant.

Funciones:

* Autenticación
* Autorización
* Acceso a recursos

Una aplicación puede tener múltiples Service Principals en distintos tenants.

---

# Managed Identities

Tipo especial de Service Principal administrado automáticamente por Azure.

Beneficios:

* No requiere almacenar secretos
* Azure administra las credenciales
* Reduce riesgos operativos

---

## System-Assigned Managed Identity

* Asociada a un único recurso Azure
* Comparte su ciclo de vida
* Se elimina automáticamente junto con el recurso

---

## User-Assigned Managed Identity

* Recurso independiente
* Puede reutilizarse en múltiples recursos
* Debe eliminarse manualmente

---

# Agent Identities

Introducidas por Microsoft Entra Agent ID.

Representan agentes de inteligencia artificial que requieren acceso seguro a recursos empresariales.

---

# Microsoft Entra Agent ID

## ¿Por qué los agentes necesitan identidades específicas?

Los agentes de IA:

* Toman decisiones dinámicas
* Adaptan comportamientos según el contexto
* Operan de forma autónoma
* Interactúan con múltiples sistemas

Esto genera desafíos específicos:

### Superficie de ataque ampliada

* Integración con sistemas externos
* Riesgo de Prompt Injection
* Manipulación de contexto

### Riesgos de permisos

* Acceso excesivo a información
* Acciones fuera de su propósito previsto

### Agent Sprawl

* Crecimiento descontrolado de agentes
* Falta de visibilidad
* Problemas de cumplimiento y auditoría

---

## Agent Identity Blueprint

Plantilla reutilizable que define una clase de agentes.

Contiene:

* Clasificación del agente
* Configuración de acceso
* Credenciales utilizadas
* Políticas aplicables

Ejemplo:

```text
Sales Assistant Agent Blueprint
```

---

## Agent Identity

Instancia individual creada a partir de un Blueprint.

Cada Agent Identity posee:

* Identificador único
* Nombre descriptivo
* Sponsor responsable

Las Agent Identities no almacenan credenciales propias; utilizan el Blueprint para obtener autenticación.

---

## Escenarios de autenticación

### Attended (On-Behalf-Of)

El agente actúa en representación de un usuario.

Utiliza:

* Permisos delegados
* Autoridad del usuario

### Unattended

El agente actúa como identidad autónoma.

Utiliza:

* Roles propios
* Permisos propios

---

## Gobierno y seguridad

### Conditional Access

Permite aplicar políticas específicas para agentes.

### Identity Protection

Proporciona:

* Detección de riesgos
* Monitoreo continuo
* Respuesta automática

### Identity Governance

Permite:

* Gestión del ciclo de vida
* Asignación de accesos
* Cumplimiento normativo

### Agent Registry

Repositorio centralizado para:

* Inventario de agentes
* Descubrimiento de agentes
* Metadatos
* Seguimiento operativo

---

## Principio de mínimo privilegio

Microsoft limita las capacidades de los agentes:

* Restricción de roles privilegiados
* Limitación de permisos críticos
* Prevención de escalación de privilegios

---

# Device Identities

Representan dispositivos físicos.

Ejemplos:

* Laptops
* Smartphones
* Tablets
* Servidores
* Impresoras
* Dispositivos IoT

---

## Microsoft Entra Registered

Diseñado para escenarios BYOD.

Características:

* Dispositivo personal
* Registro ligero
* Acceso a recursos corporativos

---

## Microsoft Entra Joined

Características:

* Dispositivo propiedad de la organización
* Inicio de sesión corporativo
* Administración desde la nube

---

## Microsoft Entra Hybrid Joined

Características:

* Unido a Active Directory local
* Unido a Microsoft Entra ID

Ideal para organizaciones híbridas.

---

# Grupos

Permiten asignar permisos a múltiples identidades simultáneamente.

---

## Security Groups

Utilizados para acceso y seguridad.

Pueden contener:

* Usuarios
* Dispositivos
* Otros grupos
* Service Principals
* Agent Identities

---

## Microsoft 365 Groups

Orientados a colaboración.

Proporcionan acceso compartido a:

* Outlook
* Calendarios
* SharePoint
* Teams
* Archivos

Solo pueden contener usuarios.

---

## Tipos de membresía

### Assigned Membership

Asignación manual.

### Dynamic Membership

Asignación automática mediante reglas basadas en atributos.

---

# Identidad Híbrida (Hybrid Identity)

Permite disponer de una identidad común para recursos locales y en la nube.

Objetivos:

* Autenticación unificada
* Administración centralizada
* Experiencia consistente para los usuarios

---

## Provisioning

Creación y administración de identidades entre directorios.

### Inter-Directory Provisioning

Permite crear identidades entre Active Directory y Microsoft Entra ID.

---

## Synchronization

Garantiza consistencia entre:

* Active Directory
* Microsoft Entra ID

---

## Microsoft Entra Cloud Sync

Herramienta recomendada por Microsoft para sincronización híbrida.

Ventajas:

* Agente ligero
* Administración desde la nube
* Alta disponibilidad
* Soporte multi-forest

---

## Microsoft Entra Connect Sync

Herramienta anterior de sincronización híbrida.

Actualmente está siendo reemplazada por Cloud Sync.

---

## SCIM

System for Cross-domain Identity Management.

Estándar utilizado para:

* Provisioning
* Deprovisioning
* Sincronización de identidades

---

# Microsoft Entra External ID

Permite administrar identidades externas para colaboración y acceso seguro.

Las identidades externas pueden provenir de:

* Microsoft Entra ID
* Google
* Facebook
* Otros proveedores de identidad

---

## Workforce Tenant

Diseñado para:

* Empleados
* Recursos internos
* Colaboración B2B

Permite invitar usuarios externos.

---

## External Tenant

Diseñado para:

* Clientes
* Consumidores
* Aplicaciones públicas
* Escenarios CIAM

---

## B2B Collaboration

Permite compartir recursos con socios externos.

Características:

* Los usuarios utilizan sus propias credenciales
* No es necesario administrar contraseñas externas
* Acceso a Microsoft 365, SaaS y aplicaciones corporativas

---

## Customer Identity and Access Management (CIAM)

Orientado a aplicaciones para clientes y consumidores.

Incluye:

* Registro de usuarios
* Inicio de sesión social
* SSO
* Administración de cuentas de clientes

---

## B2B Direct Connect

Establece una relación de confianza entre dos organizaciones Microsoft Entra.

Características:

* Los usuarios permanecen en su tenant de origen
* No se crean usuarios Guest
* Utilizado por Teams Shared Channels

---

# Licenciamiento

## Microsoft Entra ID Free

Incluye:

* Usuarios y grupos
* Reportes básicos
* Self-Service Password Reset

---

## Microsoft Entra ID P1

Incluye:

* Conditional Access
* Identidad híbrida
* Funciones avanzadas de grupos

---

## Microsoft Entra ID P2

Incluye:

* Identity Protection
* Risk-Based Conditional Access
* Privileged Identity Management (PIM)

---

## Microsoft Entra Suite

Incluye:

* Private Access
* Internet Access
* ID Governance
* ID Protection
* Capacidades premium de Verified ID

Requiere Microsoft Entra ID P1.

---

# Microsoft Entra Admin Center

Portal centralizado para administrar:

* Usuarios
* Dispositivos
* Aplicaciones
* Políticas
* Seguridad
* Productos Microsoft Entra

---

# Conceptos clave para SC-900

* Microsoft Entra es la plataforma de identidad y acceso de Microsoft.
* Microsoft Entra ID es el servicio central de IAM basado en la nube.
* Un Tenant representa una organización.
* Un Directory almacena los objetos de identidad.
* Existen identidades de usuario, dispositivo, workload y agentes.
* Service Principals representan aplicaciones dentro de un Tenant.
* Managed Identities eliminan la necesidad de administrar credenciales.
* Microsoft Entra Agent ID extiende Zero Trust a agentes de IA.
* Identity Secure Score mide la postura de seguridad.
* Hybrid Identity unifica identidades locales y cloud.
* Microsoft Entra Cloud Sync es la herramienta recomendada para sincronización híbrida.
* SCIM es el estándar para aprovisionamiento de identidades.
* B2B Collaboration permite compartir recursos con invitados.
* CIAM protege aplicaciones orientadas a clientes.
* B2B Direct Connect habilita colaboración directa entre tenants.
* Security Groups gestionan acceso; Microsoft 365 Groups gestionan colaboración.
* Microsoft Entra implementa una estrategia de seguridad basada en Zero Trust.
