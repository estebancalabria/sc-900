# Take Away

<img width="713" height="404" alt="image" src="https://github.com/user-attachments/assets/22b37404-b980-4362-b9ee-598e49395fb4" />

> https://purview.microsoft.com/

---

* Microsoft protege la privacidad de los datos de sus clientes mediante el análisis riguroso de las solicitudes gubernamentales (government requests), rechazando cualquier tipo de acceso irrestricto (unfettered access) y garantizando el envío de notificaciones (notifications) a los usuarios afectados, a menos que exista una prohibición legal explícita.

---

* Para recopilar manualmente los registros de auditoría de correo electrónico relacionados con un incidente de Exchange sin depender de la interfaz gráfica (GUI), un analista de seguridad debe utilizar el cmdlet de PowerShell Search-UnifiedAuditLog.

---

* Los principios de privacidad de Microsoft prohíben el uso del contenido del cliente para segmentación publicitaria, mientras que sus etiquetas de sensibilidad se extienden a chats y reuniones de Teams, diferenciándose conceptualmente las cartas puente (bridge letters) cuya función es cubrir brechas temporales de certificación y no reemplazar reportes de auditoría obsoletos.

---

# Roles

* **Data Steward (Encargado de datos)**
    * **Función principal:** Es el responsable operativo de la calidad, el significado y la gobernanza de los datos en el día a día.
    * **Qué hace:**
    * Mantiene la consistencia del Glosario de Negocio (*Business Glossary*) definiendo los términos de la empresa.
    * Asegura el descubrimiento de datos clasificando y etiquetando correctamente los activos.
    

* **Data Curator (Curador de datos)**
    * **Función principal:** Es el rol técnico real en la consola que le da los permisos al Data Steward para poder editar.
    * **Qué hace:**
        * Crea, edita y borra términos dentro del catálogo de datos.
        * Asocia esquemas, clasificaciones y etiquetas de sensibilidad a los activos de datos que ya fueron escaneados.
        
* **Data Reader (Lector de datos)**
    * **Función principal:** Es el rol de consulta para los usuarios finales o analistas que solo necesitan buscar información.
    * **Qué hace:**
        * Tiene acceso de "solo lectura" al catálogo de datos.
        * Puede buscar e interactuar con el buscador para descubrir qué datos existen, pero no puede modificar el glosario ni cambiar clasificaciones.

* **Data Source Administrator (Administrador de fuentes de datos)**
    * **Función principal:** Es el rol de infraestructura, el encargado de conectar los cables entre los servidores y Purview.
    * **Qué hace:**
        * Registra las fuentes de datos (como bases de datos SQL, cuentas de Azure Storage, o entornos de Fabric).
        * Configura y programa los escaneos (*scans*) automáticos para que Purview absorba los metadatos de esos sistemas.
        
* **Purview Administrator / Tenant Admin (Administrador de Purview)**
    * **Función principal:** Es el dueño absoluto de la herramienta a nivel global.
    * **Qué hace:**
        * Gestiona la configuración general de toda la cuenta de Purview.
        * Asigna los roles nombrados anteriormente a los distintos usuarios del equipo.
