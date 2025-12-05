# 📘 Manual de Usuario: Sentinel Code Guardian

**Versión:** 2.0 (Global Workflow)  
**Rol:** Auditor de Seguridad & Arquitecto de Soluciones  
**Filosofía:** Zero Trust (Confianza Cero)

---

## 1. ⚡ Cheat Sheet (Comandos Rápidos)

Copia esta tabla y tenla siempre a mano. Todos los comandos se ejecutan en el chat de Antigravity.

| Comando | Función | Cuándo usarlo |
| :--- | :--- | :--- |
| **`/sentinel`** | **Auditoría Estándar** | Antes de cada commit o PR. Analiza el archivo abierto o el código seleccionado. |
| **`/sentinel fix`** | **Reparación Automática** | Cuando Sentinel encuentra un error. Genera el código corregido y seguro. |
| **`/sentinel --wargame`** | **Simulación de Ataque** | Para entender *cómo* te hackearían. Inicia una batalla Red Team vs Blue Team. |
| **`/sentinel audit`** | **Generar Reporte Físico** | Para Compliance. Crea un archivo `.md` en la carpeta `security_reports/`. |
| **`/sentinel diff`** | **Revisión de Cambios** | Analiza solo lo que has modificado respecto a la rama principal (`git diff`). |

---

## 2. 🛡️ Alcance: ¿Qué es capaz de detectar?

Sentinel no "adivina". Ejecuta mentalmente una serie de herramientas de análisis estático basadas en reglas estrictas.

### 🔑 A. Secretos y Credenciales (Secrets Scanner)
Evita que subas claves privadas al repositorio.
* **Detecta:** * API Keys (`sk-`, `ghp-`)
  * Tokens de AWS (`AKIA...`)
  * Contraseñas hardcodeadas
  * Claves Privadas RSA/PEM
* **Acción:** Te alerta inmediatamente y censura la clave en el chat.

### 💉 B. Inyecciones de Código (Injection Scanner)
Protege contra los ataques más comunes de la web.
* **SQL Injection (SQLi):** Detecta concatenación de texto en consultas a base de datos (ej: `"SELECT * FROM users WHERE id = " + id`).
* **Cross-Site Scripting (XSS):** Detecta inserción insegura de HTML (ej: `.innerHTML`, `dangerouslySetInnerHTML`).

### 🖥️ C. Vulnerabilidades de Infraestructura (OS Scanner)
Evita que un atacante tome control del servidor.
* **Remote Code Execution (RCE):** Uso peligroso de `eval()`, `exec()`, `spawn()`.
* **Path Traversal:** Manipulación de rutas de archivos (ej: `../etc/passwd`) en funciones de lectura.

### 🏗️ D. Calidad y Arquitectura (Dev Capabilities)
Si se lo pides, actúa como Ingeniero Senior.
* Revisión de Código (Clean Code, SOLID).
* Optimización de Algoritmos (Rendimiento).
* Generación de Tests Unitarios.

---

## 3. 📊 Cómo leer el Puntaje de Riesgo

Sentinel no solo dice "esto está mal", te dice **qué tan grave es** usando una fórmula matemática.

> **Fórmula:** Riesgo = Impacto × Probabilidad × Exposición

Cada hallazgo recibe una puntuación del 1 al 27.

| Puntos | Nivel | Significado para el Desarrollador |
| :--- | :--- | :--- |
| **18 - 27** | 🚨 **CRÍTICA** | **STOP TOTAL.** Hay un agujero de seguridad grave. No hagas deploy. Arréglalo YA. |
| **12 - 17** | 🔴 **ALTA** | Vulnerabilidad explotable. Debe arreglarse antes de cerrar el ticket. |
| **06 - 11** | 🟠 **MEDIA** | Problema de seguridad moderado o condicional. Agendar para el próximo sprint. |
| **01 - 05** | 🟢 **BAJA** | Deuda técnica, falta de buenas prácticas o mejora de estilo. |

---

## 4. ⚔️ Modo Wargame (Simulación)

Esta es la función educativa más potente de Sentinel. Al usar `/sentinel --wargame`, el agente simula dos roles:

1.  **🔴 RED TEAM (El Atacante):** Analiza tu código y crea un **Payload Real** (un script o input malicioso) que demuestra cómo romper tu sistema.
    * *Ejemplo:* "Si ingreso `' OR '1'='1` en tu campo de usuario, accedo como admin."
2.  **🔵 BLUE TEAM (El Defensor):** Analiza el ataque y escribe el parche exacto para bloquearlo.

Úsalo para aprender seguridad ofensiva y defensiva en tiempo real.

---

## 5. 📂 Auditoría y Reportes

Para empresas o proyectos serios, Sentinel deja huella.
Si detecta vulnerabilidades de nivel **ALTO** o **CRÍTICO**, o si ejecutas `/sentinel audit`, generará automáticamente archivos en tu proyecto:

* **Ubicación:** `security_reports/`
* **Formato:** `AUDIT-[Fecha]-[Archivo].md`
* **Contenido:** Resumen ejecutivo, tabla de hallazgos, evidencia técnica y recomendaciones de mitigación.

---

## 6. 🚫 Límites y Ética (Lo que NO hace)

Para tu tranquilidad y seguridad del proyecto:
1.  **No rompe nada:** Nunca borra archivos ni ejecuta comandos destructivos.
2.  **No inventa:** Si no está seguro de una vulnerabilidad, la marcará como "Posible" o "Advertencia", reduciendo falsos positivos.
3.  **Soluciones Seguras:** Nunca te sugerirá un "parche rápido" que sea inseguro. Si no se puede arreglar bien, te dirá que reescribas la función.