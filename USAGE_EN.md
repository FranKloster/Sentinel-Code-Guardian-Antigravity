# 📘 User Manual: Sentinel Code Guardian

**Version:** 2.0 (Global Workflow)
**Role:** Security Auditor & Solutions Architect
**Philosophy:** Zero Trust

---

## 1. ⚡ Cheat Sheet (Quick Commands)

Copy this table and keep it handy. All commands are executed in the Antigravity chat.

| Command | Function | When to use it |
| :--- | :--- | :--- |
| **`/sentinel`** | **Standard Audit** | Before every commit or PR. Analyzes the currently open file or selected code. |
| **`/sentinel fix`** | **Auto-Repair** | When Sentinel finds an error. Generates corrected and secure code. |
| **`/sentinel --wargame`** | **Attack Simulation** | To understand *how* you would be hacked. Initiates a Red Team vs. Blue Team battle. |
| **`/sentinel audit`** | **Generate Physical Report** | For Compliance. Creates a `.md` file in the `security_reports/` folder. |
| **`/sentinel diff`** | **Change Review** | Analyzes only what you have modified compared to the main branch (`git diff`). |

---

## 2. 🛡️ Scope: What can it detect?

Sentinel does not "guess." It mentally executes a series of static analysis tools based on strict rules.

### 🔑 A. Secrets and Credentials (Secrets Scanner)
Prevents you from uploading private keys to the repository.
* **Detects:**
  * API Keys (`sk-`, `ghp-`)
  * AWS Tokens (`AKIA...`)
  * Hardcoded passwords
  * RSA/PEM Private Keys
* **Action:** Immediately alerts you and censors the key in the chat.

### 💉 B. Code Injections (Injection Scanner)
Protects against the most common web attacks.
* **SQL Injection (SQLi):** Detects text concatenation in database queries (e.g., `"SELECT * FROM users WHERE id = " + id`).
* **Cross-Site Scripting (XSS):** Detects unsafe HTML insertion (e.g., `.innerHTML`, `dangerouslySetInnerHTML`).

### 🖥️ C. Infrastructure Vulnerabilities (OS Scanner)
Prevents an attacker from taking control of the server.
* **Remote Code Execution (RCE):** Dangerous use of `eval()`, `exec()`, `spawn()`.
* **Path Traversal:** Manipulation of file paths (e.g., `../etc/passwd`) in read functions.

### 🏗️ D. Quality and Architecture (Dev Capabilities)
If requested, it acts as a Senior Engineer.
* Code Review (Clean Code, SOLID).
* Algorithm Optimization (Performance).
* Unit Test Generation.

---

## 3. 📊 How to Read the Risk Score

Sentinel doesn't just say "this is wrong," it tells you **how serious it is** using a mathematical formula.

> **Formula:** Risk = Impact × Likelihood × Exposure

Each finding receives a score from 1 to 27.

| Points | Level | Meaning for the Developer |
| :--- | :--- | :--- |
| **18 - 27** | 🚨 **CRITICAL** | **TOTAL STOP.** There is a severe security hole. Do not deploy. Fix it NOW. |
| **12 - 17** | 🔴 **HIGH** | Exploitable vulnerability. Must be fixed before closing the ticket. |
| **06 - 11** | 🟠 **MEDIUM** | Moderate or conditional security issue. Schedule for the next sprint. |
| **01 - 05** | 🟢 **LOW** | Technical debt, lack of best practices, or style improvement. |

---

## 4. ⚔️ Wargame Mode (Simulation)

This is Sentinel's most powerful educational feature. When using `/sentinel --wargame`, the agent simulates two roles:

1.  **🔴 RED TEAM (The Attacker):** Analyzes your code and creates a **Real Payload** (a malicious script or input) demonstrating how to break your system.
    * *Example:* "If I enter `' OR '1'='1` in your user field, I gain admin access."
2.  **🔵 BLUE TEAM (The Defender):** Analyzes the attack and writes the exact patch to block it.

Use it to learn offensive and defensive security in real-time.

---

## 5. 📂 Audit and Reports

For enterprises or serious projects, Sentinel leaves a trail.
If **HIGH** or **CRITICAL** vulnerabilities are detected, or if you execute `/sentinel audit`, it will automatically generate files in your project:

* **Location:** `security_reports/`
* **Format:** `AUDIT-[Date]-[File].md`
* **Content:** Executive summary, findings table, technical evidence, and mitigation recommendations.

---

## 6. 🚫 Limits and Ethics (What it does NOT do)

For your peace of mind and project safety:
1.  **Does not break anything:** It never deletes files or executes destructive commands.
2.  **Does not invent:** If it is unsure about a vulnerability, it will mark it as "Possible" or "Warning," reducing false positives.
3.  **Secure Solutions:** It will never suggest a "quick fix" that is insecure. If it cannot be fixed properly, it will tell you to rewrite the function.