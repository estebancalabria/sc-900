# LAB-M365-PURVIEW-0100: Clasificación y Protección de Documentos Sensibles

## 🎯 Objetivo del Laboratorio

Al finalizar este laboratorio, habrás configurado un escenario completo de protección de información en Microsoft Purview. Aprenderás a crear una **Etiqueta de Sensibilidad**, aplicarle **Marcado de Contenido**, y desplegarla mediante una **Política de Etiquetas** que fuerce el **Etiquetado Obligatorio** y la **Justificación de Cambio**.

---

## 🏗️ Escenario del Negocio

La empresa *"Global Finance"* necesita proteger sus reportes financieros trimestrales. Te han encomendado la tarea de asegurar que estos archivos lleven siempre una marca de agua confidencial, que ningún usuario pueda guardar un documento nuevo sin clasificarlo, y que si alguien intenta bajarle el nivel de seguridad a un archivo, deba explicar obligatoriamente sus motivos por escrito.

---

## 🛠️ Requisitos Previos

* Acceso a un Tenant de prueba de Microsoft 365 con licencias que incluyan Purview (ej: Microsoft 365 E5 o esquema de pruebas Developer).
* Cuenta con el rol de **Global Administrator** o **Compliance Administrator**.
* El portal web a utilizar será: **`https://purview.microsoft.com`**.

---

## 🥼 Paso a Paso del Laboratorio

### Parte 1: Creación de la Etiqueta (Sensitivity Label) y Marcado de Contenido

En esta etapa vamos a crear el "sello" digital que viajará incrustado en los metadatos de los archivos de forma persistente.

1. Abrí tu navegador e ingresá a **`https://purview.microsoft.com`**.
2. En la barra de navegación izquierda, hacé clic en **Solutions** (Soluciones) y luego seleccioná **Information Protection**.
3. En el menú interno izquierdo, hacé clic en **Labels** (Etiquetas).
4. En el panel principal, hacé clic en el botón **+ Create a label** (Crear una etiqueta).
5. **Configuración de Información General:**
* **Name (Nombre):** `Altamente Confidencial`
* **Display name (Nombre para mostrar):** `Altamente Confidencial`
* **Description for users (Descripción):** `Utilizar únicamente para reportes financieros y secretos comerciales.`
* Hacé clic en **Next**.


6. **Definir el Ámbito (Scope):**
* Asegurate de que la opción **Items** (Elementos) esté **tildada** y que adentro figuren activos **Files** (Archivos) y **Emails** (Correos electrónicos).
* Hacé clic en **Next**.


7. **Elegir la Protección para los Elementos:**
* Tildá la casilla que dice **Apply or remove content marking** (Aplicar o quitar marcado de contenido).
* *Nota: Dejá la opción de cifrado (Encrypt) destildada para este laboratorio básico.*
* Hacé clic en **Next**.


8. **Configurar el Marcado de Contenido (Content Marking):**
* Activá el interruptor general pasándolo a **On**.
* Tildá la casilla **Add a watermark** (Agregar una marca de agua).
* Hacé clic en el enlace **Customize text** (Personalizar texto) que aparece abajo y configurá lo siguiente:
* **Watermark text:** `PROPIEDAD DE GLOBAL FINANCE`
* **Font size (Tamaño):** `24`
* **Layout (Disposición):** `Diagonal`


* Hacé clic en **Save** y luego en **Next**.


9. **Auto-labeling (Etiquetado automático):**
* Dejá el interruptor en **Off** (lo haremos manual para la prueba). Hacé clic en **Next**.


10. **Revisión Final:**
* Avanzá las pantallas siguientes dejando las opciones por defecto (*Protection settings for groups and sites* y *Schematized data assets* en Off) hasta llegar al final.
* Hacé clic en **Create label** (Crear etiqueta). Luego, hacé clic en **Done** (Listo).



---

### Parte 2: Publicación y Configuración de Reglas Clientes (Label Policy)

Ahora que la etiqueta existe, debemos distribuirla a los usuarios y configurar el comportamiento obligatorio de las aplicaciones de Office.

1. En la misma pantalla de **Information Protection**, hacé clic en la pestaña superior que dice **Label policies** (Directivas de etiquetas).
2. Hacé clic en el botón **Publish labels** (Publicar etiquetas).
3. En la ventana lateral, hacé clic en **Choose sensitivity labels to publish** (Elegir etiquetas para publicar).
4. Tildá la casilla al lado de nuestra etiqueta **Altamente Confidencial** y hacé clic en **Add** (Agregar). Luego hacé clic en **Next**.
5. **Asignación de Usuarios:**
* Dejá seleccionada la opción **All users and groups** (Todos los usuarios y grupos) para que impacte en toda la empresa. Hacé clic en **Next**.


6. **Configuración de la Directiva (Policy Settings):**
* Aquí es donde ocurren las reglas operativas del examen. **Tildá las siguientes casillas obligatoriamente:**
* **[X] Users must provide a justification to remove a label or lower-classification label:** Esto activa el *Justification Requirement*.
* **[X] Require users to apply a label to their emails and documents:** Esto activa el *Mandatory Labeling* (Etiquetado obligatorio).


* Hacé clic en **Next**.


7. **Etiqueta por Defecto (Default Label):**
* El asistente te preguntará si querés que los documentos arranquen con una etiqueta predeterminada. Seleccioná **None** (Ninguna) para obligar al usuario a elegir activamente. Hacé clic en **Next**.


8. **Nombre de la Política:**
* **Name:** `Pol-Seguridad-Financiera`
* **Description:** `Política corporativa para control y obligatoriedad de etiquetas confidenciales.`
* Hacé clic en **Next**.


9. **Finalizar:**
* Revisá que todo esté correcto y hacé clic en **Submit** (Enviar). Luego hacé clic en **Done**.



---

### Parte 3: Verificación del Caso de Uso (Puesta a Prueba)

*Nota: Las políticas de Purview pueden demorar desde 1 hora hasta 24 horas en replicarse por completo en las aplicaciones de escritorio. Para acelerar la prueba, utilizaremos las versiones web de Microsoft 365.*

1. Iniciá sesión con la cuenta de un usuario de tu empresa en **`https://www.office.com`**.
2. Abrí la aplicación **Word** (versión web) y creá un **Nuevo documento en blanco**.
3. Escribí cualquier texto en la hoja (ej. *"Balance de ganancias Q2"*).
4. Intentá cerrar la pestaña del navegador o hacer clic en "Guardar como".
* **Resultado Esperado (Mandatory Labeling):** El sistema bloqueará la acción y te mostrará una alerta en pantalla impidiéndote guardar el documento hasta que selecciones una etiqueta de sensibilidad.


5. En la barra de herramientas superior de Word, buscá el botón **Sensitivity** (Sensibilidad), hacé clic en él y seleccioná **Altamente Confidencial**.
* **Resultado Esperado (Content Marking):** De inmediato notarás cómo aparece la marca de agua gris en diagonal detrás de tu texto diciendo `PROPIEDAD DE GLOBAL FINANCE`. El metadato quedó guardado en el archivo (*Sensitivity Label*).


6. Ahora, intentá cambiar la etiqueta del documento seleccionando una categoría inferior (si existiera) o intentando quitar la etiqueta actual haciendo clic de nuevo sobre ella para destildarla.
* **Resultado Esperado (Justification Requirement):** Word abrirá un cuadro de diálogo emergente bloqueando la pantalla. Te obligará a seleccionar una opción (ej: *"La etiqueta anterior ya no aplica"*) o escribir un texto explicando los motivos antes de permitirte remover la protección.



---

## 📊 Cuadro de Validación Teórica para el Alumno

Para confirmar que el laboratorio se comprendió correctamente, el alumno debe mapear lo realizado con los conceptos del examen:

| Lo que viste en la pantalla | Concepto Técnico Asociado |
| --- | --- |
| La marca de agua cruzada gris de fondo en el Word. | **Content Marking** |
| El bloqueo de Word que no te dejaba guardar el archivo nuevo. | **Mandatory Labeling** |
| El cartel que te obligó a dar una explicación al intentar quitar el sello. | **Justification Requirement** |
| El contenedor que usamos en la parte 2 para distribuir la regla a toda la empresa. | **Label Policies** |
| El metadato oculto que se asocia al documento de manera permanente. | **Sensitivity Labels** |
