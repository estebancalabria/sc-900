# Describe the authentication capabilities of Microsoft Entra ID

## Overview

This module explains the authentication capabilities of Microsoft Entra ID and how they improve organizational security. It focuses on modern authentication approaches that go beyond traditional passwords, helping organizations reduce risk in the face of increasingly sophisticated, AI-driven cyberattacks.

You will learn how Microsoft Entra ID supports a wide range of authentication methods, including password-based, phone-based, passwordless, phishing-resistant authentication, multifactor authentication (MFA), self-service password reset (SSPR), account recovery, and password protection and management capabilities.

---

## Introduction

Authentication is the process of verifying that an identity is legitimate before granting access to a resource, application, service, device, or network. It ensures users are who they claim to be during sign-in.

While passwords are still widely used, they are no longer sufficient on their own due to modern threats such as AI-driven cyberattacks and credential theft. Organizations increasingly adopt stronger authentication methods that go beyond passwords.

To address this, Microsoft Entra ID provides a comprehensive set of authentication capabilities that include traditional methods, modern passwordless approaches, multifactor authentication, self-service password reset, account recovery, and password protection mechanisms.

---

## Describe authentication methods

### Passwords

Passwords are the most common authentication method, but they are also one of the weakest when used alone. Weak or reused passwords are easily compromised, while strong passwords are difficult to remember and manage.

For this reason, passwords should be supplemented or replaced with stronger authentication methods available in Microsoft Entra ID, ideally moving toward passwordless authentication.

---

### Phone-based authentication

Microsoft Entra ID supports:

* SMS-based authentication (verification codes via text message)
* Voice call verification (automated call confirmation)

These methods are mainly used as secondary factors and are less secure than modern phishing-resistant options.

---

### OATH authentication

OATH (Open Authentication) uses time-based one-time passwords:

* Software OATH tokens (e.g., Microsoft Authenticator)
* Hardware OATH tokens (physical devices)

These are used for MFA and SSPR as secondary authentication methods.

---

### Other authentication methods

Additional supported methods include:

* Temporary Access Pass (TAP)
* QR code authentication
* Email one-time passcode (OTP)
* Platform Credential for macOS
* Authenticator Lite (embedded MFA in apps like Outlook)
* External authentication providers

---

### Passwordless authentication

Passwordless authentication replaces passwords with cryptographic or biometric methods:

* Windows Hello for Business (device-bound credentials with PIN/biometrics)
* Passkeys (FIDO2), including device-bound and synced passkeys
* Microsoft Authenticator passwordless sign-in
* Certificate-based authentication (CBA)

These methods are strongly resistant to phishing and credential theft.

---

### Phishing-resistant authentication

The most secure methods are those bound to trusted domains using public key cryptography:

* Windows Hello for Business
* Platform Credential for macOS
* Passkeys (FIDO2 and Microsoft Authenticator)
* Certificate-based authentication (CBA)

These prevent reuse on fraudulent websites.

---

### Primary vs secondary authentication

* Primary methods: Password, Windows Hello, Passkeys, TAP, QR code
* Secondary methods: SMS, voice call, OATH tokens, Authenticator push, email OTP

---

## Describe multifactor authentication

Multifactor authentication (MFA) requires users to provide two or more verification factors during sign-in.

### Authentication factors

* Something you know (password or PIN)
* Something you have (device or security key)
* Something you are (biometrics)

Microsoft Entra ID handles MFA automatically during sign-in without requiring application changes.

### Supported MFA methods

* Microsoft Authenticator
* Authenticator Lite
* Windows Hello for Business
* Passkeys (FIDO2)
* Certificate-based authentication (CBA)
* Temporary Access Pass (TAP)
* OATH tokens
* SMS and voice call
* External authentication methods

---

### Security defaults

Security defaults provide baseline protection by:

* Requiring MFA for all users and administrators
* Blocking legacy authentication
* Protecting privileged access
* Enforcing MFA registration

They are enabled by default in new tenants and help protect against most identity-based attacks.

---

### Conditional Access

Conditional Access allows granular MFA enforcement based on:

* Location
* Device state
* Risk level
* Application sensitivity

Requires Microsoft Entra ID P1/P2 licensing.

---

## Describe self-service password reset (SSPR)

Self-service password reset (SSPR) allows users to reset or change their password without contacting IT support.

### How SSPR works

When a user accesses the SSPR portal, Microsoft Entra ID performs validation:

* Confirms account is valid and SSPR is enabled
* Verifies required authentication methods are registered
* Determines password management location

If checks pass, the user can reset or change their password.

---

### Requirements

Users must:

* Have a Microsoft Entra ID license
* Be enabled for SSPR
* Register authentication methods (2 recommended)

---

### Authentication methods for SSPR

* Microsoft Authenticator push notifications
* Software OATH tokens
* Hardware OATH tokens (preview)
* SMS
* Voice call
* Email OTP
* Security questions (retiring March 2027)

---

### Configuration

* Admins define whether 1 or 2 methods are required
* Admin accounts require 2 methods and cannot use security questions
* Authenticator may provide code-only or notification-based verification depending on policy

---

### Registration and notifications

* Users may be forced to register at sign-in
* Reconfirmation can be required every 0–730 days
* Email notifications are sent after password resets
* Admins are notified when another admin resets their password

---

### On-premises integration

In hybrid environments, password changes can be written back to on-premises Active Directory using Microsoft Entra Connect cloud sync:

* Password writeback supported for federated/PHS/PTA users
* Account unlock without reset supported
* No AD schema changes required
* Domain controllers do not need internet access

---

### Account recovery

SSPR works only if users retain at least one method. If all are lost, account recovery is required.

* **SSPR**: user still has at least one method
* **Account recovery**: all methods lost

Account recovery uses Microsoft Entra Verified ID with Face Check and Azure AI to verify identity without preregistered methods, reducing helpdesk dependency and improving security in full lockout scenarios.

---

## Describe password protection and management capabilities

Password protection in Microsoft Entra ID reduces the risk of weak passwords by blocking known bad choices and enforcing strong password policies.

---

### Global banned password list

* Automatically applied to all tenants
* Maintained by Microsoft based on real attack telemetry
* Includes commonly used weak or compromised passwords
* Cannot be disabled or configured

This list is continuously updated using real-world password spray attack data and security analysis.

---

### Custom banned password list

Organizations can add up to 1,000 custom terms such as:

* Company names
* Products
* Locations
* Internal terms
* Abbreviations

Custom terms are combined with the global list and evaluated together. The system blocks weak variants, not just exact matches.

---

### How passwords are evaluated

When a password is changed or reset:

1. **Normalization**: lowercase conversion and character substitution (e.g., @→a, 0→o)
2. **Fuzzy matching**: detects variations within edit distance of 1
3. **Substring matching**: blocks names of users or tenant (≥4 characters)
4. **Score calculation**: password must reach minimum strength score (≥5)

Longer passwords may still be accepted even if they contain weak terms, provided overall strength is sufficient.

---

### Protection against password spray attacks

Password spray attacks attempt a small number of common passwords across many accounts.

Microsoft Entra ID mitigates this by:

* Blocking known weak passwords
* Using telemetry-driven banned password lists
* Detecting variations of common passwords

---

### On-premises integration

Password protection extends to Active Directory Domain Services using:

* **Proxy service**: forwards policy requests to Microsoft Entra ID
* **DC Agent**: enforces password validation on domain controllers

Key characteristics:

* Same global and custom banned lists applied on-premises
* Domain controllers do not require internet access
* No schema changes required
* Policies updated hourly

Password protection supplements AD DS password policies; both must agree for password acceptance.

---

## Summary

Microsoft Entra ID provides a complete authentication and identity security framework that includes:

* Multiple authentication methods (password, phone, passwordless, phishing-resistant)
* Multifactor authentication (MFA)
* Self-service password reset (SSPR)
* Account recovery using Verified ID
* Password protection and management with global and custom banned password lists
