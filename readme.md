# 🛡️ Sentinel Code Guardian
### Auditor de Seguridad Zero-Trust & Suite de Ciberseguridad

![Sentinel Banner](https://via.placeholder.com/1200x300/0f172a/38bdf8?text=SENTINEL+CODE+GUARDIAN)

[![Antigravity](https://img.shields.io/badge/Platform-Google_Antigravity-4285F4?style=for-the-badge&logo=google)](https://labs.google/)
[![Security](https://img.shields.io/badge/Security-OWASP_Top_10-red?style=for-the-badge&logo=owasp)](https://owasp.org/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](./LICENSE)

> **Auditoría Estática** • **Cálculo de Riesgo (IxPxE)** • **Simulación Red/Blue Team** • **Reportes de Compliance**

---

## 📖 Visión General

**Sentinel Code Guardian** es un flujo de trabajo (Workflow) avanzado diseñado para **Google Antigravity IDE**. Transforma al agente de IA nativo en un **Ingeniero de Seguridad Senior** capaz de realizar auditorías de código en tiempo real, detectar vulnerabilidades críticas y simular ataques para validar la robustez del software.

A diferencia de un linter tradicional, Sentinel utiliza un **Sandbox Mental** que simula herramientas de análisis estático (SAST) para evaluar patrones de inyección, secretos hardcodeados y vulnerabilidades de infraestructura bajo una doctrina de **Zero Trust**.

---

## 🚀 Características Principales

| Módulo | Descripción |
| :--- | :--- |
| **🔐 Escáner de Secretos** | Detecta y censura API Keys, Tokens AWS y Claves Privadas antes de que lleguen al commit. |
| **💉 Detección de Inyecciones** | Análisis heurístico de **XSS** y **SQL Injection** (concatenación de strings). |
| **🧮 Modelo de Riesgo** | Clasificación matemática de vulnerabilidades: **Impacto × Probabilidad × Exposición**. |
| **⚔️ Modo Wargame** | Simulación adversarial: **Red Team** genera un exploit real vs **Blue Team** que genera el parche. |
| **📄 Persistencia** | Generación automática de reportes físicos (`.md`) en `security_reports/` para auditorías. |

---

## 🛠️ Instalación e Integración

Sentinel se instala como un **Global Workflow** en Antigravity.

### Pasos de Configuración:

1. Abre **Google Antigravity IDE**.
2. Ve al menú **Customizations** -> **Workflows**.
3. Haz clic en **`+ Global`**.
4. Rellena los campos así:

| Campo | Valor |
| :--- | :--- |
| **Name** | `sentinel` |
| **Description** | `Suite de Seguridad completa: Auditoría OWASP, Validación CVE y Wargames.` |
| **Prompt** | [Copiar el Prompt Maestro desde workflow_prompt.md](./workflow_prompt.md) |

---

## 💻 Guía de Uso (Cheat Sheet)

Una vez instalado, invoca a Sentinel desde el chat usando el comando `/sentinel`.

### 1. Auditoría Estándar
Analiza el archivo abierto actualmente o el código seleccionado.

```bash
/sentinel
```

### 2. Simulación de Ataque (Wargame)
Inicia una batalla simulada para entender cómo un atacante rompería tu código. Muestra el Payload y la Defensa.

```bash
/sentinel --wargame
```

### 3. Reparación Automática
Solicita una reescritura del código inseguro aplicando patrones de diseño seguros.

```bash
/sentinel fix
```

### 4. Generación de Reporte Físico
Fuerza la creación de un archivo de evidencia en la carpeta `security_reports/`.

```bash
/sentinel audit
```

---

## 📊 Modelo de Riesgo (Risk Score)

Sentinel calcula la severidad usando la fórmula:

**Score = Impacto × Probabilidad × Exposición**

| Score | Nivel | Acción Requerida |
| :--- | :--- | :--- |
| **18 - 27** | 🚨 **CRÍTICA** | **BLOQUEANTE.** Arreglo inmediato. No desplegar. |
| **12 - 17** | 🔴 **ALTA** | Debe arreglarse antes del release. |
| **06 - 11** | 🟠 **MEDIA** | Agendar para próximo sprint. |
| **01 - 05** | 🟢 **BAJA** | Deuda técnica / Mejora opcional. |

---

## 📂 Estructura del Repositorio

Este repositorio contiene el código fuente Python que alimenta la lógica del agente:

```text
.
├── agent.json               # Definición base del Agente
├── workflow_prompt.md       # ⚠️ PROMPT MAESTRO (Instalar este)
├── mission.md               # Directivas de Misión
├── rules.md                 # Reglas Operativas
├── tools/                   # Lógica Fuente
│   ├── scan_for_secrets.py  # Regex para credenciales
│   ├── scan_for_injections.py # Heurística XSS/SQLi
│   ├── scan_for_os_vulns.py # Detección RCE
│   └── score_risks.py       # Algoritmo de Scoring
└── .context/                # Base de Conocimiento
    ├── risk_model.md        # Definición matemática de riesgo
    └── security_principles.md # Principios Zero Trust
```

---

## ⚠️ Disclaimer

**Sentinel Code Guardian** es una herramienta de asistencia basada en IA. No reemplaza una auditoría humana certificada. El usuario es el responsable final del código desplegado en producción.

---

## 👨‍💻 Autor y Créditos

**Desarrollado y mantenido por:**
**Fran Kloster**
**Rol:** Developer & Cybersecurity Analyst