# Microsoft Security Copilot - Resumen

## Introducción

Microsoft Security Copilot es una plataforma de seguridad impulsada por Inteligencia Artificial generativa diseñada para ayudar a los equipos de seguridad a responder amenazas, investigar incidentes y administrar riesgos a velocidad de máquina.

La solución combina modelos de IA avanzados, inteligencia global de amenazas de Microsoft, señales de seguridad, plugins especializados y conocimiento organizacional para mejorar la eficiencia de los analistas y fortalecer la postura de seguridad de las organizaciones.

---

# ¿Qué es Microsoft Security Copilot?

Microsoft Security Copilot es una herramienta de análisis de seguridad basada en la nube que permite:

* Investigar incidentes de seguridad.
* Analizar amenazas.
* Automatizar tareas repetitivas.
* Generar consultas KQL mediante lenguaje natural.
* Analizar scripts sospechosos.
* Crear informes técnicos y ejecutivos.
* Gestionar riesgos y postura de seguridad.
* Acelerar la respuesta ante incidentes.

Su principal objetivo es permitir que los equipos de seguridad trabajen a velocidad de máquina frente al creciente volumen y complejidad de amenazas.

---

# Desafíos actuales de seguridad

Las organizaciones enfrentan:

* Incremento constante de ataques cibernéticos.
* Mayor sofisticación de las amenazas.
* Escasez de profesionales especializados.
* Necesidad de automatización e integración de herramientas.
* Exigencias crecientes de cumplimiento, privacidad y gobierno.

Security Copilot busca abordar estos desafíos mediante la combinación de IA y experiencia humana.

---

# Casos de uso principales

## Investigación y remediación de amenazas

* Analizar incidentes complejos.
* Obtener contexto sobre alertas.
* Priorizar amenazas.
* Generar recomendaciones de respuesta.
* Guiar procesos de remediación.

## Generación de consultas KQL y análisis de scripts

* Crear consultas KQL usando lenguaje natural.
* Analizar scripts sospechosos.
* Comprender malware y código potencialmente malicioso.

## Gestión de riesgos y postura de seguridad

* Identificar riesgos prioritarios.
* Evaluar exposición.
* Detectar oportunidades de mejora.

## Resolución de problemas de TI

* Sintetizar información.
* Diagnosticar problemas.
* Obtener recomendaciones accionables.

## Gestión de políticas

* Crear políticas.
* Detectar conflictos.
* Resumir configuraciones existentes.

## Configuración de flujos de trabajo seguros

* Crear grupos.
* Configurar permisos.
* Definir parámetros de acceso.

## Creación de informes

* Elaborar informes para equipos técnicos y ejecutivos.
* Resumir incidentes y riesgos.
* Adaptar resultados según la audiencia.

---

# Experiencias de uso

## Experiencia Standalone

Portal independiente donde los usuarios interactúan con Security Copilot mediante lenguaje natural.

Permite generar:

* Texto.
* Imágenes.
* Documentos.
* Informes.
* Resúmenes.

## Experiencia Embedded

Las capacidades de Copilot están integradas en soluciones como:

* Microsoft Defender XDR
* Microsoft Sentinel
* Microsoft Intune
* Microsoft Entra
* Microsoft Purview

---

# Procesamiento de lenguaje natural (NLP)

Security Copilot utiliza Azure OpenAI Service y modelos de lenguaje de gran escala (LLM) para comprender consultas realizadas en lenguaje natural.

Estas capacidades permiten:

* Interpretar preguntas complejas.
* Generar respuestas contextualizadas.
* Automatizar investigaciones de seguridad.
* Facilitar el análisis de amenazas.

---

# Integración con fuentes de seguridad especializadas

Security Copilot combina los LLM con:

* Inteligencia global de amenazas de Microsoft.
* Más de 65 billones de señales de seguridad diarias.
* Productos de seguridad de Microsoft.
* Soluciones de terceros.
* Fuentes OSINT.
* Bases de conocimiento corporativas.
* Plugins especializados.

Esto permite generar respuestas más precisas, relevantes y contextualizadas.

---

# Seguridad y privacidad de los datos

Microsoft establece que:

* Los datos permanecen bajo control de la organización.
* No se utilizan para entrenar modelos fundacionales.
* Están protegidos mediante controles empresariales de seguridad y cumplimiento.
* Se respetan los permisos y controles de acceso existentes.

---

# Terminología fundamental

## Session (Sesión)

Conversación completa entre el usuario y Security Copilot.

Mantiene el contexto de todos los prompts y respuestas.

## Prompt

Pregunta o instrucción enviada por el usuario mediante lenguaje natural.

## Prompt Bar

Interfaz principal para interactuar con Security Copilot.

## Capability (Capacidad)

Función específica ejecutada por Copilot.

Ejemplos:

* Resumir incidentes.
* Analizar scripts.
* Generar consultas KQL.

## Plugin

Conjunto de capacidades asociadas a una fuente de datos específica.

Puede conectarse con:

* Microsoft Defender XDR
* Microsoft Sentinel
* Microsoft Intune
* Microsoft Entra
* ServiceNow
* Splunk
* Sitios web públicos
* Plugins personalizados

## Workspace

Entorno de trabajo independiente dentro de un tenant.

Beneficios:

* Separación de equipos.
* Control de costos.
* Gestión independiente de capacidades.
* Cumplimiento normativo.

## Agents

Asistentes de IA especializados capaces de ejecutar tareas de forma autónoma.

## Orchestrator

Componente encargado de coordinar capacidades y plugins para responder solicitudes.

---

# Cómo procesa Security Copilot una solicitud

Cuando un usuario envía un prompt:

1. El Orchestrator interpreta la solicitud.
2. Identifica las capacidades necesarias.
3. Invoca plugins relevantes.
4. Obtiene información desde diversas fuentes.
5. Ejecuta validaciones de seguridad.
6. Genera una respuesta contextualizada.

---

# Process Log

Security Copilot proporciona un registro detallado del proceso utilizado para construir una respuesta.

Permite visualizar:

* Capacidades ejecutadas.
* Plugins utilizados.
* Acciones realizadas por el Orchestrator.
* Flujo de procesamiento.
* Verificaciones de seguridad ejecutadas.

---

# Safety Checks

Antes de generar una respuesta, Security Copilot ejecuta controles automáticos de seguridad.

Estos controles ayudan a:

* Garantizar respuestas seguras.
* Reducir riesgos asociados a IA generativa.
* Validar información utilizada.
* Cumplir políticas organizacionales.

---

# Elementos de un Prompt Efectivo

La calidad de la respuesta depende en gran medida de la calidad del prompt.

Microsoft recomienda incluir cuatro elementos fundamentales.

## Goal (Objetivo)

Define qué información se necesita.

## Context (Contexto)

Explica por qué se necesita la información o cómo será utilizada.

## Expectations (Expectativas)

Indica el formato esperado de la respuesta.

Ejemplos:

* Tabla.
* Resumen ejecutivo.
* Lista de acciones.
* Informe técnico.

## Source (Fuente)

Especifica qué plugins o fuentes deben utilizarse.

Ejemplos:

* Microsoft Defender XDR.
* Microsoft Sentinel.
* Microsoft Intune.
* Microsoft Entra.

---

# Buenas prácticas para prompts

## Ser específico

Mientras más detallada sea la solicitud, más útil será la respuesta.

## Proporcionar contexto

Ayuda a Copilot a comprender mejor el escenario.

## Iterar

Es habitual realizar consultas de seguimiento para profundizar una investigación.

## Dar instrucciones positivas

Indicar qué se desea obtener en lugar de enfocarse únicamente en restricciones.

## Dirigirse directamente a Copilot

Utilizar expresiones como:

* "You should..."
* "You must..."
* "You need to..."

---

# Promptbooks

Security Copilot incluye Promptbooks que proporcionan:

* Prompts predefinidos.
* Sugerencias de consultas.
* Flujos guiados de investigación.
* Estandarización de tareas frecuentes.

---

# Habilitación de Microsoft Security Copilot

Para comenzar a utilizar Security Copilot es necesario completar un proceso de incorporación (onboarding) que incluye:

1. Identificar el tipo de cliente.
2. Aprovisionar capacidad.
3. Configurar el entorno predeterminado.
4. Asignar permisos y roles.

---

# Identificación del tipo de cliente

## Clientes Microsoft 365 E5 y E7

Security Copilot está incluido en estas licencias.

Microsoft realiza el aprovisionamiento automáticamente mediante **Zero-Click Activation**, por lo que:

* No se requiere configuración de Azure.
* No se requiere aprovisionamiento manual de capacidad.
* La activación se realiza automáticamente tras una notificación previa.

## Clientes sin Microsoft 365 E5 o E7

Deben realizar el aprovisionamiento manual de capacidad mediante Security Compute Units (SCU).

---

# Security Compute Units (SCU)

Las SCU son la unidad de medida de capacidad computacional utilizada por Security Copilot.

Se utilizan tanto en:

* La experiencia Standalone.
* La experiencia Embedded.

## Características

* Se facturan por hora.
* Pueden incrementarse o reducirse según demanda.
* No requieren compromisos a largo plazo.
* Admiten capacidad adicional bajo demanda mediante overage.

## Overage

Permite utilizar capacidad adicional cuando las SCU aprovisionadas se agotan.

Puede configurarse como:

* Ilimitado.
* Con un límite máximo definido.

Microsoft recomienda comenzar con:

* 3 SCU.
* Overage ilimitado.

El mínimo permitido es 1 SCU y el máximo es 100 SCU.

---

# Requisitos para aprovisionar capacidad

Para aprovisionar Security Copilot se requiere:

* Una suscripción de Azure.
* Rol Azure Owner o Azure Contributor sobre el Resource Group.
* Rol Security Administrator o superior en el tenant.

Importante:

Ser Global Administrator en Microsoft Entra no implica automáticamente tener permisos sobre recursos de Azure.

---

# Métodos de aprovisionamiento

## Desde Security Copilot (Recomendado)

Un asistente guía la configuración de:

* Workspace.
* Suscripción de Azure.
* Resource Group.
* Región.
* Nombre de capacidad.
* Cantidad de SCU.

## Desde Azure Portal

Security Copilot aparece como un servicio nativo de Azure.

Permite configurar:

* Suscripción.
* Resource Group.
* Región.
* Capacidad.
* Cantidad de SCU.

---

# Monitoreo de uso

Security Copilot incluye un panel de monitoreo que permite:

* Visualizar consumo de SCU.
* Analizar uso por Workspace.
* Identificar plugins utilizados.
* Identificar usuarios que iniciaron sesiones.
* Exportar datos.
* Consultar hasta 90 días de historial.

---

# Configuración del entorno predeterminado

Para configurar el entorno se requiere al menos el rol:

* Security Administrator

La configuración inicial incluye:

## Capacidad SCU

Cada Workspace debe tener una capacidad asociada.

## Almacenamiento de datos

Los datos pueden almacenarse en distintas regiones:

* Unión Europea (EUDB)
* Reino Unido
* Estados Unidos
* Australia y Nueva Zelanda
* Japón
* Canadá
* Sudamérica

## Ubicación de evaluación de prompts

Permite definir si los prompts deben evaluarse:

* Dentro de la misma región geográfica.
* En cualquier región del mundo.

---

# Integración con Microsoft Purview

Puede habilitarse el registro de auditoría mediante Microsoft Purview.

Permite registrar:

* Acciones administrativas.
* Acciones de usuarios.
* Respuestas generadas por Copilot.
* Actividad de plugins Microsoft y no Microsoft.

Esta configuración aplica a todo el tenant.

---

# Configuración de compartición de datos

Los administradores pueden decidir si compartir información con Microsoft para:

## Mejorar el producto

Permite analizar prompts y respuestas para optimizar:

* Selección de plugins.
* Calidad de respuestas.
* Latencia.
* Formatos de salida.

## Mejorar los modelos de IA de seguridad

Permite mejorar las capacidades de Copilot.

Importante:

**Los datos compartidos nunca se utilizan para entrenar modelos fundacionales de IA.**

Estas configuraciones pueden realizarse por Workspace.

---

# Configuración de Plugins

Los administradores pueden:

* Habilitar o deshabilitar plugins.
* Restringir acceso a plugins.
* Gestionar plugins personalizados.
* Controlar acceso a datos de Microsoft 365.

La configuración se realiza por Workspace.

---

# Roles de Security Copilot

Security Copilot incorpora dos roles propios:

## Copilot Owner

Permite:

* Administrar configuración.
* Gestionar plugins.
* Asignar permisos.
* Administrar Workspaces.

## Copilot Contributor

Permite utilizar la plataforma y ejecutar tareas autorizadas.

---

# Roles que heredan acceso de Copilot Owner

## Microsoft Entra

* Global Administrator
* Security Administrator
* Billing Administrator
* Compliance Administrator
* Intune Administrator

## Microsoft Purview

* Purview Compliance Administrator
* Purview Data Governance Administrator
* Purview Organization Management

---

# Modelo de permisos

Security Copilot sigue el principio de mínimo privilegio.

Además:

* Los roles de Copilot no conceden acceso automático a datos de seguridad.
* Los usuarios deben poseer permisos sobre cada producto utilizado.

Ejemplo:

Un usuario puede acceder a Security Copilot, pero necesitará:

* Microsoft Sentinel Reader para consultar datos de Sentinel.
* Intune Endpoint Security Manager para acceder a información de Intune.

---

# Modelo OBO (On Behalf Of)

La mayoría de los plugins Microsoft utilizan el modelo OBO.

Esto significa que:

* Copilot reconoce las licencias del usuario.
* Utiliza los permisos existentes.
* Accede a los servicios en nombre del usuario.

Por lo tanto, Copilot nunca supera los permisos que el usuario ya posee.

---

# Resumen

Microsoft Security Copilot es una plataforma de seguridad impulsada por IA que combina modelos de lenguaje avanzados, inteligencia global de amenazas, capacidades especializadas y datos organizacionales para ayudar a los equipos de seguridad a trabajar a velocidad de máquina. La plataforma incorpora conceptos como prompts, sesiones, plugins, capacidades, workspaces, agentes y un Orchestrator que coordina todas las operaciones. Además, proporciona mecanismos de transparencia mediante Process Logs, protección mediante Safety Checks y una arquitectura flexible basada en Security Compute Units (SCU). Su implementación incluye aprovisionamiento de capacidad, configuración de Workspaces, administración de plugins, integración con Microsoft Purview y un modelo de permisos basado en mínimo privilegio, permitiendo a las organizaciones adoptar la IA de forma segura, escalable y controlada.
