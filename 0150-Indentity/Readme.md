# 🔐 SC-900 - Conceptos Fundamentales de Identidad

## Introducción

La identidad es la forma en que personas, dispositivos, aplicaciones y agentes de IA demuestran quiénes son al intentar acceder a recursos digitales.

En la actualidad, los usuarios trabajan desde cualquier lugar, utilizan múltiples dispositivos y acceden tanto a recursos locales como a servicios en la nube. Como resultado, la seguridad ya no puede depender únicamente de la red corporativa.

Por esta razón:

> La identidad es el nuevo perímetro de seguridad.

La identidad se ha convertido en el principal mecanismo para controlar el acceso a aplicaciones, datos y servicios.

---

# Objetivos del Módulo

Al finalizar este módulo deberías ser capaz de:

* Definir autenticación y autorización.
* Explicar cómo trabajan juntas para controlar el acceso.
* Comprender por qué la identidad es el nuevo perímetro de seguridad.
* Identificar los cuatro pilares de una infraestructura de identidad.
* Comprender el rol de los Identity Providers.
* Explicar el funcionamiento de los tokens y Single Sign-On.
* Comprender los servicios de directorio.
* Diferenciar Active Directory Domain Services y Microsoft Entra ID.
* Comprender el concepto de federación.

---

# El Fin del Perímetro Tradicional

## Modelo Tradicional

Históricamente las organizaciones protegían sus recursos mediante:

* Firewalls
* VPNs
* Segmentación de red

Este modelo asumía que todo lo que estaba dentro de la red corporativa era confiable.

Funcionaba correctamente cuando:

* Los usuarios trabajaban en oficinas.
* Las aplicaciones residían en servidores locales.
* Los dispositivos eran administrados por la organización.

---

## ¿Qué Cambió?

### Cloud Computing y SaaS

Las aplicaciones ya no están dentro de la red corporativa.

Ejemplos:

* Microsoft 365
* CRM
* ERP
* Herramientas de colaboración

### Trabajo Remoto e Híbrido

Los usuarios acceden desde:

* Hogares
* Cafeterías
* Aeropuertos
* Redes públicas

### BYOD (Bring Your Own Device)

Los empleados utilizan dispositivos personales.

### Acceso de Partners y Clientes

Usuarios externos necesitan acceder a recursos corporativos.

### Internet of Things (IoT)

Miles de dispositivos conectados interactúan con sistemas organizacionales.

---

## La Nueva Pregunta de Seguridad

Antes:

> ¿La solicitud proviene de la red corporativa?

Ahora:

> ¿Quién o qué está realizando esta solicitud y debería confiar en ello?

Por este motivo, la identidad reemplaza al perímetro de red como principal límite de confianza.

---

# ¿Qué es una Identidad?

Una identidad es el conjunto de atributos que describen una entidad.

Puede incluir:

* Nombre de usuario
* Correo electrónico
* Roles
* Permisos
* Métodos de autenticación
* Estado de cumplimiento
* Información del dispositivo

---

# Tipos de Identidades

## Human Identities

Representan personas.

Ejemplos:

* Empleados
* Contratistas
* Clientes
* Partners

---

## Device Identities

Representan dispositivos físicos.

Ejemplos:

* Laptops
* Smartphones
* Tablets
* Dispositivos IoT

---

## Workload Identities

Representan software.

Ejemplos:

* Aplicaciones
* APIs
* Servicios
* Contenedores

---

## Agent Identities

Representan agentes de Inteligencia Artificial.

Ejemplos:

* Copilots
* Agentes autónomos
* Sistemas multiagente

---

# Authentication (Autenticación)

La autenticación verifica la identidad.

Responde a la pregunta:

> ¿Quién eres?

El sistema solicita evidencia de identidad y valida que sea legítima antes de conceder acceso.

---

## Factores de Autenticación

### Algo que sabes

* Contraseña
* PIN
* Preguntas de seguridad

### Algo que tienes

* Smartphone
* Smart Card
* Hardware Token
* Llave FIDO2

### Algo que eres

* Huella digital
* Reconocimiento facial
* Escaneo de iris

---

## Single-Factor Authentication (SFA)

Utiliza un único factor de autenticación.

Ejemplo:

* Usuario y contraseña

Si el factor es comprometido, la cuenta queda expuesta.

---

## Multifactor Authentication (MFA)

Requiere dos o más factores de categorías distintas.

Ejemplo:

* Contraseña
* Aprobación desde el teléfono móvil

Beneficios:

* Reduce secuestros de cuentas
* Mitiga ataques de phishing
* Incrementa la confianza en la identidad

---

# Authorization (Autorización)

La autorización determina qué acciones puede realizar una identidad autenticada.

Responde a la pregunta:

> ¿Qué tienes permitido hacer?

---

## Elementos Utilizados

### Roles

Ejemplos:

* Empleado
* Supervisor
* Administrador

### Permisos

Ejemplos:

* Leer
* Crear
* Modificar
* Eliminar

### Atributos

Ejemplos:

* Departamento
* Ubicación
* Cargo

---

## Principle of Least Privilege

Los usuarios deben tener únicamente los permisos mínimos necesarios para realizar sus tareas.

Beneficios:

* Menor impacto ante cuentas comprometidas
* Menor exposición de datos
* Menor riesgo operativo
* Mayor cumplimiento normativo

---

# Relación entre Authentication y Authorization

```text
Authentication
        ↓
Authorization
        ↓
Access Granted / Denied
```

Primero se verifica la identidad.

Luego se evalúan permisos y privilegios.

Finalmente se concede o deniega el acceso.

---

# Los Cuatro Pilares de una Infraestructura de Identidad

## 1. Administration

Gestiona el ciclo de vida completo de las identidades.

Incluye:

* Provisioning
* Actualización
* Asignación de roles
* Deprovisioning
* Políticas de identidad

---

## 2. Authentication

Verifica que una identidad sea quien afirma ser.

---

## 3. Authorization

Determina qué puede hacer una identidad autenticada.

---

## 4. Auditing

Registra actividades relacionadas con la identidad.

Incluye:

* Logs de inicio de sesión
* Actividades de usuarios
* Alertas
* Investigaciones forenses

---

# Modern Authentication

La autenticación moderna centraliza los procesos de autenticación y autorización mediante un Identity Provider.

Las aplicaciones dejan de administrar usuarios y contraseñas individualmente y delegan estas responsabilidades a un sistema central.

---

# Identity Provider (IdP)

Un Identity Provider (IdP) es un sistema encargado de:

* Crear identidades
* Mantener identidades
* Administrar identidades
* Autenticar usuarios
* Autorizar accesos
* Auditar actividades

Las aplicaciones confían en el Identity Provider para validar identidades.

---

## Flujo de Autenticación Moderna

1. El usuario intenta acceder a una aplicación.
2. La aplicación redirige al usuario al Identity Provider.
3. El IdP valida las credenciales.
4. El IdP emite un token.
5. El usuario presenta el token a la aplicación.
6. La aplicación valida el token y concede acceso.

---

# ¿Por Qué Centralizar la Autenticación?

Sin un Identity Provider central:

* Cada aplicación administra usuarios propios.
* Existen múltiples contraseñas.
* Las políticas de seguridad son inconsistentes.
* La administración se vuelve compleja.

Beneficios:

* MFA centralizado
* Políticas consistentes
* Gestión central del ciclo de vida
* Visibilidad completa de accesos
* Menor carga administrativa

---

# Security Tokens

Un token es una credencial digital emitida por el Identity Provider después de autenticar una identidad.

La aplicación utiliza el token como prueba de autenticación.

Los tokens tienen duración limitada y expiran automáticamente.

---

# Claims

Los tokens contienen información denominada claims.

Ejemplos:

* Identificador único
* Nombre
* Correo electrónico
* Roles
* Grupos
* Permisos
* Fecha de emisión
* Fecha de expiración

---

# Tipos de Tokens

## ID Token

Prueba que la autenticación fue exitosa.

Permite identificar:

* Quién es el usuario

---

## Access Token

Permite acceder a recursos específicos.

Define:

* Qué puede hacer el usuario

---

# Protocolos de Autenticación Moderna

## OpenID Connect (OIDC)

Protocolo moderno de autenticación.

Permite:

* Verificar identidad
* Obtener información básica del usuario

Está construido sobre OAuth 2.0.

---

## OAuth 2.0

Protocolo de autorización.

Permite obtener Access Tokens para acceder a recursos protegidos.

Su objetivo principal es delegar acceso.

---

## Security Assertion Markup Language (SAML)

Protocolo ampliamente utilizado en escenarios empresariales.

Frecuente en:

* Aplicaciones corporativas tradicionales
* Integraciones empresariales
* Escenarios de federación

---

# Single Sign-On (SSO)

Single Sign-On permite iniciar sesión una sola vez y acceder a múltiples aplicaciones.

## Funcionamiento

1. El usuario inicia sesión en el Identity Provider.
2. El IdP emite un token.
3. El usuario accede a diferentes aplicaciones.
4. Las aplicaciones validan el token.
5. No es necesario volver a autenticarse.

## Beneficios

### Mejor experiencia de usuario

Menos credenciales para recordar.

### Mayor seguridad

Menor exposición al phishing.

Menor reutilización de contraseñas.

### Administración centralizada

Deshabilitar una cuenta en el IdP elimina el acceso a todas las aplicaciones conectadas.

---

# Servicios de Directorio (Directory Services)

## ¿Qué es un Directorio?

Un directorio es un repositorio estructurado que almacena información sobre:

* Usuarios
* Dispositivos
* Grupos
* Aplicaciones
* Políticas

---

## ¿Qué es un Directory Service?

Es el software encargado de almacenar y administrar la información del directorio.

Permite responder preguntas como:

* ¿Quién es este usuario?
* ¿A qué grupos pertenece?
* ¿Qué recursos puede utilizar?

Los Directory Services constituyen la base de Authentication y Authorization.

---

# Active Directory Domain Services (AD DS)

AD DS es el servicio de directorio tradicional de Microsoft para entornos on-premises.

Fue introducido con Windows 2000 Server.

---

## Domain Controller (DC)

Un servidor que ejecuta AD DS se denomina:

> Domain Controller (DC)

Responsabilidades:

* Almacenar el directorio
* Autenticar usuarios
* Aplicar políticas
* Gestionar recursos

---

## Capacidades de AD DS

* Identidad única para múltiples sistemas
* Administración centralizada
* Group Policy
* Kerberos
* NTLM
* Organizational Units (OU)

---

# Limitaciones de AD DS

AD DS fue diseñado para redes corporativas tradicionales.

Presenta limitaciones en:

* Aplicaciones cloud
* SaaS
* Dispositivos móviles
* OAuth 2.0
* OpenID Connect
* Trabajo remoto sin VPN

Estas limitaciones impulsaron la aparición de soluciones cloud-native.

---

# Microsoft Entra ID

Microsoft Entra ID es la evolución moderna de los servicios de identidad para la nube.

Implementa el modelo:

> Identity as a Service (IDaaS)

Microsoft opera la infraestructura y la organización consume el servicio.

---

## Características Principales

* Cloud Native
* OAuth 2.0
* OpenID Connect
* SAML
* MFA
* Conditional Access
* Single Sign-On
* Integración SaaS
* Compatibilidad multiplataforma

---

# Hybrid Identity

Muchas organizaciones utilizan simultáneamente:

* Active Directory Domain Services
* Microsoft Entra ID

Esto se conoce como:

> Hybrid Identity

Permite acceder a recursos locales y cloud utilizando las mismas credenciales.

---

# Federación (Federation)

La federación permite que usuarios autenticados en una organización accedan a recursos de otra organización sin necesidad de crear cuentas adicionales.

La federación se basa en relaciones de confianza entre Identity Providers.

---

## Cómo Funciona la Federación

La federación puede compararse con un pasaporte.

Un país emite el pasaporte y otros países confían en él como prueba de identidad.

De forma similar:

1. Una organización autentica a su usuario.
2. Su Identity Provider emite un token.
3. Otra organización confía en ese Identity Provider.
4. El acceso es concedido según las políticas definidas.

---

## Relaciones de Confianza (Trust Relationships)

La federación depende de relaciones de confianza explícitas entre Identity Providers.

Importante:

> La confianza no es automáticamente bidireccional.

Si la Organización A confía en la Organización B:

* B puede acceder a recursos de A.

Pero eso no implica que:

* A pueda acceder a recursos de B.

La confianza bidireccional debe configurarse explícitamente.

---

## Escenarios Comunes de Federación

### Business-to-Business (B2B)

Dos organizaciones colaboran compartiendo recursos.

Ejemplos:

* Portales compartidos
* Aplicaciones conjuntas
* Espacios de colaboración

Los usuarios utilizan sus propias credenciales corporativas.

---

### Identidades Sociales

Cuando una aplicación permite iniciar sesión mediante:

* Google
* Microsoft
* GitHub

se está utilizando federación.

La aplicación confía en el proveedor externo para autenticar al usuario.

---

### Integración con Active Directory

Las organizaciones pueden extender la autenticación de Active Directory hacia servicios cloud.

Para ello se utiliza:

Active Directory Federation Services

AD FS permite emitir tokens que servicios externos aceptan como prueba de identidad.

---

## Beneficios de la Federación

* Menor cantidad de cuentas
* Menor administración
* Mejor experiencia de usuario
* Mayor seguridad
* Colaboración entre organizaciones
* Acceso simplificado a recursos externos

---

## Microsoft Entra ID y Federación

Microsoft Entra ID soporta escenarios de federación para:

* Partners
* Clientes
* Proveedores
* Usuarios externos

permitiendo extender relaciones de confianza sin necesidad de crear cuentas adicionales.

---

# Resumen para el Examen

| Concepto           | Idea Clave                                      |
| ------------------ | ----------------------------------------------- |
| Identity           | Nuevo perímetro de seguridad                    |
| Human Identity     | Personas                                        |
| Device Identity    | Dispositivos                                    |
| Workload Identity  | Aplicaciones y servicios                        |
| Agent Identity     | Agentes de IA                                   |
| Authentication     | Verifica quién eres                             |
| Authorization      | Determina qué puedes hacer                      |
| MFA                | Dos o más factores de autenticación             |
| Least Privilege    | Acceso mínimo necesario                         |
| Administration     | Gestión del ciclo de vida                       |
| Auditing           | Registro y monitoreo                            |
| Identity Provider  | Autentica, autoriza y emite tokens              |
| Token              | Credencial digital                              |
| Claim              | Información contenida en un token               |
| ID Token           | Identidad del usuario                           |
| Access Token       | Permisos del usuario                            |
| OIDC               | Autenticación                                   |
| OAuth 2.0          | Autorización                                    |
| SAML               | Federación e integración empresarial            |
| SSO                | Un inicio de sesión para múltiples aplicaciones |
| Directory Service  | Repositorio centralizado de identidades         |
| AD DS              | Directorio tradicional on-premises              |
| Domain Controller  | Servidor que ejecuta AD DS                      |
| Microsoft Entra ID | Identity Provider cloud de Microsoft            |
| IDaaS              | Identity as a Service                           |
| Hybrid Identity    | AD DS + Entra ID                                |
| Federation         | Confianza entre Identity Providers              |
| B2B Federation     | Acceso entre organizaciones                     |
| AD FS              | Federación con Active Directory                 |
