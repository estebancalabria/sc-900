# DDOS

## 🛡️ 1. Azure DDoS Protection: Network Protection vs. IP Protection

Azure ofrece dos sabores para proteger tus recursos públicos contra ataques de denegación de servicio (Capa 3 y Capa 4). La diferencia entre ellos es puramente comercial y de alcance de recursos:

### **IP Protection (La opción económica/básica)**

* **Cómo funciona:** Se asocia directamente a una **IP pública individual** (por ejemplo, la IP de una máquina virtual o de un Load Balancer).
* **Qué incluye:** Mitigación de ingeniería pura (*core engineering mitigation*). Es decir, el motor automático de Azure detecta si hay una inundación de tráfico basura hacia esa IP y lo frena para que tu servicio no se caiga.
* **Qué NO tiene:** No te da ninguna garantía económica ni soporte premium.

### **Network Protection (La opción corporativa/Premium)**

* **Cómo funciona:** Se compra a nivel de **toda tu red virtual (VNet)** y protege automáticamente a todos los recursos que estén conectados dentro de ella.
* **El valor agregado (Lo que menciona el texto):** Incluye **garantías de costo (*cost protection*)**. Esto significa que si sufrís un ataque DDoS masivo y tus recursos de Azure (como las máquinas virtuales) empiezan a escalar de forma automática para aguantar los trapos, generándote una factura de miles de dólares, Microsoft te cubre y te devuelve esa plata. Además, te da descuentos comerciales en servicios asociados como el WAF.

---

## 🌐 2. La Capa 7 (Aplicación) y el WAF

Acá es donde el examen suele meter la trampa para ver si pisás el palito:

> **Regra de oro:** Ninguno de los dos planes de Azure DDoS Protection (ni Network ni IP) te protege por sí solo contra ataques a la **Capa 7 (Capa de Aplicación)**. Ellos solo miran volumen de tráfico (red y transporte).

Si un atacante intenta tirar tu sitio web explotando vulnerabilidades del código, inyecciones SQL o ataques dirigidos específicamente a la lógica de la aplicación, el servicio de DDoS de Azure no lo va a frenar.

Para defenderte en ese nivel, la oración de resumen lo deja clarito: **organizaciones deben usar un Web Application Firewall (WAF)**. El WAF es el único componente que inspecciona el contenido de las peticiones HTTP/HTTPS (Capa 7) para bloquear las amenazas web. Por eso, en una arquitectura segura, DDoS Protection y WAF siempre trabajan juntos en capas.


## 🛠️ Paso a Paso: Implementación de Azure DDoS Network Protection

### Etapa 1: Crear el Plan de Protección DDoS

El plan es el recurso administrativo que define el conjunto de redes virtuales que tendrán habilitada la protección avanzada.

1. Iniciá sesión en el **Portal de Azure** (`portal.azure.com`).
2. En la barra de búsqueda superior, escribí **"DDoS protection plans"** (Planes de protección contra DDoS) y seleccionalo en los resultados.
3. Hacé clic en el botón **➕ Create** (Crear).
4. En la pestaña *Basics*, configurá los datos esenciales:
* **Subscription & Resource Group:** Elegí tu suscripción y el grupo de recursos de seguridad o red.
* **Name:** Dale un nombre descriptivo, por ejemplo: `DDoS-Plan-Corporativo`.
* **Region:** Seleccioná la región donde están tus recursos de red.


5. Hacé clic en **Review + create** y luego en **Create** para que se despliegue el plan. *(Este recurso se crea en segundos, a diferencia del Firewall)*.

---

### Etapa 2: Vincular el Plan a la VNet de tu Aplicación Web

La protección DDoS no se aplica directo a la máquina virtual o al App Service, sino que **se activa a nivel de la Virtual Network (VNet)** para proteger todas las IPs públicas que residan en ella.

1. En la barra de búsqueda superior del portal, buscá y seleccioná **Virtual networks** (Redes virtuales).
2. Hacé clic sobre la **VNet específica** donde está hosteada tu aplicación web de cara al público.
3. En el menú lateral izquierdo de la VNet, bajá hasta el apartado de **Settings** (Configuración) y hacé clic en **DDoS protection** (Protección contra DDoS).
4. En la pantalla central, marcá la opción **Enable** (Habilitar).
5. En el menú desplegable que aparece abajo (*DDoS protection plan*), seleccioná el plan que creamos en la Etapa 1 (`DDoS-Plan-Corporativo`).
6. Hacé clic en el botón **Save** (Guardar) arriba a la izquierda.

---

### Etapa 3: Configurar la Telemetría y Alertas (Para cumplir con el requerimiento del examen)

Para obtener la *"telemetría detallada"* que menciona el enunciado, necesitás habilitar el envío de logs a tu Log Analytics Workspace.

1. Buscá en el portal la **IP Pública (Public IP)** asociada al Balanceador de Carga o Application Gateway de tu aplicación web.
2. En su menú izquierdo, ingresá a **Diagnostic settings** (Configuración de diagnóstico).
3. Hacé clic en **Add diagnostic setting** (Agregar configuración de diagnóstico).
4. Tildá las tres casillas críticas de DDoS:
* `DDoSProtectionNotifications`: Te avisa al instante si el tráfico superó el umbral y la mitigación activa comenzó.
* `DDoSMitigationFlowLogs`: Te da el análisis forense línea por línea del tráfico sucio que se está bloqueando.
* `DDoSMitigationReports`: El reporte ejecutivo post-ataque.


5. En *Destination details*, tildá **Send to Log Analytics workspace** y seleccioná tu repositorio de logs (donde también podrías tener conectado Sentinel).
6. Guardá los cambios.

---

### Conclusion

* **Umbrales inteligentes:** A diferencia de la protección por defecto de Azure (que solo salta ante ataques masivos que pongan en riesgo a todo el centro de datos), **Network Protection** usa Machine Learning para analizar el tráfico normal de *tu* aplicación durante días. Si tu app se degrada con apenas un pico moderado, la IA de DDoS ajusta los umbrales hacia abajo automáticamente para empezar a mitigar y limpiar el tráfico de inmediato.
* **Garantía de costos:** Si el ataque DDoS obliga a tu aplicación a autoescalar (generando decenas de VMs de soporte por culpa del tráfico falso), Microsoft te devuelve el dinero de ese gasto extra en infraestructura mediante créditos de soporte gracias a la póliza que incluye este plan.
