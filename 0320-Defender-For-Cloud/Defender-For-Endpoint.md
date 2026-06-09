# Microsoft Defender for Endpoint 

Para que pueda proteger, monitorear y reaccionar ante amenazas en las computadoras de la empresa, necesita estar metido adentro del sistema operativo.

La forma en que se "instala" varía según el sistema operativo que uses, pero el concepto técnico clave es el Onboarding (o Incorporación):

💻 1. En Windows 10 y Windows 11 (Viene preinstalado, pero hay que activarlo)
Si las computadoras de tus usuarios usan Windows 10 o Windows 11, no tenés que descargar ningún instalador pesado .exe o .msi.

El código y el motor de Defender ya vienen integrados de fábrica dentro del propio sistema operativo.

Lo que hace el Administrador: Ejecuta un paquete de configuración o un script (generalmente distribuido de forma masiva a través de herramientas como Microsoft Intune, Group Policies/GPO o Configuration Manager).

Qué hace ese script: Despierta el componente de Endpoint, le inyecta las credenciales de tu empresa y lo "asocia" a tu Tenant de la nube. A partir de ese segundo, la computadora empieza a reportar logs y alertas al portal de seguridad.

🍎 🐧 2. En Mac, Linux, iOS o Android (Ahí sí se instala de cero)
Como Microsoft no es dueño de esos sistemas operativos, ahí no viene nada preinstalado. En estos entornos, el administrador o el usuario sí tienen que instalar una aplicación real:

En macOS y Linux: Se descarga e instala un paquete específico corporativo (un archivo .pkg en Mac o un paquete desde el gestor de descargas de la distribución de Linux).

En dispositivos móviles (Celulares/Tablets): Los usuarios se bajan la app oficial de Microsoft Defender desde la Google Play Store o la Apple App Store, e inician sesión con su cuenta de la empresa para activar la protección de endpoint.

🕵️ ¿Qué es lo que corre de fondo una vez instalado?
Una vez que el dispositivo pasó por el proceso de Onboarding, lo que queda corriendo en la computadora es un agente de fondo (un sensor).

Este sensor no se dedica a escanear el disco de forma pesada todo el tiempo, sino que se queda escuchando eventos del comportamiento del sistema en tiempo real: qué procesos se abren, qué archivos se modifican y qué conexiones de red hace la máquina. Si detecta un comportamiento típico de un ransomware o un malware, lo frena al instante y le manda la alerta al panel central de Defender.

---

# Defender for Endpoint vs Defender for Servers

**No, no son el mismo producto**, pero están íntimamente relacionados y comparten el mismo "cerebro" tecnológico.

Para el examen SC-900 y para entender el licenciamiento de Microsoft, la diferencia es la siguiente: **Defender for Endpoint protege los dispositivos de los usuarios finales (PCs, notebooks, celulares)**, mientras que **Defender for Servers protege la infraestructura de servidores de la empresa (tanto en la nube como locales)**.

Acá tenés el desglose de cómo se separan y cómo interactúan:

---

### 💻 1. Microsoft Defender for Endpoint

* **¿Para quién es?** Está pensado para los dispositivos de los empleados del día a día.
* **Sistemas operativos:** Windows 10, Windows 11, macOS, Android, iOS.
* **Cómo se compra:** Se licencia **por usuario** (normalmente viene incluido en los planes corporativos de Microsoft 365 E5 / Business Premium, o se compra como un "add-on" por cada empleado).

---

### 🖥️ 2. Microsoft Defender for Servers

* **¿Para quién es?** Está pensado para cuidar los servidores que sostienen las aplicaciones y bases de datos de la empresa.
* **Sistemas operativos:** Windows Server y Linux Server.
* **Dónde viven esos servidores?** No importa. Pueden ser máquinas virtuales en **Azure**, servidores en otras nubes (**AWS / GCP**) o servidores físicos en el **datacenter local** de tu oficina.
* **Cómo se compra:** No se licencia por usuario (porque a un servidor no lo usa una sola persona). Se compra **por servidor/máquina virtual por hora o por mes**, y es uno de los tantos módulos (planes) que forman parte del ecosistema de **Microsoft Defender for Cloud**.

---

### 🤝 ¿Dónde se cruzan y por qué se confunden? (La trampa)

La confusión viene porque Microsoft usa la tecnología de **Defender for Endpoint** como parte del escudo protector de **Defender for Servers**.

Cuando un administrador activa el plan de *Defender for Servers* en la nube para proteger sus servidores de producción, el sistema hace un despliegue automático por atrás y les instala el sensor de *Defender for Endpoint*.

> 💡 **En resumen para la certificación:**
>  * Si la pregunta te habla de proteger la infraestructura, VMs de Azure, servidores Linux o Windows Server de fondo, la respuesta es **Defender for Servers** (dentro de Defender for Cloud).
> * Si la pregunta te habla de proteger las computadoras portátiles de los empleados, el trabajo remoto o dispositivos móviles, la respuesta es **Microsoft Defender for Endpoint**.
 
