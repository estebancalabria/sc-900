# SC-900 - Fundamentos de Seguridad, Cumplimiento e Identidad

## Introducción

La seguridad y el cumplimiento son fundamentales para proteger los datos empresariales en entornos modernos donde la información puede encontrarse en infraestructura local, servicios cloud o soluciones basadas en Inteligencia Artificial.

Las organizaciones deben proteger sus datos independientemente de dónde se encuentren y cumplir con requisitos regulatorios relacionados con el almacenamiento, procesamiento y protección de la información.

Este módulo introduce los conceptos fundamentales que sustentan las soluciones de seguridad, cumplimiento e identidad de Microsoft:

* Modelo de Responsabilidad Compartida.
* Modelo de Responsabilidad Compartida para IA.
* Defense in Depth.
* Tríada CIA.
* Zero Trust.
* Encryption y Hashing.
* Governance, Risk and Compliance (GRC).

---

# Modelo de Responsabilidad Compartida

Define qué responsabilidades corresponden a la organización y cuáles al proveedor cloud.

## On-Premises

La organización administra:

* Infraestructura física.
* Hardware.
* Redes.
* Sistemas operativos.
* Aplicaciones.
* Datos.

## IaaS

El proveedor administra:

* Centro de datos.
* Infraestructura física.
* Hardware de red.

La organización administra:

* Sistemas operativos.
* Aplicaciones.
* Configuración de red.
* Datos.

## PaaS

El proveedor también administra:

* Sistemas operativos.
* Runtime.

La organización administra:

* Aplicaciones.
* Configuración.
* Accesos.
* Datos.

## SaaS

El proveedor administra:

* Aplicación completa.
* Infraestructura subyacente.

La organización administra:

* Usuarios y accesos.
* Configuración del tenant.
* Datos.

## Responsabilidades que Siempre Conserva la Organización

### Datos

* Clasificación.
* Protección.
* Cifrado.
* Gobernanza.

### Identidades y Accesos

* Usuarios.
* Autenticación.
* Permisos.

### Endpoints

* Computadoras.
* Tablets.
* Teléfonos.
* Dispositivos conectados.

### Configuración

* Servicios.
* Políticas.
* Permisos.
* Configuraciones de seguridad.

## Beneficios del Cloud

Los proveedores cloud invierten continuamente en:

* Seguridad física.
* Monitoreo.
* Certificaciones.
* Infraestructura.
* Operaciones de seguridad.

---

# Modelo de Responsabilidad Compartida para IA

La responsabilidad compartida también se aplica a soluciones de Inteligencia Artificial.

## Capas de una Solución de IA

### AI Platform

* Infraestructura.
* Modelos de IA.
* Controles de seguridad.
* Filtrado de contenido.

### AI Application

* Aplicaciones.
* Configuración.
* Conectores.
* Fuentes de datos.

### AI Usage

* Uso por parte de los usuarios.
* Políticas de uso.
* Supervisión organizacional.

## Responsabilidades del Proveedor

* Seguridad de la infraestructura.
* Seguridad de la plataforma.
* Operación del servicio.
* Controles de seguridad integrados.

## Responsabilidades de la Organización

* Protección de datos.
* Gestión de identidades.
* Configuración segura.
* Mitigación de Prompt Injection.
* Capacitación y políticas de uso.

---

# Defense in Depth

Defense in Depth utiliza múltiples capas de protección para evitar depender de un único mecanismo de seguridad.

Si una capa falla, las demás continúan protegiendo los recursos.

## Capas de Seguridad

### Physical Security

* Instalaciones seguras.
* Guardias.
* Cámaras.
* Control de acceso físico.

### Identity and Access

* MFA.
* RBAC.
* Conditional Access.

### Perimeter Security

* Firewalls.
* Protección DDoS.

### Network Security

* Segmentación.
* Network Security Groups (NSG).

### Compute Security

* Actualizaciones.
* Parches.
* Restricción de accesos administrativos.
* Monitoreo.

### Application Security

* Desarrollo seguro.
* Validación de entradas.
* Autenticación.
* Autorización.

### Data Security

La capa más importante.

Incluye:

* Controles de acceso.
* Cifrado.
* Clasificación de datos.

## Beneficios

* Retrasa atacantes.
* Incrementa la detección.
* Reduce el impacto de fallas.
* Mejora la resiliencia.

---

# Tríada CIA

La seguridad busca proteger tres objetivos fundamentales:

## Confidentiality

Garantiza que sólo usuarios autorizados puedan acceder a la información.

Mecanismos:

* Cifrado.
* Controles de acceso.
* Políticas de seguridad.

## Integrity

Garantiza que los datos permanezcan:

* Correctos.
* Completos.
* Sin modificaciones no autorizadas.

Mecanismos:

* Hashing.
* Firmas digitales.
* Auditorías.
* Controles transaccionales.

## Availability

Garantiza que los sistemas y datos estén disponibles cuando se necesiten.

Mecanismos:

* Infraestructura redundante.
* Balanceo de carga.
* Failover.
* Backups.
* Protección DDoS.

## Balance de la CIA Triad

Las organizaciones deben equilibrar confidencialidad, integridad y disponibilidad según sus necesidades y riesgos.

---

# Zero Trust

Zero Trust es una estrategia de seguridad basada en:

> Never Trust, Always Verify

Ningún usuario, dispositivo, aplicación o red debe considerarse confiable por defecto.

Cada solicitud debe ser autenticada y autorizada.

## Principios Fundamentales

### Verify Explicitly

Evaluar múltiples señales:

* Identidad.
* Ubicación.
* Estado del dispositivo.
* Aplicación.
* Datos.
* Riesgo.

### Use Least Privileged Access

Otorgar únicamente los permisos mínimos necesarios.

#### Just-In-Time (JIT)

Acceso sólo cuando se necesita.

#### Just-Enough-Access (JEA)

Sólo los permisos estrictamente necesarios.

### Assume Breach

Asumir que una brecha puede ocurrir.

Implementar:

* Segmentación.
* Cifrado.
* Monitoreo.
* Detección y respuesta.

---

# Los Siete Pilares de Zero Trust

## 1. Identities

* Usuarios.
* Servicios.
* Dispositivos.
* Autenticación fuerte.

## 2. Devices

* Estado de salud.
* Cumplimiento.
* Detección de compromiso.

## 3. Applications

* Aplicaciones autorizadas.
* Shadow IT.
* Permisos.

## 4. Data

* Clasificación.
* Etiquetado.
* Cifrado.

## 5. Infrastructure

* Configuración.
* Actualizaciones.
* Telemetría.
* Acceso JIT.

## 6. Networks

* Segmentación.
* Microsegmentación.
* Monitoreo.
* Protección de red.

## 7. Visibility, Automation and Orchestration

Integra señales provenientes de todos los pilares.

Incluye:

* Correlación de eventos.
* Detección de amenazas.
* Automatización.
* SIEM.
* SOAR.

---

# Encryption

La encriptación convierte datos legibles en información ilegible para usuarios no autorizados.

Para acceder a la información se requiere una clave de descifrado.

## Symmetric Encryption

Utiliza una única clave para:

* Cifrar.
* Descifrar.

Ventaja:

* Mayor velocidad.

Desventaja:

* Distribución segura de la clave.

## Asymmetric Encryption

Utiliza:

* Public Key.
* Private Key.

Características:

* Lo cifrado con la clave pública sólo puede descifrarse con la privada.
* Lo firmado con la privada puede verificarse con la pública.

Aplicaciones:

* HTTPS.
* Email seguro.
* Protocolos criptográficos.

---

# Digital Signatures

Permiten verificar:

## Authenticity

Confirman quién envió la información.

## Integrity

Confirman que no fue modificada.

Usos:

* Software.
* Documentos.
* Correos.
* Transacciones.

---

# Encryption Según el Estado de los Datos

## Data at Rest

Datos almacenados.

Ejemplos:

* Discos.
* Bases de datos.
* Cloud Storage.

## Data in Transit

Datos en movimiento.

Protección mediante:

* HTTPS.
* TLS.
* VPN.

## Data in Use

Datos procesándose activamente.

Protección mediante:

* Confidential Computing.
* Secure Enclaves.

---

# Key Management

La seguridad del cifrado depende de la protección de las claves.

Incluye:

* Generación.
* Almacenamiento.
* Protección.
* Rotación.
* Retiro.

## Buenas Prácticas

* Separar claves y datos.
* Utilizar HSM.
* Rotar claves.
* Restringir accesos.

### Azure Key Vault

Permite administrar:

* Claves.
* Certificados.
* Secretos.

---

# Hashing

Hashing genera una huella digital única (hash o digest) de longitud fija.

Características:

* No utiliza claves.
* No puede revertirse.
* El mismo dato produce siempre el mismo resultado.

## Hashing para Contraseñas

Se almacena el hash de la contraseña, no la contraseña original.

Durante el inicio de sesión se compara el hash generado con el hash almacenado.

---

# Salting

Consiste en agregar un valor aleatorio único a cada contraseña antes de generar el hash.

Beneficios:

* Contraseñas iguales generan hashes distintos.
* Reduce la efectividad de Rainbow Tables.
* Incrementa la seguridad del almacenamiento de credenciales.

---

# Governance, Risk and Compliance (GRC)

GRC es el conjunto de prácticas que permiten gestionar de forma estructurada:

* Gobernanza.
* Riesgo.
* Cumplimiento.

Su objetivo es ayudar a las organizaciones a:

* Definir responsabilidades.
* Identificar amenazas.
* Cumplir regulaciones.
* Generar confianza.

---

# Governance

Governance es el conjunto de reglas, procesos y prácticas utilizadas para dirigir y controlar una organización.

Incluye:

* Clasificación y manejo de datos.
* Gestión de identidades y accesos.
* Procesos de aprobación para accesos privilegiados.
* Asignación de responsabilidades.
* Definición de la estrategia de seguridad.

Governance proporciona la estructura sobre la cual funcionan Risk y Compliance.

---

# Risk

Risk Management es el proceso de identificar, evaluar y responder a amenazas que pueden afectar a la organización.

## Fuentes de Riesgo

### Externas

* Ciberataques.
* Desastres naturales.
* Cambios regulatorios.
* Proveedores externos.

### Internas

* Exposición accidental de datos.
* Insider Threats.
* Fraude.
* Fallas en procesos.

## Proceso de Gestión de Riesgos

### Identify

Identificar riesgos potenciales.

### Assess

Evaluar impacto y probabilidad.

### Respond

Las opciones incluyen:

* Accept.
* Mitigate.
* Transfer.
* Avoid.

### Monitor

Supervisar continuamente los riesgos y controles.

---

# Compliance

Compliance es el cumplimiento de leyes, regulaciones, estándares y políticas aplicables a una organización.

## Ejemplos

### HIPAA

Protección de información médica.

### ISO 27001

Estándar internacional de gestión de seguridad de la información.

### SOC 2

Auditoría para proveedores de servicios que procesan datos.

## Compliance ≠ Security

Compliance establece requisitos mínimos obligatorios.

Security es un concepto más amplio que busca proteger datos y sistemas frente a amenazas.

Una organización puede cumplir regulaciones y aun así presentar vulnerabilidades de seguridad.

---

# Conceptos Relacionados con Compliance

## Data Residency

Define dónde pueden almacenarse físicamente los datos y cómo pueden transferirse entre ubicaciones.

## Data Sovereignty

Los datos quedan sujetos a las leyes del país o región donde son recopilados, almacenados o procesados.

## Data Privacy

Se refiere al tratamiento adecuado de datos personales.

Incluye:

* Transparencia sobre el uso de datos.
* Consentimiento.
* Derechos de acceso.
* Corrección.
* Eliminación.
* Protección frente a accesos no autorizados.

---

# Ideas Clave del Módulo

* La seguridad cloud se basa en el modelo de responsabilidad compartida.
* Los datos, identidades, endpoints y configuraciones siempre siguen siendo responsabilidad de la organización.
* El modelo de responsabilidad compartida también se aplica a la IA.
* Defense in Depth utiliza múltiples capas de protección.
* La CIA Triad define los objetivos fundamentales de la seguridad.
* Zero Trust elimina la confianza implícita y exige verificación continua.
* Los siete pilares de Zero Trust protegen identidades, dispositivos, aplicaciones, datos, infraestructura y redes.
* Encryption protege los datos en reposo, tránsito y uso.
* Hashing permite verificar información sin almacenar el valor original.
* Salting mejora la protección de contraseñas.
* Governance establece reglas y responsabilidades.
* Risk permite identificar y gestionar amenazas.
* Compliance ayuda a cumplir leyes y regulaciones.
* Data Residency, Data Sovereignty y Data Privacy son conceptos fundamentales dentro del cumplimiento normativo.
