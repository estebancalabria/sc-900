# Take Aways

* Para permitir que los usuarios accedan a recursos locales y de la nube con una identidad única mediante la sincronización y aprovisionamiento de cuentas desde un Active Directory local, la herramienta recomendada es Microsoft Entra Cloud Sync.
  * https://learn.microsoft.com/es-es/entra/identity/hybrid/cloud-sync/what-is-cloud-sync

---

* La aplicación Microsoft Authenticator es el método de autenticación multifactor (MFA) que admite de forma simultánea el envío de notificaciones de inserción (push) y la generación de códigos de un solo uso basados en el tiempo (TOTP).

---

* El modelo de control de acceso de Microsoft Entra asigna automáticamente el rol de Administrador Global a quien crea el inquilino (tenant), ofrece roles integrados específicos de servicios (como el de Exchange) y permite asignar roles personalizados tanto a usuarios individuales como a grupos de seguridad, extendiendo el alcance de ciertos roles de administración más allá de Entra (como en Purview o Microsoft 365).


---

* Las listas de contraseñas prohibidas personalizadas en Microsoft Entra permiten añadir términos específicos de la organización (como marcas y ubicaciones) y bloquean automáticamente las variantes comunes de dichas palabras para robustecer la seguridad en el proceso de autenticación.
  * Portal de Azure : Microsoft Entra -> Security -> Manage -> Authentication Methods -> Password Protection -> Password Protection
  * https://entra.microsoft.com/ ->  Authentication Methods -> Password Protection -> Password Protection

---

