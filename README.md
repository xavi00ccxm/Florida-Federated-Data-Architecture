# Florida-Federated-Data-Architecture
# 🏛️ Florida Federated Data Architecture
**Designed by:** Otto De La Rocha  
**Role:** Data Architect | Data Engineer | Data Analyst  

---

### 📘 Overview
This project demonstrates a **secure, cloud-native federated data architecture** designed for the **Florida Digital Service (Department of Management Services)** to enable **cross-agency data sharing** while maintaining **agency autonomy**.  
It leverages Microsoft Azure technologies — **Azure Data Factory (ADF)**, **Microsoft Purview**, **Azure Active Directory (AAD)**, and **Power BI** — to ensure interoperability, governance, and compliance across the enterprise.

---

### 🧩 Data Flow Diagram
![Florida Federated Data Architecture](Florida_Federated_Data_Architecture.png)

---

### 🧠 Explanation
Each participating agency (for example, the **Department of Revenue [DOR]**, **Department of Transportation [DOT]**, and **Department of Children & Families [DCF]**) maintains its own **Bronze – Silver – Gold** data layers.  
Instead of centralizing raw data, this architecture uses **Azure Data Factory (ADF)** to securely extract, transform, and load standardized subsets of information through **standardized interfaces** and **encrypted pipelines**.

Once ingested, data passes through a **Federated Integration Layer**, where transformation rules align formats and schemas.  
The **State Master Index (Master Data Management Hub)** then performs **entity resolution** across key identifiers such as *Citizen ID*, *Parcel ID*, and *Application ID*, linking records across agencies.

Governance and compliance are handled by **Microsoft Purview**, which provides **schema lineage, sensitivity labeling, and audit tracking** in compliance with:
- **HIPAA** (Health Insurance Portability and Accountability Act)  
- **CJIS** (Criminal Justice Information Services Security Policy)  
- **PCI-DSS** (Payment Card Industry Data Security Standard)  
- **Rule 60GG-2**, Florida’s IT governance rule  

Finally, the **Secure Data Access Layer** delivers insights through **Power BI dashboards** and **REST / GraphQL APIs**. Access is managed using:
- **Azure Active Directory (AAD)** for authentication  
- **OAuth 2.0** protocol for secure authorization  
- **RBAC** (Role-Based Access Control) and **ABAC** (Attribute-Based Access Control)

All data assets are documented within a **Microsoft Purview Catalog**, ensuring discoverability, stewardship, and transparency.

---

### 🗂️ Data Catalog

| **Component** | **Description** | **Technologies / Standards** | **Purpose / Outcome** |
|----------------|----------------|-------------------------------|-----------------------|
| **Agency Data Sources (Decentralized Ownership)** | Each agency maintains its own Bronze – Silver – Gold data layers. | SQL Server, Oracle, On-prem or Cloud DBs | Agencies retain control and responsibility for data quality while following statewide interface standards. |
| **Secure Integration Layer** | Handles encryption, tokenization, logging, and message queuing. | Azure Service Bus, Event Hub, HTTPS/TLS 1.2+ | Guarantees secure, reliable transmission and auditability during ingestion. |
| **Azure Data Factory (ADF)** | Extract-Transform-Load (ETL) / Extract-Load-Transform (ELT) engine and pipeline orchestrator. | Azure Data Factory, Data Flows, Logic Apps | Performs ETL, secure API / file / event ingestion, and metadata capture. |
| **Federated Integration Layer** | Applies standardized schemas and reconciliation logic across datasets. | JSON / Parquet formats, Schema Registry | Ensures interoperability and consistent data structures. |
| **State Master Index (MDM Hub)** | Master Data Management (MDM) center for cross-agency identifiers. | Azure SQL Database or Synapse | Resolves entities (*Citizen_ID*, *Parcel_ID*, *Application_ID*), deduplicates records, links data, and hashes PII. |
| **Data Governance & Compliance** | Enforces schema lineage, sensitivity, and policy rules. | Microsoft Purview / ISO 20000-1 / Rule 60GG-2 | Provides full governance, audit trails, and regulatory compliance across agencies. |
| **Secure Data Access Layer** | Controls authenticated access to shared dashboards and APIs. | Azure Active Directory (AAD), OAuth 2.0, RBAC, ABAC | Delivers fine-grained security for interagency users and citizens. |
| **Analytics & Reporting** | Provides statewide insights and KPIs through dashboards. | Power BI, SQL Views, Incremental Refresh | Enables decision-makers to view real-time performance and program outcomes. |
| **API Gateway / Data Services** | Offers real-time and batch data endpoints for applications. | REST / GraphQL APIs, Azure API Management | Allows secure interagency and citizen access to authorized data. |
| **Data Catalog (Microsoft Purview)** | Catalogs and documents data assets for discovery and stewardship. | Microsoft Purview Metadata API | Centralized registry of datasets, schemas, lineage, and sensitivity labels. |

---

### 🔁 Continuous Improvement
A **Data Quality Feedback Loop** from the Analytics layer ensures that issues or inconsistencies identified in Power BI or API outputs are reviewed and corrected in Azure Data Factory validation rules, continuously improving data accuracy and trust.

---

### 🧰 Key Acronyms (Spelled Out)

| Acronym | Full Form | Description |
|----------|------------|-------------|
| **ADF** | Azure Data Factory | Cloud service for building ETL/ELT pipelines and orchestrating data integration. |
| **AAD** | Azure Active Directory | Microsoft’s identity and access management platform for authentication. |
| **MDM** | Master Data Management | Process of creating a single, consistent view of key entities across systems. |
| **RBAC** | Role-Based Access Control | Access based on user roles (e.g., analyst, engineer, manager). |
| **ABAC** | Attribute-Based Access Control | Access based on user attributes (e.g., agency, location, security clearance). |
| **HIPAA** | Health Insurance Portability and Accountability Act | U.S. law protecting health information privacy and security. |
| **CJIS** | Criminal Justice Information Services Security Policy | FBI standard for handling criminal justice data. |
| **PCI-DSS** | Payment Card Industry Data Security Standard | Global standard for protecting payment card data. |
| **ETL** | Extract – Transform – Load | Process for moving and preparing data for analysis. |
| **ELT** | Extract – Load – Transform | Cloud-optimized variant where transformations occur after loading. |
| **API** | Application Programming Interface | Software interface enabling applications to exchange data. |
| **RLS** | Row-Level Security | Security feature that restricts database rows visible to a user based on role or filter. |
| **OAuth 2.0** | Open Authorization 2.0 Protocol | Framework for secure delegated access to resources. |

---

### ⚙️ Tools & Technologies
- **Azure Data Factory** (ADF) — ETL pipelines  
- **Microsoft Purview** — governance & lineage  
- **Power BI** — reporting & analytics  
- **Azure Active Directory (AAD)** — identity management  
- **Azure API Management** — secure API layer  
- **Azure Service Bus / Event Hub** — messaging integration  
- **SQL Server / Synapse Analytics** — storage & MDM hub  

---

### 🧩 Architecture Principles
- **Federated, not centralized:** agencies own their data.  
- **Interoperable schemas:** standardized data exchange formats.  
- **Secure by design:** encryption, tokenization, RBAC/ABAC.  
- **Compliant:** HIPAA, CJIS, PCI-DSS, Rule 60GG-2.  
- **Metadata-driven:** governance built into every layer.  

---

### ✉️ Contact
📧 xavi00ccxm@gmail.com  
🔗 GitHub: [github.com/OttoDeLaRocha](https://github.com/OttoDeLaRocha)

---

*Federated Data Architecture  |  Cloud Native  |  Secure & Compliant  |  Data Governance by Design*
