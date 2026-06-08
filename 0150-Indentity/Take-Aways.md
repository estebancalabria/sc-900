* Take Away Bullets

* La autenticación se encarga de verificar y demostrar la identidad de un usuario, mientras que la autorización define los permisos y las acciones específicas que ese usuario tiene permitido realizar una vez dentro del sistema.
* Los pilares de la identidad definen que una identidad puede representar usuarios, dispositivos o aplicaciones, donde la auditoría genera reportes de su uso, la administración gestiona su ciclo de vida (y no sus permisos post-autenticación), y el proceso técnico exige que la autenticación ocurra obligatoriamente antes de la autorización.


# Pilares Identidad

Los **4 pilares de la identidad** en el modelo de control de acceso y seguridad de Microsoft (especialmente detallados en la certificación SC-900) se conocen comúnmente en inglés como **"The Four A's"**.

Cada uno cubre una etapa o una necesidad específica dentro del ciclo de vida y control de una identidad:

---

### 1. Administración (Administration)

Es el pilar encargado de **gestionar el ciclo de vida** de todos los elementos del sistema.

* **Qué incluye:** La creación, edición, desactivación y eliminación de usuarios, grupos, dispositivos y aplicaciones.
* **Ejemplo:** Cuando un nuevo empleado ingresa a una empresa y el administrador de TI crea su cuenta de correo y lo asigna a un departamento en Microsoft Entra ID.

### 2. Autenticación (Authentication / AuthN)

Es el proceso que responde a la pregunta: **¿Quién eres?** Su único objetivo es **verificar la identidad** de un sujeto que intenta ingresar al sistema.

* **Cómo funciona:** El usuario o servicio debe demostrar su identidad mediante algo que sabe (contraseña), algo que tiene (un teléfono para recibir un código) o algo que es (su huella dactilar o reconocimiento facial).
* **Ejemplo:** El uso de **MFA** (Autenticación de Múltiples Factores) o Windows Hello para iniciar sesión.

### 3. Autorización (Authorization / AuthZ)

Una vez que el sistema ya sabe quién eres, este pilar responde a la pregunta: **¿Qué tienes permitido hacer?**

* **Cómo funciona:** Evalúa los permisos, roles y políticas asignadas a esa identidad ya autenticada para conceder o denegar el acceso a un recurso específico.
* **Ejemplo:** Determinar si un usuario puede editar una base de datos en Azure o si solo tiene permisos de lectura.

### 4. Auditoría (Auditing)

Es el pilar que se encarga del **seguimiento, la visibilidad y el control** de todo lo que ocurre en el entorno de identidades. Responde a la pregunta: **¿Qué hiciste y cuándo lo hiciste?**

* **Qué incluye:** El registro de inicios de sesión, el historial de cambios, la generación de **alertas de seguridad** ante comportamientos sospechosos y la creación de **reportes detallados** de uso.
* **Ejemplo:** Revisar los *Sign-in logs* para ver si hubo un intento de inicio de sesión fallido desde un país inusual.

---

> 🔒 **Regla de oro en examen:** El flujo lógico de seguridad dicta que la **Autenticación siempre ocurre antes que la Autorización**. Primero demuestras quién eres (AuthN) y luego el sistema verifica a qué tienes derecho a entrar (AuthZ).
