## Así es como trabaja el equipo en el día a día dentro de **Microsoft Purview**, desde que se conecta la base de datos hasta que el dato está disponible para los analistas:

---

* **Paso 1: El Administrador configura el entorno**
* **Quién lo hace:** El **Purview Administrator / Tenant Admin** (ej. Laura, la Directora de Seguridad Cloud).
* **Qué hace en el mundo real:** Laura entra al portal, crea la cuenta global de Purview para el banco y define la estructura inicial.
* **Asignación de permisos:** Como ella tiene el control total, va a la sección de control de accesos y le asigna a Carlos el rol de *Data Source Administrator*, y a Sofía el rol de *Data Curator*.


* **Paso 2: La conexión de la infraestructura y carga de datos**
* **Quién lo hace:** El **Data Source Administrator** (ej. Carlos, el Ingeniero de Datos).
* **Qué hace en el mundo real:** Carlos tiene las credenciales técnicas del banco. Entra a la sección de **Fuentes de datos (Data Sources)** de Purview.
* **Dónde va en la herramienta:** Va a la pestaña **Data Catalog** o **Solutions**, selecciona **Sources**, hace clic en *Register* y conecta el servidor **Azure SQL** que contiene la tabla histórica de "Clientes_VIP" y cuentas bancarias. Luego, programa un escaneo (*scan*) para que Purview lea automáticamente las columnas (metadatos) de esa base de datos sin tocar los datos reales.


* **Paso 3: La definición del negocio y la semántica**
* **Quién lo hace:** El **Data Steward** (ej. Sofía, la Analista de Gobierno de Datos).
* **Qué hace en el mundo real:** Sofía no sabe de servidores ni de código, pero sabe qué significan los datos para el banco. Su trabajo es evitar que la gente confunda términos legales o financieros.
* **Dónde va en la herramienta:** Sofía entra a **Data Catalog** > **Glossary (Glosario)**. Como en la consola real tiene asignado el rol técnico de **Data Curator**, la herramienta le permite hacer clic en *New Term*. Ahí crea el término formal **"Ingreso Neto Anual"** y escribe la definición oficial: *"Suma de sueldos menos deducciones impositivas en el año fiscal"*.


* **Paso 4: La curación y clasificación del dato**
* **Quién lo hace:** El **Data Steward / Data Curator** (Sofía).
* **Qué hace en el mundo real:** Sofía busca la tabla de "Clientes_VIP" que importó Carlos. Ve que hay una columna técnica llamada `ING_NET_2`.
* **Dónde va en la herramienta:** Entra al activo de datos dentro del **Unified Catalog**, edita sus propiedades y **asocia** esa columna técnica con el término de glosario **"Ingreso Neto Anual"** que creó en el paso anterior. Además, le aplica una clasificación de privacidad que dice "Información Financiera Altamente Confidencial".


* **Paso 5: El consumo y descubrimiento de la información**
* **Quién lo hace:** El **Data Reader** (ej. Mateo, un Analista de Negocios de Marketing).
* **Qué hace en el mundo real:** Mateo necesita armar una campaña para clientes de altos ingresos, pero no sabe en qué servidor o base de datos guardaron esa información.
* **Dónde va en la herramienta:** Mateo entra al portal de Purview y, como tiene acceso de solo lectura, va directo a la barra de búsqueda superior (**Search catalog**). Escribe *"Ingreso Neto Anual"*. Al instante, Purview le muestra la tabla "Clientes_VIP" que Carlos cargó y Sofía documentó. Mateo puede ver el significado del dato y pedir acceso a la base de datos real sabiendo exactamente qué contiene, sin romper nada ni ver información prohibida.
