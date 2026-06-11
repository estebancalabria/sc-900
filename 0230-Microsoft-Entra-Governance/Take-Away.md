# Take Away

## Identity Protection

* Microsoft Entra ID Identity Protection permite automatizar la detección y remediación de riesgos basados en la identidad, investigar vulnerabilidades o sospechas relacionadas con la autenticación de los usuarios y exportar los datos de detección de riesgos hacia herramientas o utilidades de terceros (como sistemas SIEM) para su posterior análisis.
 * Azure Portal -> Entra ID -> Security -> Protect -> Identity Protection

## Entitlement Management 

* Microsoft Entra ID Governance utiliza las revisiones de acceso (access reviews) para auditar periódicamente los permisos vigentes y la administración de derechos (entitlement management) para automatizar la asignación, el ciclo de vida y la expiración del acceso a los recursos.
  * Access Reviews
    * Portal de Azure : Microsoft Entra -> Identity Governance -> Access Reviews
    * entra.microsoft.com : ID Gobernande -> Access Reviews
  * Entitlement Management
    * Portal de Azure  : Microsoft Entra -> Identity Governance -> Entitlement Management
    * entra.microsoft.com : ID Gobernande ->  Entitlement Management

---

Cuando un usuario externo que obtuvo acceso a través de un paquete de administración de derechos (entitlement management) pierde todas sus asignaciones válidas, el sistema puede configurarse para asegurar que sea eliminado automáticamente del directorio para mitigar la acumulación de cuentas huérfanas o inactivas.

## Terms of USe

* **Terms of Use (Términos de uso)**
  * Los Términos de Uso permiten a las organizaciones asegurarse de que los usuarios acepten los avisos legales o requisitos de cumplimiento antes de acceder a los recursos, y aunque se **crean y administran** dentro del área de Gobernanza, se **obligan (enforce)** aplicando una política de **Acceso Condicional**.
  * **Ruta de Creación:**
    * **Portal de Azure:** Microsoft Entra $\rightarrow$ Identity Governance $\rightarrow$ Terms of use
    * **entra.microsoft.com:** ID Governance $\rightarrow$ Terms of use
  * **Ruta de Obligación (Enforcement):**
    * **Portal de Azure:** Microsoft Entra $\rightarrow$ Protection $\rightarrow$ Conditional Access $\rightarrow$ Policies (Se asocia dentro del control de otorgamiento o *Grant controls*).
    * **entra.microsoft.com:** Protection $\rightarrow$ Conditional Access $\rightarrow$ Policies
---

## User Provisioning

* El User Provisioning es el proceso automático que toma las identidades de Microsoft Entra ID y se encarga de crear, actualizar y borrar sus cuentas en las aplicaciones externas (como Slack) registradas en Enterprise Applications, eliminando la gestión manual del ciclo de vida del usuario.

---

## Condifional Access

* Formas de Acceso MFA
  * Métodos Estándar (Los tradicionales) :Son las formas de MFA más comunes, aunque hoy en día se consideran vulnerables a ataques de phishing avanzados:
       * Microsoft Authenticator (Notificación Push clásica): Le llega una alerta a la app del celular del usuario donde solo tiene que tocar "Aprobar" o ingresar el número que ve en la pantalla de la computadora.
       * Código de verificación (OTP) desde app de autenticación: El código de 6 dígitos que cambia cada 30 segundos, generado por Microsoft Authenticator, Google Authenticator o similares.
       * Mensaje de texto (SMS): Un código numérico enviado por línea telefónica al celular registrado del usuario.
       * Llamada de voz: El sistema llama al teléfono del usuario y este debe presionar la tecla numeral (#) para confirmar su identidad.
   * Métodos Phishing-Resistant (Resistentes a Phishing) : Estas son las formas de MFA más seguras y modernas. Las directivas de Acceso Condicional te permiten exigir específicamente que el usuario use uno de estos métodos si intenta entrar a recursos ultra críticos (como cuentas de administradores):
     * Windows Hello for Business: Autenticación biométrica (reconocimiento facial o huella dactilar) o PIN seguro del dispositivo, ligado directamente al chip TPM de la computadora del usuario.
     * Claves de seguridad FIDO2 (Llaves físicas): Dispositivos de hardware USB o NFC (como las llaves YubiKey) que requieren que el usuario las conecte y las toque físicamente para iniciar sesión.
      * Autenticación basada en certificados (CBA): El usuario valida su identidad utilizando un certificado digital criptográfico instalado en su máquina o en una tarjeta inteligente (Smart Card).

---

Los Session controls en Conditional Access permiten controlar lo que el usuario puede hacer dentro de la sesión una vez que ya autenticó. Por ejemplo: permitir el acceso pero bloquear la descarga de archivos si el dispositivo no es corporativo.

## General

* Microsoft Entra ID Governance y PIM protegen los accesos privilegiados a recursos de Azure y estructuran revisiones de acceso secuenciales en varias etapas, mientras que el aprovisionamiento automatiza el ciclo de vida de las cuentas en aplicaciones externas y las condiciones de uso se exigen mediante políticas de acceso directo en lugar de reglas de grupos dinámicos.

---

* Las características de gobernanza de identidades en Microsoft Entra permiten condicionar los términos de uso según los roles asignados y programar revisiones de acceso trimestrales de forma recurrente, mientras que la gestión de derechos (Entitlement Management) extiende su alcance a usuarios externos y PIM se limita a mitigar la persistencia de privilegios elevados en lugar de remover accesos estándar.

---

* Como solución de gestión de infraestructura de derechos de identidad (CIEM), Microsoft Entra Permissions Management ofrece compatibilidad nativa con entornos multicloud (como Azure, AWS y GCP) para proporcionar visibilidad integral y remediación sobre accesos no utilizados o con excesivos privilegios.
