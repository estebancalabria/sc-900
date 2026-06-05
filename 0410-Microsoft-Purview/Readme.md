### 🧾 Resumen Completo – Microsoft Purview (End-to-End: Seguridad, Cumplimiento, Riesgo, DSPM e Investigaciones)

Microsoft Purview es una plataforma integral que permite **clasificar, proteger, prevenir fugas, gestionar riesgos internos, adaptar controles de seguridad y realizar investigaciones avanzadas de incidentes de datos**, en entornos Microsoft 365, multi-cloud, on-premises y aplicaciones de IA.

---

# 🔐 1. Data Classification en Microsoft Purview

Permite identificar información sensible para aplicar controles de seguridad.

## 🧩 Sensitive Information Types (SITs)

Detectan datos sensibles mediante patrones.

**Ejemplos:**

* Tarjetas de crédito
* Pasaportes
* Cuentas bancarias
* Información médica

### Componentes:

* Primary element (regex, keywords, funciones)
* Supporting elements (evidencia contextual)
* Confidence level (bajo, medio, alto)
* Proximity (distancia entre coincidencias)

### Tipos:

* Built-in SITs
* Named entity SITs
* Custom SITs
* Exact Data Match (EDM)

---

## 🤖 Trainable Classifiers

Clasificación basada en IA/ML según contenido.

* Pre-trained
* Custom (entrenados con ejemplos)

⚠️ No funcionan con contenido cifrado.

---

## 🤖 Clasificación + IA

* Detecta datos sensibles en Microsoft 365 Copilot
* Aplica SITs en prompts y respuestas
* DSPM y Activity Explorer permiten visibilidad de IA
* Copilot respeta etiquetas y permisos

---

## 🔎 Exploración de datos

* 📁 Content Explorer: datos clasificados y ubicación
* 📊 Activity Explorer: actividad, cambios de etiquetas, DLP endpoint

---

# 🏷️ 2. Sensitivity Labels

Etiquetas persistentes que clasifican y protegen datos.

## Características:

* Customizables
* Persisten en metadata
* Solo una etiqueta por elemento
* Viajan con el contenido

## Capacidades:

* Cifrado
* Watermarks, headers, footers
* Auto-labeling
* Protección de contenedores (Teams, SharePoint, Groups)
* Integración con terceros
* Clasificación sin protección

## Scopes:

* Files, Emails, Meetings, Groups & Sites

## 🤖 Con Copilot:

* Hereda la etiqueta más restrictiva
* Respeta cifrado y permisos

## ⚙️ Label Policies:

* Publicación a usuarios/grupos
* Default label
* Justificación de cambios
* Mandatory labeling
* Help contextual

---

# 🚫 3. Data Loss Prevention (DLP)

Previene la fuga de datos sensibles detectando y bloqueando acciones riesgosas.

## 🌐 Cobertura:

* Microsoft 365 (Teams, Exchange, SharePoint, OneDrive)
* Office apps
* Endpoints Windows/macOS
* Cloud apps
* On-premises
* Fabric / Power BI
* Microsoft Edge

## 🔍 Detección:

* Pattern matching
* Regex + keywords
* ML y validación contextual

---

## 🛡️ Acciones:

* Policy tips
* Bloqueo (con o sin override)
* Cuarentena
* Ocultamiento en Teams

## 📊 Visibilidad:

* Audit logs
* Activity Explorer
* Microsoft Defender incidents

---

## 💻 Endpoint DLP:

* USB / network copy
* Printing
* File creation/rename
* Apps no autorizadas
* Navegación no controlada

---

## 💬 DLP en Teams:

* Protección de chats y archivos
* Explicaciones al usuario

---

## 🤖 DLP + IA:

* Bloquea o advierte sobre uso de datos sensibles en IA
* Control de copy/paste en prompts

---

## 🤖 DLP + Security Copilot:

* Alert summarization
* Triage Agent (priorización automática de alertas)

---

# 🚨 4. Insider Risk Management

Solución para detectar, investigar y actuar sobre riesgos internos.

## ⚠️ Riesgos:

* Data leaks
* IP theft
* Fraude
* Insider trading
* Violaciones regulatorias

## 🧭 Principios:

* Transparencia
* Configurable
* Integrado
* Accionable

---

## 🔄 Workflow:

1. Policies
2. Alerts
3. Triage
4. Investigate:

   * User activity
   * Content Explorer
   * Case notes
   * Data risk graph
5. Action:

   * Notificaciones
   * eDiscovery
   * Exportación

---

## 🤖 Insider Risk + IA:

* Detecta uso indebido de IA
* Prompt injection
* Exfiltración a IA externas
* Integración con Defender XDR

---

## 🤖 Insider Risk + Security Copilot:

* Alert summarization
* Triage Agent (reduce ruido y prioriza riesgo)

---

# ⚙️ 5. Adaptive Protection

Aplica controles dinámicos según el nivel de riesgo del usuario usando ML.

## 🔗 Integraciones:

* DLP
* Data Lifecycle Management
* Microsoft Entra Conditional Access

## ⚠️ Niveles de riesgo:

* 🟢 Minor: tips educativos
* 🟠 Moderate: advertencias + justificación
* 🔴 Elevated: bloqueos estrictos

👉 Los niveles cambian dinámicamente sin intervención manual.

## 🧠 Principios:

* Context-aware detection
* Dynamic controls
* Automated mitigation

---

## 🚫 Ejemplos:

* DLP ajusta bloqueos según riesgo
* Retención automática de datos en usuarios de alto riesgo (120 días)
* Conditional Access restringe o bloquea acceso según riesgo

---

# 📊 6. Data Security Posture Management (DSPM)

DSPM ofrece una **vista unificada del estado de seguridad de los datos en toda la organización**.

## 🎯 Enfoque

Se centra en el **dato**, no en el endpoint.

## ❓ Responde:

* ¿Qué datos tenemos?
* ¿Dónde están?
* ¿Quién accede?
* ¿Cómo están protegidos?

---

## 🔗 Integración:

* DLP
* Sensitivity Labels
* Insider Risk Management
* Data Security Investigations

---

## ⚙️ Acciones:

* Remover links públicos
* Aplicar DLP
* Corregir oversharing
* Iniciar investigaciones

---

## 🎯 Data Security Objectives:

* Evitar exposición en Copilot
* Evitar oversharing
* Prevenir exfiltración
* Descubrir datos sensibles

Incluye:

* Métricas
* One-click policies
* Flujos guiados

---

## 🌐 Cobertura:

* Microsoft 365
* Azure
* Fabric
* SaaS (Google Cloud, Snowflake, Databricks)
* Integraciones (Cyera, BigID, OneTrust)

---

## 🤖 AI Observability:

* Copilot y apps de IA
* Oversharing
* Exfiltración
* Accesos anómalos

---

## 📁 Asset Explorer:

* Shadow data
* Datos sin etiquetar
* Riesgos por ubicación

---

## 📊 Reporting:

* Posture dashboard
* Objetivos
* AI risks
* DLP usage
* Trends

---

## 🤖 DSPM + IA:

* Detecta riesgos en AI agents
* Sugerencias de remediación
* One-click policies
* Automatización con control humano

---

# 🔬 7. Microsoft Purview Data Security Investigations

Solución para **investigar incidentes de seguridad de datos con IA generativa**.

## 🧠 Qué es

Permite investigar:

* Brechas de datos
* Insider leaks
* Exposición inesperada de información

Usa **IA generativa para acelerar análisis de grandes volúmenes de datos**.

---

## 🤖 Capacidades de IA

* 🔎 Vector search: búsqueda semántica (no solo keywords)
* 🗂️ Categorization: agrupa datos por tipo y nivel de riesgo
* 🧪 Examination: detecta riesgos como credenciales expuestas o vulnerabilidades

---

## ⚠️ Casos de uso

* Data breach: identificar qué datos fueron expuestos
* Insider leak: analizar usuarios que compartieron datos
* Proactive assessment: detectar riesgos antes de incidentes

---

## 🔗 Integraciones

* Insider Risk Management → casos a investigación profunda
* Microsoft Defender XDR → análisis desde alertas
* DSPM → análisis de exfiltración detectada
* Unified Audit Log → trazabilidad completa

---

## 🛡️ Acciones

* Soft purge (recuperable)
* Hard purge (eliminación definitiva)
* Ajuste de accesos
* Aplicación de cifrado
* Cumplimiento regulatorio

---

## 💰 Modelo de consumo

* Pay-as-you-go
* Basado en almacenamiento y procesamiento
* No requiere licencia por usuario

---

# 🎯 IDEA FINAL (PURVIEW COMPLETO)

Microsoft Purview unifica todo el ciclo de seguridad de datos:

* 🔍 Clasificación (SITs + ML)
* 🏷️ Etiquetado (Sensitivity Labels)
* 🚫 Prevención (DLP)
* 🚨 Riesgo interno (Insider Risk)
* ⚙️ Adaptación dinámica (Adaptive Protection)
* 📊 Postura de seguridad (DSPM)
* 🔬 Investigación avanzada (Data Security Investigations)
* 🤖 Automatización con IA (Copilot + Security Copilot)

---

## 🧠 CONCEPTO FINAL

👉 Purview evoluciona de seguridad reactiva a un modelo:

**“Detectar → Clasificar → Proteger → Prevenir → Adaptar → Investigar → Automatizar”**

