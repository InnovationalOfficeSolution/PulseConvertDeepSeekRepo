# Pulse Convert — DeepSeek Harness MCP Plugin (`dsh-plugin`)

[![DeepSeek Harness](https://img.shields.io/badge/DSH-Plugin-blue.svg)](https://github.com/topics/dsh-plugin)
[![MCP Protocol](https://img.shields.io/badge/MCP-2024--11--05-brightgreen.svg)](https://modelcontextprotocol.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**Pulse Convert** is an enterprise Model Context Protocol (MCP) plugin for **DeepSeek Harness (DSH)**, developed by [Office Solution AI Labs](https://innovationalofficesolution.com).

It empowers DeepSeek coding and data engineering agents with automated assessment capabilities across **40+ legacy BI, ETL, and Data Warehouse platforms** modernizing to **Microsoft Fabric**, **Power BI**, and **Databricks**.

This plugin connects natively to the live Pulse Convert MCP service via high-performance **Streamable HTTP**. **No local Python installation or runtime dependencies required.**

---

## 🚀 Features & Tools

When connected, DeepSeek Harness gains direct access to 4 specialized modernization tools:

| Tool | Description |
| :--- | :--- |
| **`get_supported_migrations`** | Catalogs all 24 source platforms and 49 supported modernization pathways across BI, ETL, and DWH. |
| **`assess_migration`** | Generates instant complexity scoring, manual vs automated timeline comparisons, and workload blueprints. |
| **`lookup_migration_architecture`** | Returns star-schema modeling rules, semantic translation guidelines, and gotchas for any source platform. |
| **`create_assessment_request`** | Collects enterprise project scope and schedules an in-depth technical discovery consultation with Office Solution AI Labs. |

### Supported Migration Matrix (40+ Pathways)
* **BI & Reporting:** Tableau, Qlik Sense / View, SAP BusinessObjects (WebI), IBM Cognos, MicroStrategy, SSRS, Crystal Reports, Oracle Analytics (OAC/OBIEE).
* **ETL & Data Pipelines:** SSIS, SSAS, Alteryx, Informatica PowerCenter, SAS Data Integration.
* **Data Warehouses & Databases:** Snowflake, Teradata, Oracle, UiPath RPA, Excel Workbooks, MS Access.
* **Target Modernization Platforms:** Microsoft Fabric (Direct Lake, Data Factory, Lakehouse), Power BI (Tabular Import/DirectQuery), Databricks (Delta Live Tables, PySpark).

---

## 📦 Installation in DeepSeek Harness (DSH)

> **Prerequisite:** DSH uses `pnpm` under the hood to manage profile packages (`npm install -g pnpm`).

### Option 1: Install Directly from GitHub (Recommended)
Add the plugin directly into your DSH web profile without manual cloning:
```bash
dsh plugin --profile web add git+https://github.com/InnovationalOfficeSolution/PulseConvertDeepSeekRepo.git
```

### Option 2: Install from Local Clone
If you have cloned this repository locally:
```bash
git clone https://github.com/InnovationalOfficeSolution/PulseConvertDeepSeekRepo.git
cd PulseConvertDeepSeekRepo
dsh plugin --profile web add .
```

### Option 3: Manual Profile Mount (Zero Git)
Add the following snippet directly into your `~/.dsh/profiles/web/cordis.patch.yml`:
```yaml
- insert:
    - id: pulse-convert-dsh
      name: '@deepseek-ai/dsh-mcp-client'
      config:
        serverName: 'pulse-convert'
        transport: 'streamable-http'
        url: 'https://mcp.innovationalofficesolution.com/pulse-convert/'
```

---

## ⚡ Launch & Verify

Restart your DeepSeek Harness web workbench:
```bash
dsh web
```

Open `http://127.0.0.1:3080` in your browser and test with prompts such as:
* *"What legacy BI and ETL platforms can you help me migrate to Microsoft Fabric?"*
* *"Assess migrating 50 Alteryx workflows to Microsoft Fabric."*
* *"How do Cognos Framework Manager relational packages map to Power BI semantic models?"*

---

## 🔒 Security & Privacy

* **Zero Local Execution:** Operates as a pure client-side manifest connecting over secure HTTPS.
* **Encrypted in Transit:** All communication between DSH and the Pulse Convert MCP server is protected by industry-standard TLS (HTTPS).
* **Privacy Policy:** Full privacy policy and data protection terms are available at [https://mcp.innovationalofficesolution.com/pulse-convert/privacy.html](https://mcp.innovationalofficesolution.com/pulse-convert/privacy.html).

---

## 🏢 About Office Solution AI Labs

[Office Solution AI Labs](https://innovationalofficesolution.com) specializes in AI-accelerated enterprise modernization, delivering up to 75% faster migrations from legacy BI and ETL platforms to modern cloud architectures.

* **Website:** [innovationalofficesolution.com](https://innovationalofficesolution.com)
* **Inquiries:** `admin@innovationalofficesolution.com`
* **License:** [MIT](LICENSE)
