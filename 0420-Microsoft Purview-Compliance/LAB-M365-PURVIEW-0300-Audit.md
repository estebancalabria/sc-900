# LAB-M365-PurView-0300-Audit
## Microsoft Purview — Audit (Core y Advanced)

---

### Objetivo

Explorar el portal de Microsoft Purview para entender cómo funciona la auditoría de actividad en Microsoft 365: qué registra, cómo se busca y qué diferencia hay entre Core Audit y Advanced Audit.

---

### Requisitos previos

- Acceso a un tenant de Microsoft 365 con permisos de administrador global o compliance administrator
- Si no tenés tenant: activar uno gratuito en **developer.microsoft.com/microsoft-365/dev-program**

---

### Parte 1 — Acceder al portal de auditoría

1. Abrí el navegador y andá a **purview.microsoft.com**
2. Iniciá sesión con tu cuenta de administrador
3. En el menú izquierdo buscá **Audit** y hacé clic

Si no ves Audit en el menú, andá a **Solutions → Audit**.

---

### Parte 2 — Verificar que la auditoría está habilitada

Al entrar por primera vez puede aparecer un banner que dice "Start recording user and admin activity".

1. Si aparece ese banner, hacé clic en **Turn on audit**
2. Esperá unos minutos hasta que el sistema confirme que está activo
3. La auditoría tarda hasta 60 minutos en empezar a registrar eventos después de habilitarse

---

### Parte 3 — Entender la interfaz de búsqueda

En la pantalla principal de Audit vas a ver estos campos:

- **Date range** — el rango de fechas a consultar (máximo 90 días en Core, hasta 10 años en Advanced)
- **Activities** — el tipo de evento que querés buscar (inicio de sesión, modificación de archivo, cambio de label, etc.)
- **Users** — podés filtrar por usuario específico o dejar vacío para todos
- **File, folder, or site** — filtro opcional por recurso específico

---

### Parte 4 — Hacer tu primera búsqueda

Vamos a buscar actividad de inicio de sesión:

1. En **Date range** seleccioná los últimos 7 días
2. En **Activities** escribí `signed in` y seleccioná **User logged in**
3. Dejá **Users** vacío para ver todos
4. Hacé clic en **Search**
5. Esperá que carguen los resultados

Vas a ver una lista de eventos con columnas: Date, User, Activity, Item, Detail.

---

### Parte 5 — Explorar el detalle de un evento

1. Hacé clic en cualquier fila de los resultados
2. Se abre un panel lateral con el detalle completo del evento
3. Observá los campos:
   - **ClientIP** — desde qué dirección IP se conectó el usuario
   - **UserAgent** — qué navegador o cliente usó
   - **ResultStatus** — si el login fue exitoso o falló
   - **Workload** — qué servicio de M365 generó el evento

---

### Parte 6 — Buscar actividad sobre archivos de SharePoint

1. Limpié la búsqueda anterior con **Clear**
2. En **Activities** escribí `downloaded file` y seleccioná **Downloaded file**
3. Definí un rango de fecha de los últimos 30 días
4. Hacé clic en **Search**
5. Si hay actividad, vas a ver qué usuarios descargaron archivos y desde qué sitios de SharePoint

---

### Parte 7 — Buscar eventos de sensitivity labels (Information Protection)

1. Limpié la búsqueda
2. En **Activities** buscá `sensitivity label` 
3. Vas a ver opciones como:
   - **Applied sensitivity label to file**
   - **Changed sensitivity label applied to file**
   - **Removed sensitivity label from file**
4. Seleccioná **Changed sensitivity label applied to file**
5. Ejecutá la búsqueda
6. Si hay resultados, podés investigar si alguien bajó la clasificación de un archivo (por ejemplo de Confidential a Internal)

---

### Parte 8 — Diferencia visual entre Core y Advanced Audit

Core Audit (licencia E3 o inferior):
- Retención de logs: **90 días**
- No incluye eventos como SearchQueryInitiatedExchange ni MailItemsAccessed

Advanced Audit (licencia E5 o add-on E5 Compliance):
- Retención de logs: **hasta 10 años** (requiere configurar retention policies)
- Agrega eventos de alto valor para investigaciones forenses

Para verificar qué licencia tiene tu tenant:
1. Andá a **admin.microsoft.com**
2. **Billing → Licenses**
3. Buscá si tenés **Microsoft 365 E5** o **Microsoft 365 E5 Compliance**

---

### Parte 9 — Exportar resultados

1. Ejecutá cualquier búsqueda que devuelva resultados
2. Hacé clic en **Export** (arriba a la derecha de los resultados)
3. Se descarga un archivo **.csv** con todos los eventos
4. Abrilo en Excel
5. Observá que cada fila es un evento y la columna **AuditData** contiene el JSON completo del evento con todos los campos técnicos

---

### Parte 10 — Crear una Audit Retention Policy (solo Advanced)

Si tenés licencia E5:

1. En el portal de Audit, hacé clic en **Audit retention policies**
2. Clic en **New audit retention policy**
3. Completá:
   - **Name**: Retention-ExchangeAudit-1Year
   - **Description**: Retención de eventos de Exchange por 1 año
   - **Workload**: Exchange
   - **Duration**: 1 year
4. Guardá la política

Esto garantiza que los logs de Exchange se conserven 1 año en lugar de los 90 días por defecto.

---

### Resumen

| Característica | Core Audit | Advanced Audit |
|---|---|---|
| Retención | 90 días | Hasta 10 años |
| Eventos básicos | ✅ | ✅ |
| MailItemsAccessed | ❌ | ✅ |
| SearchQueryInitiatedExchange | ❌ | ✅ |
| Retention policies | ❌ | ✅ |
| Licencia requerida | E3 | E5 o add-on |

---

### Fin del laboratorio
