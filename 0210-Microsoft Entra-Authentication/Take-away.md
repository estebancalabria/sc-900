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

* Para extender las capacidades de protección de contraseñas globales y las listas de exclusión de Microsoft Entra a los restablecimientos realizados de forma nativa en el entorno local, se requiere integrar Active Directory on-premises con **Microsoft Entra password protection** mediante el despliegue de sus agentes de dominio correspondientes.
 * https://learn.microsoft.com/en-us/entra/identity/authentication/howto-password-ban-bad-on-premises-deploy
 * https://www.microsoft.com/en-us/download/details.aspx?id=57071

---

* La administración integral de Microsoft Intune, incluyendo el despliegue de aplicaciones, la configuración de políticas de cumplimiento y la gestión del ciclo de vida de los dispositivos móviles y de escritorio, se realiza de forma centralizada a través del portal de Microsoft Endpoint Manager admin center (actualmente denominado centro de administración de Microsoft Intune).

---

* Microsoft Defender for Identity protege entornos híbridos analizando de manera continua las señales y la autenticación de los servicios de directorio para identificar vectores de ataque basados en identidades, especializándose en la detección de movimientos laterales ejecutados por ciberdelincuentes y en el descubrimiento de actividades internas maliciosas (malicious insider activity).

---

* Las capacidades de colaboración de Azure Active Directory (Azure AD) B2B permiten federar el acceso de usuarios externos provenientes de organizaciones socias, integrándolos de forma controlada como usuarios invitados (guest users) dentro del directorio corporativo sin necesidad de administrar sus credenciales locales.

---

* La implementación de identidades híbridas se realiza mediante herramientas de sincronización como Azure AD Connect para integrar los servicios locales de AD DS con Azure AD bajo un mismo tenant de organización, descartando la necesidad de desplegar múltiples inquilinos de Microsoft 365.

---

* Hello for Business: los datos biométricos del usuario empleados para la autenticación se almacenan únicamente en el dispositivo local (protegidos por el chip TPM) y nunca se envían a la nube ni a servidores externos.

---

* La autenticación de paso de Microsoft Entra (Entra ID Pass-through authentication) es un método de autenticación híbrido que permite a los usuarios iniciar sesión en servicios en la nube utilizando el mismo nombre de usuario y contraseña que manejan en su Active Directory local. Al implementarse mediante agentes ligeros locales, las solicitudes de validación de credenciales se envían y validan directamente contra los controladores de dominio locales en tiempo real.

## MFA

* Azure Multi-Factor Authentication (MFA) admite la validación de identidad a través de mensajes de texto (SMS), la aplicación móvil Microsoft Authenticator y llamadas telefónicas automatizadas, excluyendo de los factores nativos de segundo paso a las preguntas de seguridad o la verificación por correo electrónico estándar para inicios de sesión tradicionales de usuarios.
