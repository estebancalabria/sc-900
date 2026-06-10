# LAB-M365-PURVIEW-0200: Detección y Revisión de Comunicaciones Riesgosas

## 🎯 Objetivo del Laboratorio

Al finalizar este laboratorio, habrás configurado el ciclo de vida completo de la solución **Communication Compliance** en Microsoft Purview. Aprenderás a realizar la **Configuración de Políticas** para detectar lenguaje inapropiado, simularás el proceso de **Revisión de Mensajes** (*Message Review*), explorarás las herramientas de **Monitoreo** (*Monitoring*) y entenderás cómo **Microsoft Security Copilot** asiste resumiendo incidentes complejos.

---

## 🏗️ Escenario del Negocio

El departamento de Recursos Humanos de la empresa *"Global Finance"* ha detectado un aumento de tensiones en los canales internos. Te solicitan configurar una solución automatizada que detecte insultos, acoso o lenguaje ofensivo en los chats de Microsoft Teams. Además, necesitan designar a un miembro de RR.HH. como revisor oficial para que tome acciones ante las alertas y use Inteligencia Artificial para acelerar la investigación de hilos de chat muy largos.

---

## 🛠️ Requisitos Previos

* Acceso al portal de cumplimiento: **`https://purview.microsoft.com`**.
* Licencia de Microsoft 365 E5 (o tenant de pruebas/Developer con el add-on de Compliance).
* El usuario que configure el laboratorio debe tener asignado el rol de **Communication Compliance Admin** o **Global Administrator**, y el revisor de RR.HH. debe estar en el rol de **Communication Compliance Reviewer**.

---

## 🥼 Paso a Paso del Laboratorio

### Parte 1: Configuración de la Política (Policy Configuration)

En esta etapa vamos a definir las reglas del radar: qué canales vamos a monitorear y qué lenguaje específico activará las alarmas.

1. Abrí tu navegador e ingresá a **`https://purview.microsoft.com`**.
2. En la barra de navegación izquierda, hacé clic en **Solutions** (Soluciones) y seleccioná **Communication Compliance**.
3. En el menú interno izquierdo, ingresá a la pestaña **Policies** (Directivas).
4. Hacé clic en el botón **+ Create policy** (Crear directiva) y elegís la opción **Custom policy** (Directiva personalizada) para armarla desde cero.
5. **Nombre y Descripción:**
* **Name:** `Detectar-Acoso-Teams`
* **Description:** `Monitoreo de lenguaje ofensivo e inapropiado en los canales de la empresa.`
* Hacé clic en **Next**.


6. **Elegir Usuarios y Revisores:**
* **Choose users and groups (¿A quién monitoreamos?):** Seleccioná **All users** (Todos los usuarios).
* **Choose reviewers (¿Quién investiga?):** Buscá y agregá el usuario que usará el equipo de Recursos Humanos (para la prueba, podés agregarte a vos mismo).
* Hacé clic en **Next**.


7. **Elegir Canales (Ubicaciones):**
* Verás switches para Exchange, Teams, Viva Engage, etc. Para este laboratorio, dejá encendido únicamente el switch de **Microsoft Teams** (así el motor se enfoca en chats privados y canales). Hacé clic en **Next**.


8. **Condiciones de Detección:**
* Hacé clic en *Add condition* y seleccionás **Content matches classifiers** (El contenido coincide con clasificadores).
* En la lista de clasificadores de Microsoft, tildá las opciones de **Harassment** (Acoso) y **Profanity** (Lenguaje soez/insultos).
* Hacé clic en **Next**.


9. **Finalizar:**
* Revisá el resumen de tu configuración y hacé clic en **Create policy**. Luego hacé clic en **Done**.



---

### Parte 2: El Proceso de Revisión (Message Review)

*Nota de simulación: En un entorno real, cuando un usuario escribe un insulto en Teams, la alerta tarda unos minutos en procesarse e impactar en el portal.*

1. En el panel de **Communication Compliance**, hacé clic en la sección de la izquierda llamada **Pending** (Pendientes) o entrá directo a tu política `Detectar-Acoso-Teams`.
2. Vas a ver una lista con los mensajes sospechosos capturados. Hacé clic sobre uno de ellos (ej: un mensaje simulado que dice *"Sos un inútil, te voy a hacer echar"*).
3. Se te abrirá la interfaz de **Message Review** (Revisión de mensajes). Acá vas a simular el rol del investigador de RR.HH. analizando el panel de acciones superior:
* **Pestaña Source:** Te muestra el mensaje de texto crudo tal cual se envió.
* **Pestaña Conversation:** Te muestra el contexto (qué se habló antes y qué se habló después en ese chat de Teams).


4. **Ejecutar una Acción:** Arriba en la barra de tareas, hacé clic en el botón **Escalate** (Escalar) para enviarle una notificación formal al mánager del empleado, o hacé clic en **Remove message** en Teams para borrar el insulto del chat de forma remota para que nadie más lo vea.

---

### Parte 3: Asistencia de IA (Microsoft Security Copilot)

Cuando un hilo de conversación de Teams es gigantesco y los empleados vienen discutiendo hace días, leer línea por línea es inviable. Aquí entra la IA generativa.

1. Dentro de la misma pantalla de revisión del mensaje ofensivo, localizá el panel lateral derecho de **Microsoft Security Copilot** (o el botón de *Summarize* integrado).
2. Hacé clic en el botón **Summarize conversation** (Resumir conversación).
* **Resultado Esperado:** Copilot analizará todo el contexto del chat y te entregará en pantalla un párrafo corto redactado en lenguaje natural (ej: *"El usuario A muestra un patrón de frustración repetitivo hacia el usuario B debido a la entrega de un reporte, culminando en comentarios despectivos sobre su capacidad laboral"*). Esto consolida la capacidad de **Microsoft Security Copilot** para resúmenes ejecutivos de incidentes.



---

### Parte 4: Auditoría y Tableros (Monitoring)

Para cerrar el ciclo, necesitamos ver las métricas macro de la empresa.

1. En el menú izquierdo de Communication Compliance, hacé clic en **Dashboard** (Panel de control).
2. **Resultado Esperado (Monitoring):** Verás gráficos estadísticos e históricos que reflejan:
* Cuántas alertas totales saltaron en la última semana.
* Cuál es el canal más problemático (si Exchange o Teams).
* El tiempo promedio que tardan los revisores en resolver un caso.


3. Dirigite a la pestaña **Audit log** (Log de auditoría) abajo a la izquierda para verificar que cada acción que tomó el revisor (como borrar el mensaje o escalarlo) quedó registrada con fecha y hora de forma inalterable para auditorías legales de la empresa.

---

## 📊 Cuadro de Validación Teórica para el Alumno

| Lo que viste o hiciste en el portal | Concepto Técnico Asociado |
| --- | --- |
| Definir el canal de Teams y seleccionar el clasificador "Harassment". | **Policy Configuration** |
| Entrar al panel de pendientes, leer el chat y usar los botones de Borrar o Escalar el mensaje. | **Message Review** |
| Ver los gráficos de torta con las tendencias de infracciones y revisar los logs inalterables. | **Monitoring** |
| Apretar el botón para obtener un párrafo resumen con el contexto del conflicto sin leer todo el chat. | **Microsoft Security Copilot** |
