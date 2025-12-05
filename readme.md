# 🛡️ Sentinel Code Guardian
### Zero-Trust Security Auditor & Cybersecurity Suite

![Sentinel Banner](./assets/banner.png)

[![Antigravity](https://img.shields.io/badge/Platform-Google_Antigravity-4285F4?style=for-the-badge&logo=google)](https://labs.google/)
[![Security](https://img.shields.io/badge/Security-OWASP_Top_10-red?style=for-the-badge&logo=owasp)](https://owasp.org/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](./LICENSE)

> **Static Audit** • **Risk Scoring (IxPxE)** • **Red/Blue Team Simulation** • **Compliance Reports**

---

## 📖 Overview

**Sentinel Code Guardian** is an advanced Workflow designed for **Google Antigravity IDE**. It transforms the native AI agent into a **Senior Security Engineer** capable of performing real-time code audits, detecting critical vulnerabilities, and simulating attacks to validate software robustness.

Unlike a traditional linter, Sentinel uses a **Mental Sandbox** that simulates static analysis tools (SAST) to evaluate injection patterns, hardcoded secrets, and infrastructure vulnerabilities under a **Zero Trust** doctrine.

---

## 🚀 Key Features

| Module | Description |
| :--- | :--- |
| **🔐 Secrets Scanner** | Detects and censors API Keys, AWS Tokens, and Private Keys before they reach the commit. |
| **💉 Injection Detection** | Heuristic analysis of **XSS** and **SQL Injection** (string concatenation). |
| **🧮 Risk Model** | Mathematical vulnerability classification: **Impact × Probability × Exposure**. |
| **⚔️ Wargame Mode** | Adversarial simulation: **Red Team** generates a real exploit vs. **Blue Team** generating the patch. |
| **📄 Persistence** | Automatic generation of physical reports (`.md`) in `security_reports/` for audits. |

---

## 🛠️ Installation & Integration

Sentinel is installed as a **Global Workflow** in Antigravity.

### Configuration Steps:

1. Open **Google Antigravity IDE**.
2. Go to the menu **Customizations** -> **Workflows**.
3. Click on **`+ Global`**.
4. Fill in the fields as follows:

| Field | Value |
| :--- | :--- |
| **Name** | `sentinel` |
| **Description** | `Complete Security Suite: OWASP Audit, CVE Validation, and Wargames.` |
| **Prompt** | [Copy the Master Prompt from sentinel-code-guardian.md](./sentinel-code-guardian.md) |

---

## 💻 Usage Guide (Cheat Sheet)

Once installed, invoke Sentinel from the chat using the `/sentinel` command.

### 1. Standard Audit
Analyzes the currently open file or selected code.

```bash
/sentinel
```

### 2. Attack Simulation (Wargame)
Starts a simulated battle to understand how an attacker would break your code. Displays the Payload and Defense.

```bash
/sentinel --wargame
```

### 3. Auto-Repair
Requests a rewrite of insecure code applying secure design patterns.

```bash
/sentinel fix
```

### 4. Generate Physical Report
Forces the creation of an evidence file in the `security_reports/` folder.

```bash
/sentinel audit
```

---

## 📊 Risk Model (Risk Score)

Sentinel calculates severity using the formula:

**Score = Impact × Probability × Exposure**

| Score | Level | Required Action |
| :--- | :--- | :--- |
| **18 - 27** | 🚨 **CRITICAL** | **BLOCKER.** Immediate fix. Do not deploy. |
| **12 - 17** | 🔴 **HIGH** | Must be fixed before release. |
| **06 - 11** | 🟠 **MEDIUM** | Schedule for next sprint. |
| **01 - 05** | 🟢 **LOW** | Technical debt / Optional improvement. |

---

## 📂 Repository Structure

This repository contains the essential files to implement and use the workflow:

```text
.
├── assets/                    # Project Images (Banner)
├── readme.md                  # Project Documentation
├── sentinel-code-guardian.md  # ⚠️ MASTER PROMPT (Install this)
├── USAGE_EN.md                # User Manual (English)
└── USAGE_ES.md                # User Manual (Spanish)
```

---

## ⚠️ Disclaimer

**Sentinel Code Guardian** is an AI-based assistance tool. It does not replace a certified human audit. The user is ultimately responsible for the code deployed to production.

---

## 👨‍💻 Author & Credits

**Developed and maintained by:**
**Fran Kloster**
**Role:** Developer & Cybersecurity Analyst