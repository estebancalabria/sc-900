# Microsoft Purview: Gobernanza de datos, Data Map y Unified Catalog

En las organizaciones modernas, los datos se generan en grandes volúmenes y provienen de múltiples sistemas, departamentos y entornos. Esta dispersión dificulta su gestión, protección y aprovechamiento.

Para resolver este desafío, se implementa una estrategia de **gobernanza de datos**, cuyo objetivo es garantizar la seguridad, el cumplimiento normativo y, al mismo tiempo, maximizar el valor de negocio de los datos. En este contexto, **Microsoft Purview** proporciona una plataforma integral para descubrir, organizar y gobernar datos a escala empresarial.

Con el crecimiento de la **inteligencia artificial (IA)**, la gobernanza de datos se vuelve aún más crítica, ya que los modelos dependen de datos confiables y de alta calidad. Datos incompletos o mal clasificados pueden generar resultados incorrectos, además de que las regulaciones emergentes exigen un control más estricto sobre el uso de la información.

---

## Conceptos fundamentales de la gobernanza de datos

La gobernanza moderna no solo se enfoca en proteger datos, sino también en hacerlos más accesibles, comprensibles y útiles:

* **Gobernanza federada:** combina control central de políticas con autonomía distribuida en los equipos de negocio.
* **Acceso a los datos:** asegura que los usuarios correctos accedan a la información adecuada.
* **Curación de datos:** organiza y publica datos para su uso seguro y reutilizable.
* **Descubrimiento de datos:** facilita encontrar información relevante rápidamente.
* **Salud de los datos:** mantiene la calidad, consistencia y actualización del dato.
* **Entendimiento de los datos:** aporta contexto mediante metadatos y descriptores.

---

## Roles en la gobernanza de datos

* **Consumidores de datos:** acceden y utilizan datos confiables de forma simplificada.
* **Propietarios de datos:** registran y gestionan activos de datos, controlando calidad y acceso.
* **Data Stewards:** aseguran calidad, linaje, consistencia y descubrimiento.
* **Oficina central de datos:** define políticas, supervisa cumplimiento y gestiona la salud del ecosistema.

---

## Beneficios de la gobernanza de datos

**Para consumidores de datos:**

* Descubrimiento rápido de datos relevantes.
* Acceso seguro y controlado.
* Mejor comprensión del significado del dato.

**Para propietarios y administradores:**

* Mejora en la calidad y curación de datos.
* Uso responsable de la información.
* Análisis de impacto sobre cambios en los datos.

**Para líderes y ejecutivos:**

* Mayor creación de valor a partir de los datos.
* Estandarización del entorno de datos.
* Reducción de costos operativos.

---

# Microsoft Purview Data Map

**Data Map** es la base de la gobernanza de datos en Microsoft Purview.

Es un sistema que crea un **inventario automatizado de datos**, similar al catálogo de una biblioteca, registrando todos los activos de datos y sus características mediante procesos de escaneo.

### Función principal

* Descubrir y catalogar datos en entornos:

  * On-premises
  * Azure
  * AWS
  * Google Cloud
  * SaaS y sistemas híbridos

### Cómo funciona

* **Escaneo:** detecta bases de datos, tablas, archivos y reportes, capturando metadatos como estructura, ubicación y relaciones.
* **Clasificación:** identifica datos sensibles (personales, financieros, etc.) usando patrones automáticos o reglas personalizadas.

Esto permite identificar información sensible antes de usarla en análisis o modelos de IA.

### Tipos de metadatos

* **Técnicos:** estructura, esquemas, tipos de datos.
* **De negocio:** descripciones, contexto y términos.
* **Semánticos:** clasificación y agrupación de datos.
* **Operativos:** ejecución, flujos y tiempos de actualización.

### Importante

Data Map trabaja únicamente con **metadatos**, no con los datos en sí, y no otorga acceso a la información.

---

# Microsoft Purview Unified Catalog

**Unified Catalog** es la capa superior de gobernanza que se construye sobre los metadatos de Data Map. Su objetivo es transformar los datos en activos organizados, gobernados y con valor de negocio.

---

## Componentes clave del Unified Catalog

### Gobernance Domains (Dominios de gobernanza)

Organizan el ecosistema de datos según áreas de negocio como Finanzas, Marketing o RRHH.

Permiten definir límites de gobernanza, propiedad y descubrimiento de datos, alineados con conceptos de negocio.

---

### Data Products

Un **data product** es un conjunto de datos con contexto de negocio, propietario y casos de uso definidos.

* Agrupa activos de datos relacionados.
* Facilita la comprensión para consumidores de datos.
* Mejora la búsqueda usando lenguaje de negocio.

Ejemplo: un modelo de datos creado por un científico de datos puede publicarse como un data product con descripción, uso y datasets asociados.

---

### Glossary Terms (Términos de glosario)

Proveen contexto de negocio y políticas asociadas a los datos.

* Definen conceptos organizacionales.
* Pueden tener significados distintos según el dominio (ej. ventas vs marketing).
* Incluyen políticas de uso, calidad y gobernanza.

---

### Critical Data Elements (CDE)

Son elementos de datos críticos para el negocio.

* Agrupan datos importantes bajo una misma definición lógica.
* Permiten estandarización (ej. “Customer ID” en distintas tablas).
* Pueden tener reglas de calidad y acceso asociadas.
* Ayudan a enfocar esfuerzos de gobernanza en datos de alto impacto.

---

### OKRs (Objectives and Key Results)

Conectan los datos con objetivos de negocio medibles.

* Relacionan data products con resultados empresariales.
* Permiten demostrar el valor del dato en términos de negocio.
* Conectan IT con objetivos estratégicos.

---

### Access Policies

Permiten gestionar accesos a data products mediante un modelo de autoservicio controlado.

* Facilitan la solicitud de acceso.
* Mantienen seguridad y cumplimiento.
* Fomentan innovación sin comprometer control.

---

### Búsqueda y descubrimiento

Unified Catalog permite:

* Búsqueda tradicional por nombre o término.
* Exploración por jerarquías o colecciones.
* Descubrimiento guiado de datos disponibles.
* Búsqueda en lenguaje natural mediante copiloto con IA.

---

### Health Management (Gestión de salud del dato)

Evalúa y mejora la gobernanza del ecosistema de datos.

* Monitorea calidad y cumplimiento.
* Proporciona controles de salud del dato.
* Ofrece acciones para mejorar puntuación de gobernanza.

Beneficios:

* Mejor calidad de datos
* Mayor seguridad
* Cumplimiento regulatorio
* Mayor eficiencia operativa

---

### Data Quality

Permite evaluar y mejorar la calidad de los datos.

* Usa reglas sin código o low-code.
* Incluye reglas sugeridas por IA.
* Genera scores de calidad por activo, producto y dominio.
* Mejora la detección de problemas de datos y su curación.

---

## Relación entre Data Map y Unified Catalog

* **Data Map:** descubre, escanea y clasifica datos, creando el inventario de metadatos.
* **Unified Catalog:** organiza, gobierna y aporta contexto de negocio a esos datos.

En conjunto:

* Data Map provee los datos técnicos (metadatos).
* Unified Catalog los convierte en activos gobernados y utilizables por el negocio.

---

## Conclusión

Microsoft Purview proporciona una solución completa de gobernanza de datos que permite a las organizaciones:

* Descubrir todos sus datos (Data Map).
* Organizar y gobernar su uso (Unified Catalog).
* Mejorar calidad, seguridad y cumplimiento.
* Convertir datos en valor de negocio real.

