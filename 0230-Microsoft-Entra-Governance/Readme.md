# SC-900 – Microsoft Entra: Identity Governance, Identity Protection, Verified ID y Security Copilot

## Introducción

La gobernanza de identidades (**Identity Governance**) busca equilibrar la seguridad con la productividad de los usuarios, garantizando que los accesos sean apropiados, auditables y cumplan requisitos regulatorios.

La protección de identidades (**Identity Protection**) se centra en detectar, investigar y remediar riesgos relacionados con identidades digitales, credenciales comprometidas y accesos sospechosos.

Microsoft Entra combina capacidades de gobernanza, protección y verificación de identidades para proteger recursos críticos, reducir riesgos y mantener la productividad de empleados, socios, proveedores y agentes de inteligencia artificial.

---

# Microsoft Entra ID Governance

Microsoft Entra ID Governance es una solución de gobernanza de identidades que ayuda a las organizaciones a mejorar la productividad, fortalecer la seguridad y cumplir requisitos regulatorios mediante automatización, delegación y visibilidad sobre accesos.

## Preguntas que responde

* ¿Qué identidades deberían tener acceso a qué recursos?
* ¿Qué hacen los usuarios con esos accesos?
* ¿Existen controles para administrar esos accesos?
* ¿Pueden los auditores verificar que los controles funcionan correctamente?

## Escenarios principales

* Gobernanza del ciclo de vida de identidades.
* Gobernanza del ciclo de vida de accesos.
* Protección de accesos privilegiados.

---

# Gobernanza del ciclo de vida de identidades (Identity Lifecycle)

Microsoft Entra ID Governance utiliza el modelo **Join, Move, Leave**.

## Join (Ingreso)

Cuando una persona se incorpora a la organización:

* Se crea su identidad digital.
* Se asignan permisos iniciales.
* Se habilitan recursos necesarios para comenzar a trabajar.

## Move (Cambio de rol)

Cuando cambia de puesto o departamento:

* Se agregan permisos necesarios.
* Se eliminan permisos obsoletos.
* Se actualizan grupos y roles.

## Leave (Salida)

Cuando abandona la organización:

* Se revocan accesos.
* Se deshabilitan cuentas.
* La información puede conservarse para auditoría.

## Automatización del ciclo de vida

### Inbound Provisioning

Sincroniza usuarios desde sistemas de RRHH como:

* Workday.
* SAP SuccessFactors.

Manteniendo actualizadas las identidades en:

* Microsoft Entra ID.
* Active Directory.

### Lifecycle Workflows

Automatiza tareas relacionadas con:

* Incorporación de empleados.
* Cambios de puesto.
* Desvinculación.

### User Provisioning

Automatiza la creación, actualización y eliminación de cuentas en aplicaciones cloud y locales.

---

# Gobernanza del ciclo de vida de accesos (Access Lifecycle)

Permite administrar permisos durante toda la permanencia del usuario en la organización.

## Dynamic Groups

Permiten crear grupos basados en atributos como:

* Departamento.
* Cargo.
* Ubicación.
* Tipo de empleado.

Cuando cambian los atributos del usuario, la membresía se actualiza automáticamente.

---

# Entitlement Management

Entitlement Management es una funcionalidad de Identity Governance que permite administrar el ciclo de vida de accesos a gran escala.

Automatiza:

* Solicitudes de acceso.
* Flujos de aprobación.
* Asignaciones.
* Revisiones.
* Expiración de accesos.

## Problemas que resuelve

* Los usuarios no saben qué acceso solicitar.
* Es difícil encontrar al aprobador correcto.
* Los permisos permanecen activos más tiempo del necesario.
* La administración de usuarios externos es compleja.

## Access Packages

Un **Access Package** es un conjunto de recursos necesarios para que un usuario realice una tarea o participe en un proyecto.

Puede incluir:

* Security Groups.
* Microsoft 365 Groups.
* Aplicaciones empresariales.
* Sitios de SharePoint Online.

## Capacidades principales

### Delegación

Permite delegar la creación y administración de Access Packages a usuarios no administradores.

### Políticas de acceso

Permiten definir:

* Quién puede solicitar acceso.
* Quién debe aprobarlo.
* Cuándo expira.

### Gestión de usuarios externos

Cuando un usuario externo solicita acceso:

* Puede ser invitado automáticamente mediante B2B.
* Se le asignan recursos automáticamente tras la aprobación.
* Su cuenta puede eliminarse automáticamente cuando expire el acceso.

### Gestión de agentes de IA

Permite gobernar accesos de identidades de agentes de inteligencia artificial utilizando los mismos principios aplicados a usuarios humanos.

---

# Microsoft Entra Terms of Use

Permite presentar términos legales o de cumplimiento antes de acceder a aplicaciones o recursos corporativos.

## Casos de uso

* Acceso a información sensible.
* Recordatorios regulatorios periódicos.
* Términos específicos para determinados roles.
* Políticas corporativas generales.

## Características

* Basados en archivos PDF.
* Compatibles con dispositivos móviles.
* Integrados con Conditional Access.

## Conditional Access + Terms of Use

Puede exigirse que el usuario:

1. Visualice los términos.
2. Los acepte.
3. Obtenga acceso al recurso.

Los administradores pueden verificar quién aceptó o rechazó los términos.

---

# Access Reviews

Microsoft Entra Access Reviews permite revisar periódicamente:

* Membresías de grupos.
* Accesos a aplicaciones empresariales.
* Asignaciones de roles.

Su objetivo es garantizar que únicamente las personas adecuadas mantengan acceso a los recursos.

## Casos de uso

### Revisar roles privilegiados

Permite verificar:

* Administradores activos.
* Usuarios con privilegios elevados.
* Invitados o socios externos que ya no necesitan acceso.

### Revisar acceso a información crítica

Permite exigir que los usuarios justifiquen periódicamente la necesidad de mantener acceso.

### Revisar excepciones de políticas

Facilita demostrar a los auditores que las excepciones son revisadas regularmente.

### Validar acceso de invitados

Los propietarios de grupos pueden confirmar que usuarios externos continúan necesitando acceso.

### Revisiones recurrentes

Pueden configurarse:

* Semanalmente.
* Mensualmente.
* Trimestralmente.
* Anualmente.

## Gestión de usuarios e invitados

Las revisiones pueden ser realizadas por:

* Los propios usuarios.
* Propietarios de grupos.
* Responsables de negocio.
* Administradores.

Los cambios pueden aplicarse:

* Manualmente.
* Automáticamente (Auto Apply).

## Multi-Stage Access Reviews

Permiten hasta tres etapas de revisión.

Beneficios:

* Participación de múltiples revisores.
* Mayor cumplimiento regulatorio.
* Mejor trazabilidad.

## Recomendaciones impulsadas por IA

Analizan:

* Actividad de inicio de sesión.
* Relación con grupos.
* Patrones de uso.
* Contexto organizacional.

También identifican **Peer Outliers**, usuarios cuyos patrones de acceso difieren significativamente de sus compañeros.

---

# Privileged Identity Management (PIM)

Privileged Identity Management (PIM) es un servicio de Microsoft Entra ID que permite administrar, controlar y supervisar el acceso a recursos críticos.

Puede utilizarse con:

* Microsoft Entra ID.
* Azure.
* Microsoft 365.
* Microsoft Intune.
* Otros servicios Microsoft.

Su objetivo es reducir riesgos asociados con privilegios excesivos, innecesarios o mal utilizados.

## Características principales

### Just-In-Time (JIT)

Los privilegios se otorgan únicamente cuando son necesarios.

### Time-Bound

Los accesos privilegiados tienen fecha de inicio y finalización.

### Approval-Based

La activación de privilegios puede requerir aprobación previa.

### MFA Obligatorio

Puede exigir autenticación multifactor antes de activar un rol.

### Justificación

Los usuarios deben indicar el motivo por el que solicitan privilegios.

### Visible

Genera notificaciones cuando se activan roles privilegiados.

### Auditable

Mantiene historial completo de asignaciones y activaciones.

## Recursos compatibles con PIM

### Microsoft Entra Roles

* Roles integrados.
* Roles personalizados.
* Roles administrativos de Microsoft 365.

### Azure Roles

Roles RBAC aplicados a:

* Management Groups.
* Suscripciones.
* Resource Groups.
* Recursos individuales.

### PIM for Groups

Permite:

* Membresía Just-In-Time.
* Propiedad Just-In-Time.

Aplicable a:

* Roles de Microsoft Entra.
* Roles de Azure.
* Azure SQL.
* Azure Key Vault.
* Intune.
* Aplicaciones Microsoft y de terceros.

## Flujo de trabajo de PIM

### 1. Assign

El administrador asigna roles a:

* Usuarios.
* Grupos.
* Service Principals.
* Managed Identities.

Tipos de asignación:

#### Eligible Assignment

El usuario debe activar el rol antes de utilizarlo.

#### Active Assignment

Los privilegios están disponibles inmediatamente.

### 2. Activate

El usuario:

* Solicita activación.
* Selecciona duración.
* Proporciona justificación.
* Puede requerir MFA.

### 3. Approve or Deny

Los aprobadores reciben notificaciones y pueden:

* Aprobar.
* Rechazar.

### 4. Extend and Renew

Permite:

* Extender asignaciones activas.
* Renovar asignaciones expiradas.

## Auditoría

PIM mantiene historial de:

* Asignaciones.
* Activaciones.
* Solicitudes.
* Aprobaciones.

Facilitando auditorías y cumplimiento normativo.

---

# Gobernanza de identidades para agentes de IA

Microsoft Entra permite administrar identidades de agentes de inteligencia artificial de forma similar a las identidades humanas.

Permite:

* Gestionar permisos.
* Controlar el ciclo de vida.
* Auditar actividades.
* Aplicar el principio de mínimo privilegio.

---

# Microsoft Entra ID Protection

Microsoft Entra ID Protection ayuda a detectar, investigar y remediar riesgos basados en identidades.

Protege:

* Identidades de usuarios.
* Workload Identities.

Los riesgos detectados pueden utilizarse posteriormente en:

* Conditional Access.
* Microsoft Defender XDR.
* Herramientas SIEM.
* Plataformas de monitoreo y correlación.

Identity Protection forma parte fundamental de una estrategia Zero Trust.

## Detección de riesgos

Microsoft analiza billones de señales diariamente provenientes de:

* Microsoft Entra ID.
* Microsoft Accounts.
* Xbox.
* Otros servicios Microsoft.

Estas señales permiten detectar amenazas como:

* Anonymous IP Addresses.
* Password Spray Attacks.
* Leaked Credentials.
* Actividades sospechosas.
* Posibles compromisos de cuentas.

Durante cada autenticación, Identity Protection ejecuta detecciones en tiempo real y genera un nivel de riesgo para la sesión.

## Sign-in Risk

Representa la probabilidad de que una autenticación no haya sido realizada por el propietario legítimo de la cuenta.

Ejemplos:

* Inicio de sesión desde IP anónima.
* Atypical Travel.
* Propiedades de inicio de sesión desconocidas.

## User Risk

Representa la probabilidad de que una cuenta haya sido comprometida.

Ejemplos:

* Credenciales filtradas.
* Actividad sospechosa reportada por el usuario.
* Evidencia de compromiso.

> Identity Protection solo genera detecciones cuando se utilizan credenciales válidas.

## Reportes

### Risk Detections

Lista de detecciones individuales.

### Risky Sign-ins

Inicios de sesión con riesgos detectados.

### Risky Users

Usuarios con riesgos asociados.

## Remediación

Las políticas de Risk-Based Conditional Access pueden requerir:

* MFA.
* Métodos fuertes de autenticación.
* Secure Password Reset.

Si el usuario completa satisfactoriamente el control solicitado, el riesgo puede remediarse automáticamente.

### Remediación manual

Los administradores pueden:

* Dismiss.
* Confirm Safe.
* Confirm Compromised.

Desde:

* Portal de Microsoft Entra.
* APIs.
* Microsoft Defender XDR.

## Exportación e integración

Los datos pueden exportarse mediante:

* Microsoft Graph API.
* SIEM.
* Log Analytics Workspace.
* Azure Storage.
* Event Hubs.
* Microsoft Defender XDR.

---

# Microsoft Entra Verified ID

Microsoft Entra Verified ID es un servicio administrado de **credenciales verificables (Verifiable Credentials)** basado en estándares abiertos.

Permite automatizar la verificación de identidades y facilitar interacciones seguras respetando la privacidad del usuario.

## ¿Por qué es necesario?

Las organizaciones necesitan verificar información digital de forma:

* Criptográficamente segura.
* Compatible con requisitos de privacidad.
* Legible por máquinas.
* Fácil de verificar.

Las credenciales verificables permiten demostrar información sin perder el control sobre los datos compartidos.

## Beneficios

* Mayor confianza digital.
* Protección de privacidad.
* Menor dependencia de documentos físicos.
* Control del usuario sobre sus datos.
* Prevención de fraude de identidad.

## Basado en estándares abiertos

Microsoft participa activamente en iniciativas como:

* W3C.
* Decentralized Identity Foundation (DIF).

---

# Funcionamiento de Verified ID

Participan tres actores principales.

## Issuer

Organización que emite la credencial.

Ejemplos:

* Gobiernos.
* Universidades.
* Empleadores.
* Proveedores de identidad.

## User

El usuario:

* Recibe la credencial.
* La almacena en una billetera digital.
* Decide cuándo compartirla.

Las credenciales están firmadas criptográficamente.

## Verifier

Organización que solicita verificar la credencial.

Ejemplos:

* Empresas.
* Aerolíneas.
* Bancos.
* Entidades financieras.

## Verifiable Data Registry

Infraestructura que almacena metadatos y claves públicas necesarias para verificar credenciales.

Representa el sistema de confianza subyacente.

---

# DID Web Trust System

Verified ID utiliza **did:web**.

El identificador descentralizado (DID) está asociado a un dominio web controlado por la organización emisora.

La confianza se basa en la reputación y propiedad de dicho dominio.

---

# Expiración y revocación

Las credenciales verificables pueden:

* Expirar.
* Ser revocadas por el emisor.

Los estándares de Verifiable Credentials contemplan ambos escenarios.

---

# Account Recovery con Verified ID

Verified ID desempeña un papel importante en la recuperación de cuentas.

Permite recuperar acceso incluso cuando el usuario perdió todos sus métodos de autenticación.

## Flujo general

1. Verificación de identidad mediante un proveedor confiable.
2. Validación de documentos oficiales.
3. Emisión de una credencial verificable.
4. Verificación biométrica mediante Face Check.
5. Emisión de un Temporary Access Pass (TAP).
6. Registro de nuevos métodos de autenticación.

## Face Check

Utiliza Azure AI para comparar:

* Selfie en tiempo real.
* Fotografía del documento oficial.

Solo se comparte el resultado de la coincidencia, preservando la privacidad del usuario.

---

# IA y Credenciales Verificables

A medida que aumentan:

* Los deepfakes.
* La suplantación de identidad.
* El contenido generado por IA.

Las credenciales verificables ayudan a demostrar que una interacción involucra a una persona real y validada.

Esto reduce riesgos asociados con fraude e impersonación impulsados por IA.

---

# Microsoft Security Copilot y Microsoft Entra

## ¿Qué es Microsoft Security Copilot?

Microsoft Security Copilot es una solución de seguridad impulsada por IA generativa que combina:

* Inteligencia artificial.
* Machine Learning.
* Datos de seguridad en tiempo real.
* Conocimiento humano.

Su objetivo es ayudar a los equipos de seguridad a detectar amenazas, investigar incidentes y responder más rápidamente.

Microsoft Entra es uno de los plugins principales utilizados por Security Copilot para proporcionar información sobre identidades y accesos.

## Capacidades de integración

Security Copilot puede:

* Investigar riesgos de identidad.
* Analizar accesos y permisos.
* Detectar actividad sospechosa.
* Evaluar configuraciones de seguridad.
* Generar recomendaciones.
* Automatizar tareas administrativas.

Obtiene información de:

* Usuarios.
* Grupos.
* Sign-in Logs.
* Audit Logs.
* Provisioning Logs.
* Conditional Access.
* Métodos de autenticación.
* Roles.
* Dispositivos.

---

# Experiencias disponibles

## Standalone Experience

Disponible en el portal de Security Copilot.

Permite realizar investigaciones utilizando lenguaje natural.

Ejemplos:

* Consultar información de usuarios.
* Obtener Object IDs.
* Analizar Risky Sign-ins.
* Consultar Sign-in Logs.
* Consultar Audit Logs.

## Embedded Experience

Integrada directamente en Microsoft Entra Admin Center.

Por ejemplo, dentro de Identity Protection puede:

* Resumir el nivel de riesgo de un usuario.
* Explicar incidentes detectados.
* Recomendar acciones de remediación.
* Priorizar actividades de respuesta.

---

# Escenarios soportados por Security Copilot

## Microsoft Entra ID

Permite:

* Consultar usuarios.
* Consultar grupos.
* Consultar dominios.
* Consultar licencias.
* Investigar Sign-in Logs.
* Investigar Audit Logs.
* Revisar Conditional Access.
* Analizar métodos de autenticación.
* Consultar asignaciones de roles.
* Revisar alertas y recomendaciones.

## Microsoft Entra ID Protection

Permite:

* Analizar usuarios riesgosos.
* Investigar detecciones de riesgo.
* Obtener recomendaciones de remediación.
* Evaluar riesgos de aplicaciones.
* Analizar Workload Identities.

## Microsoft Entra ID Governance

Permite:

* Analizar Access Reviews.
* Administrar Access Packages.
* Monitorear PIM.
* Diagnosticar Lifecycle Workflows.

## Microsoft Entra Internet Access y Private Access

Permite:

* Analizar Global Secure Access Logs.
* Revisar tráfico de red.
* Comprender cómo los usuarios acceden a los recursos.

---

# Microsoft Entra Agents

Microsoft Entra Agents son herramientas impulsadas por IA que automatizan tareas repetitivas relacionadas con identidades y accesos.

Beneficios:

* Reducen trabajo manual.
* Aplican mejores prácticas.
* Mejoran la postura de seguridad.
* Automatizan acciones correctivas.

## Agent Identity

Cada agente posee una identidad propia.

Esta identidad:

* Se crea automáticamente al habilitar el agente.
* Tiene permisos específicos.
* Puede leer información.
* Puede ejecutar acciones autorizadas.

Los agentes se administran desde Microsoft Entra Admin Center.

---

# Agentes disponibles

## Conditional Access Optimization Agent

Analiza políticas de Conditional Access y compara la configuración con:

* Buenas prácticas de Microsoft.
* Principios Zero Trust.

Detecta:

* Usuarios sin protección.
* Aplicaciones sin protección.
* Agent Identities sin protección.
* Configuraciones incorrectas.

Se ejecuta cada 24 horas o bajo demanda.

## Identity Risk Management Agent (Preview)

Ayuda a investigar riesgos detectados por Microsoft Entra ID Protection.

Funciones:

* Analizar riesgos.
* Explicar impacto potencial.
* Recomendar acciones.
* Monitorear continuamente.

---

# Security Store

Security Store es un catálogo centralizado integrado en Microsoft Entra que permite:

* Descubrir agentes.
* Comprar soluciones.
* Implementar agentes.
* Gestionar extensiones de seguridad.

Incluye agentes desarrollados por Microsoft y por socios tecnológicos.

---

# Consideraciones sobre IA

Security Copilot utiliza IA generativa y Machine Learning.

Como toda solución basada en IA:

* Puede generar respuestas incorrectas.
* Requiere validación humana.
* Debe utilizarse como herramienta de apoyo para la toma de decisiones.

Microsoft permite enviar retroalimentación mediante:

* 👍 Thumbs Up
* 👎 Thumbs Down

---

# Conceptos clave para el examen SC-900

## Identity Governance

* Join, Move, Leave.
* Inbound Provisioning.
* Lifecycle Workflows.
* Dynamic Groups.
* Entitlement Management.
* Access Packages.
* Terms of Use.

## Access Governance

* Access Reviews.
* Multi-Stage Reviews.
* Peer Outliers.
* Auto Apply.

## Privileged Access

* PIM.
* Just-In-Time (JIT).
* Eligible Assignment.
* Active Assignment.
* PIM for Groups.

## Identity Protection

* Sign-in Risk.
* User Risk.
* Risk Detections.
* Risky Sign-ins.
* Risky Users.
* Anonymous IP.
* Atypical Travel.
* Password Spray Attack.
* Risk-Based Conditional Access.
* Workload Identities.

## Verified ID

* Verifiable Credentials.
* Issuer.
* User.
* Verifier.
* Verifiable Data Registry.
* DID.
* did:web.
* Face Check.
* Temporary Access Pass (TAP).
* Decentralized Identity.

## Security Copilot

* Microsoft Entra Plugin.
* Standalone Experience.
* Embedded Experience.
* Microsoft Entra Agents.
* Agent Identity.
* Conditional Access Optimization Agent.
* Identity Risk Management Agent.
* Security Store.

# Resumen Final

Microsoft Entra proporciona una plataforma integral para gobernar, proteger y verificar identidades. Identity Governance controla quién accede a qué recursos y durante cuánto tiempo; Entitlement Management y Access Reviews administran y certifican accesos; PIM protege privilegios administrativos mediante acceso Just-In-Time; Identity Protection detecta y remedia riesgos basados en identidad; Verified ID permite emitir y verificar credenciales digitales seguras; y Security Copilot incorpora IA generativa para investigar incidentes, automatizar tareas y fortalecer la postura de seguridad. En conjunto, estas capacidades permiten implementar una estrategia Zero Trust moderna centrada en la identidad, el acceso mínimo necesario y la automatización inteligente.
