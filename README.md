# AI Agentic Workflow for Automated ML-Based Threat Detection and Remediation

**Humber Polytechnic College – Cloud Computing (Summer 2025) Capstone Project**

## Overview

This project implements a fully automated AI-driven penetration testing and remediation pipeline for web applications. Using Python, Node-RED, OWASP ZAP, and LLM-powered agents, the system detects vulnerabilities, classifies them by severity, and applies automated fixes in a continuous feedback loop. This approach minimizes manual intervention, accelerates remediation cycles, and demonstrates a practical agentic workflow for modern DevSecOps practices.

---

## Features

* **Automated Vulnerability Scanning**: Agent 1 triggers OWASP ZAP API scans on Heroku-hosted applications.
* **AI-Powered Classification**: Agent 2 analyzes scan results, categorizes vulnerabilities (High/Medium/Low), and identifies affected source files with potential fixes.
* **Automated Remediation**: Agent 3 modifies source files, applies patches, and redeploys the application.
* **Self-Healing Loop**: Continues scanning and remediation until all vulnerabilities are resolved.
* **Efficiency Gains**: \~70% reduction in manual effort and \~90% automated fixes compared to traditional testing.
* **Ethical Compliance**: Tested only on authorized applications, adhering to ethical hacking standards.

---

## Architecture & Workflow

```
User Initiates Scan
        ↓
   Agent 1: OWASP ZAP Scan
        ↓
   Agent 2: Vulnerability Classification (LLM-based)
        ↓
   Agent 3: Automated Remediation & Redeployment
        ↓
     Feedback Loop (Repeat until no vulnerabilities remain)
```

**Technologies Used:**

* Python (Backend logic for classification and remediation)
* Node-RED (Orchestration of agents)
* OWASP ZAP (Automated vulnerability scanning)
* AutoGen & Ollama (LLM reasoning for fixes)
* Heroku (Application hosting & deployment)

---

## Usage

1. Start the Node-RED server:

```bash
node-red
```

2. Trigger the workflow from the Node-RED UI by providing the target Heroku application URL.

3. Monitor agent execution in the Node-RED dashboard:

   * **Agent 1**: Runs ZAP scan and generates `zap_output.json`
   * **Agent 2**: Classifies vulnerabilities and suggests fixes
   * **Agent 3**: Applies patches and redeploys the application

4. Workflow continues automatically until no vulnerabilities remain.

---

## Results

* Significant reduction in ZAP alerts after automated remediation.
* Near-complete automation of scanning, classification, and remediation cycle.
* Improved productivity and reduced time-to-remediation.

**Benchmarking:**

* Manual vs Automated: \~70% reduction in time, \~90% fixes automated

---

## Limitations

* Currently supports single Heroku-hosted application.
* Static test environment; no live production scanning.
* Limited dataset for AI model training.
* Complex business logic vulnerabilities may still require manual review.
* Executor Agent applies line-level patches; full fine-grained patching is ongoing.

---

## Future Improvements

* Broader vulnerability coverage across multiple platforms.
* Production-ready CI/CD integration.
* Fine-grained patching for more complex codebases.
* Real-time monitoring and multi-tenant support.

