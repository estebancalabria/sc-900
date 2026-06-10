# Take Away

Microsoft Sentinel automatiza el manejo de incidentes a través de reglas de automatización (automation rules), las cuales se encargan de ejecutar libros de respuestas o estrategias predefinidas (playbooks) para orquestar acciones específicas de mitigación ante amenazas.

<img width="2377" height="1474" alt="image" src="https://github.com/user-attachments/assets/b32cb347-4735-48b0-9062-4100537c7ad9" />

---

* Microsoft Sentinel optimiza las operaciones de seguridad al mitigar los tiempos de detección y respuesta mediante la ejecución automatizada de flujos de trabajo de remediación (Security playbooks basados en Logic Apps) y capacidades analíticas de búsqueda proactiva de amenazas (Proactive threat hunting).

---

* Las capacidades operativas de Microsoft Sentinel permiten automatizar respuestas con flujos basados en Logic Apps (Playbooks), buscar amenazas de forma proactiva (Hunts), normalizar logs heterogéneos mediante ASIM (Advanced Security Information Model) e integrar paquetes listos para usar desde el Content hub.

---

* Microsoft Sentinel utiliza los libros de trabajo (Workbooks) para ofrecer capacidades avanzadas de visualización de datos y paneles interactivos, y las listas de seguimiento (Watchlists) para enriquecer la detección de amenazas mediante la correlación con fuentes de datos externas o indicadores personalizados.

---

* Microsoft Sentinel funciona como una plataforma SIEM/SOAR capaz de centralizar e ingestar telemetría híbrida o multicloud proveniente de AWS, GCP y entornos locales, ofreciendo tableros interactivos mediante Workbooks para la visualización de tendencias y permitiendo estructurar estrategias de remediación semiautomatizadas donde los analistas validan las acciones de los Playbooks antes de su ejecución operativa.

---

Para conectar cualquier fuente de datos (ya sea de Microsoft como Defender, o de terceros como Firewalls Fortinet, AWS CloudTrail, etc.) hacia Microsoft Sentinel en tiempo real, se utilizan los Data Connectors (conectores de datos) integrados en la plataforma. El Log Analytics Workspace es donde se almacenan los datos, pero la herramienta de integración propiamente dicha es el conector.
