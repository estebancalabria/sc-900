### 🧭 Introducción — Microsoft Entra Security Model

La seguridad moderna ha evolucionado desde un **perímetro de red tradicional** hacia un modelo centrado en **identidades** (usuarios, dispositivos y servicios). Esto ocurre porque las aplicaciones y los datos se han trasladado a la nube y la IA está ampliando cómo se accede a los recursos.

Este escenario impulsa un enfoque de **Zero Trust**, donde nunca se confía por defecto y siempre se verifica explícitamente.

---

# 🔐 Conditional Access (Microsoft Entra)

Conditional Access es el motor de políticas Zero Trust de Microsoft Entra ID.

Permite aplicar **políticas de seguridad antes de conceder acceso**, incluso después de la autenticación.

## 🧠 Modelo IF–THEN

* IF el usuario intenta acceder a un recurso
* THEN debe cumplir condiciones adicionales (ej. MFA)

📌 Claves:

* Se aplica **después del primer factor de autenticación**
* No es defensa primaria contra ataques DoS
* Usa señales de identidad, dispositivo, red y riesgo

---

## 🧩 Componentes de una política

### 1) Assignments (quién, qué, dónde, cuándo)

Se combinan con lógica **AND**:

* 👤 Usuarios: usuarios, grupos, roles, invitados y workloads (IA)
* 🎯 Recursos: apps, Microsoft 365, acciones, tráfico de red
* 🌐 Red: IPs confiables, ubicaciones, redes corporativas
* ⚠️ Condiciones:

  * Riesgo de inicio de sesión o usuario (Microsoft Entra ID Protection)
  * Riesgo interno (Microsoft Purview)
  * Plataforma, cliente y filtros de dispositivos

---

### 2) Access Controls

* 🔴 Block access
* 🟢 Grant access:

  * MFA
  * Authentication strength
  * Dispositivo compliant
  * Hybrid joined
  * App aprobada
* 🧾 Session controls:

  * Control de descargas, copia, impresión
  * Sign-in frequency
  * Restricciones de app

---

## 🔑 Authentication Strengths

Definen métodos de autenticación permitidos:

* MFA strength (password + segundo factor)
* Passwordless MFA (FIDO2, Authenticator, Windows Hello)
* Phishing-resistant MFA (FIDO2, certificados, Windows Hello)

---

## 🤖 Protección de IA

Conditional Access permite proteger servicios como Copilot:

* MFA resistente a phishing
* Dispositivos compliant según riesgo
* Bloqueo por alto riesgo

---

# 🌐 Global Secure Access

Global Secure Access es la solución SSE de Microsoft basada en Zero Trust:

* Verificar explícitamente
* Aplicar mínimo privilegio
* Asumir brecha

Integra:

* Internet Access
* Microsoft Services Access
* Private Access
* Defender for Cloud Apps

---

## 🎯 Capacidades clave

* Reduce movimiento lateral (VPN comprometidas)
* Protege accesos a internet y SaaS
* Mejora conectividad remota

---

## 🌍 Componentes

### Internet Access

Microsoft Entra Internet Access

* Filtrado web
* Conditional Access universal
* Continuous Access Evaluation (CAE)

### Microsoft Services Access

Microsoft Entra Internet Access for Microsoft Services

* Compliant network check
* Tenant restrictions
* Restauración de IP
* Logs mejorados

### Private Access

Microsoft Entra Private Access

* Reemplaza VPN (ZTNA)
* Acceso por aplicación
* Modelos:

  * Quick Access
  * Per-app Access

---

## 📊 Gestión y seguridad

* Dashboard en Entra Admin Center
* Monitoreo de tráfico, usuarios y dispositivos
* Detección de actividad sospechosa

---

# 👤 Microsoft Entra Roles y RBAC

Role-Based Access Control es el modelo que controla **quién puede administrar qué recursos en Microsoft Entra**.

---

## 🧠 Concepto clave

* Roles = conjunto de permisos
* RBAC = asignar roles a usuarios/grupos
* Controla acceso a recursos de Entra (usuarios, apps, grupos)

---

## 🧱 Built-in roles

Roles predefinidos con permisos fijos:

* 👑 Global Administrator: acceso total al tenant
* 👥 User Administrator: gestiona usuarios y grupos
* 💳 Billing Administrator: compras y suscripciones

📌 No se pueden modificar

---

## 🛠️ Custom roles

Permiten definir roles personalizados:

1. Crear definición de rol (permisos seleccionados)
2. Asignar el rol a usuarios o grupos

📌 Incluyen:

* Scope (alcance):

  * Organización completa
  * Aplicación específica

📌 Requiere Microsoft Entra ID P1 o P2

---

## 🧭 Principio de mínimo privilegio

* Dar solo los permisos necesarios
* Reducir impacto de cuentas comprometidas
* Crítico en entornos con IA

👉 También limita riesgos de herramientas de IA que operen con credenciales excesivas.

---

## 🧩 Tipos de roles

* 🔵 Entra-specific roles: usuarios, grupos, apps
* 🟡 Service-specific roles: Exchange, Teams, Intune, SharePoint
* 🟣 Cross-service roles: Security Admin, Compliance Admin

---

## 🔄 Entra RBAC vs Azure RBAC

* **Microsoft Entra RBAC**:

  * Controla recursos de identidad (usuarios, apps, grupos)

* **Azure RBAC**:

  * Controla recursos de Azure (VMs, storage, redes)

📌 Son sistemas distintos aunque comparten el concepto RBAC.

---

# 🎯 Idea final

Conditional Access, Global Secure Access y Role-Based Access Control forman juntos la base del modelo de seguridad moderno en Microsoft Entra:

* Conditional Access → decide **si se puede acceder**
* Global Secure Access → controla **por dónde se accede**
* RBAC → define **quién puede administrar qué**




