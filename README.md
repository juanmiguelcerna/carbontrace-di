# CarbonTrace-DI

### Digital Carbon Footprint · Circularity · Uncertainty-Aware Sustainability Analytics

CarbonTrace-DI is a Python-based applied research and software-engineering prototype designed to estimate, organize and analyze the institutional digital carbon footprint of universities and organizations.

The system combines digital-device inventories, operational energy, cloud services, artificial intelligence workloads, electronic circularity, uncertainty analysis and reduction scenarios within a traceable analytical workflow.

This repository is a **public technical portfolio showcase**.

> The complete Python source code, databases, internal calculation modules and implementation components are maintained privately. This repository presents the architecture, verified behavior, analytical capabilities and selected visual evidence of the executed prototype.

---

## 🌍 The Problem

Digital transformation creates environmental impacts that are often distributed across different sources:

- device manufacturing;
- electricity consumption;
- cloud computing;
- data transfer;
- artificial intelligence workloads;
- equipment replacement;
- electronic waste.

Organizations may track these elements separately or rely on isolated estimates, making it difficult to understand their combined digital footprint.

CarbonTrace-DI addresses this problem through a structured and auditable analytical system.

---

## 💡 What CarbonTrace-DI Does

The platform allows an organization to:

- register organizations and operational sites;
- inventory digital devices;
- estimate embodied carbon;
- analyze operational electricity consumption;
- register cloud and network activity;
- model artificial intelligence workloads;
- track repair, reuse and recycling events;
- evaluate electronic circularity;
- quantify uncertainty using Monte Carlo simulation;
- compare carbon-reduction scenarios;
- preserve calculation provenance;
- export institutional reports.

The objective is not only to estimate emissions, but also to support comparison between alternative reduction strategies using traceable assumptions.

---

## 🎯 Operational Question

CarbonTrace-DI explores the following decision problem:

> **What combination of device-life extension, energy efficiency, cloud/AI reduction and circularity can reduce digital environmental impact under traceable assumptions?**

---

## 🏗 High-Level Architecture

```text
Institutional Data
        │
        ▼
Organizations & Sites
        │
        ▼
Digital Asset Inventory
        │
        ├───────────────┐
        ▼               ▼
Energy Activity     Cloud / AI Activity
        │               │
        └───────┬───────┘
                ▼
        Calculation Layer
                │
                ▼
      Uncertainty Analysis
          Monte Carlo
                │
                ▼
      Carbon + Circularity
             Results
                │
        ┌───────┴────────┐
        ▼                ▼
Reduction Scenarios   Provenance
                     + Integrity
        │                │
        └───────┬────────┘
                ▼
 Dashboard · Excel · CSV · JSON
```

The diagram intentionally represents the system at a high level.

Detailed implementation remains private.

---

## 🧩 Functional Areas

The documented MVP includes capabilities for:

### Organizations & Sites

Institutional context and operational locations.

### Digital Device Inventory

Information such as:

- device category;
- quantity;
- nominal power;
- expected lifetime;
- embodied carbon;
- device weight;
- lifecycle status.

### Operational Energy

The system prioritizes measured electricity consumption when available.

When measured energy is unavailable, estimation can be performed from operational parameters.

### Cloud & Network

Cloud-related activity can be represented through components such as:

- computing;
- storage;
- data transfer.

### Artificial Intelligence

AI workloads can be represented through uncertainty ranges rather than a single artificially precise value.

### Circularity

The prototype records lifecycle events including:

- failures;
- repairs;
- upgrades;
- reassignment;
- reuse;
- storage;
- retirement;
- formal recycling;
- donation.

### Uncertainty

Monte Carlo simulation is used to evaluate uncertainty in the calculated digital footprint.

### Reduction Scenarios

Organizations can compare hypothetical interventions affecting areas such as:

- operational emissions;
- embodied emissions;
- cloud and AI activity;
- electronic waste.

### Provenance

Calculation records preserve information about:

- inputs;
- assumptions;
- calculation context;
- integrity metadata.

### Reporting

Results can be exported in:

- Excel;
- CSV;
- JSON.

---

## 🎲 Uncertainty Analysis

Environmental calculations frequently depend on uncertain factors.

Instead of representing every input as perfectly known, CarbonTrace-DI supports uncertainty-aware analysis.

The documented MVP includes Monte Carlo configurations of:

```text
100
1,000
5,000
10,000 iterations
```

Simulation outputs can include:

- mean;
- median;
- standard deviation;
- P05;
- P95;
- sensitivity information.

This allows the system to communicate ranges rather than false numerical precision.

---

## 🔍 Calculation Provenance

CarbonTrace-DI includes a provenance mechanism designed to preserve the context behind a calculation.

A calculation record may include:

```text
Input Snapshot
      +
Assumptions
      +
Calculation Context
      +
Integrity Hash
```

SHA-256 is used as part of the documented integrity mechanism.

This provides traceability between analytical results and the information that produced them.

---

## ♻️ Digital Circularity

CarbonTrace-DI separates carbon-footprint measurement from electronic circularity indicators.

This avoids collapsing different environmental concepts into a single arbitrary score.

Circularity-related analysis includes indicators associated with:

- repair;
- reuse;
- device-life extension;
- retirement;
- electronic waste;
- formal recycling.

This allows environmental performance to be analyzed from both:

**Carbon Impact + Asset Lifecycle**

---

## 📉 Reduction Scenarios

The prototype can compare a baseline against hypothetical reduction strategies.

Scenario analysis may include changes in:

- operational emissions;
- embodied carbon;
- cloud and AI consumption;
- electronic waste;
- estimated implementation cost.

This supports questions such as:

> Which intervention produces the greatest reduction under the available assumptions and resources?

---

## 📊 Dashboard

CarbonTrace-DI includes an interactive Streamlit dashboard.

The documented application was executed locally with synthetic institutional data.

The dashboard presents indicators associated with:

- expected total digital footprint;
- annualized embodied carbon;
- operational emissions;
- cloud impact;
- artificial intelligence impact;
- average device lifetime;
- repair;
- reuse;
- formal recycling.

The public repository will use selected screenshots from the executed application as visual evidence.

---

## 🖥 Application Workflow

A typical analytical workflow is:

```text
1. Select or create an organization
            │
            ▼
2. Register sites and digital devices
            │
            ▼
3. Register energy, cloud and AI activity
            │
            ▼
4. Register circularity events
            │
            ▼
5. Review dashboard and run uncertainty analysis
            │
            ▼
6. Compare reduction scenarios
            │
            ▼
7. Audit provenance and export reports
```

The workflow connects operational data with environmental analytics and decision support.

---

## 🛠 Technology Stack

### Core

Python 3.12+

### User Interface

Streamlit

### Data & Analytics

pandas · NumPy

### Persistence

SQLAlchemy 2.0 · SQLite

### Validation

Pydantic 2 · Domain Validation

### Reporting

pandas · openpyxl · Excel · CSV · JSON

### Uncertainty

Monte Carlo Simulation · Triangular and Uniform Distributions

### Integrity

JSON Snapshots · SHA-256

### Testing

Pytest · pytest-cov

---

## 🧱 Software Architecture

The documented implementation separates responsibilities into several layers:

```text
Presentation
     │
     ▼
Application Services
     │
     ├───────────────┐
     ▼               ▼
Domain Logic      Persistence
     │               │
     ▼               ▼
Calculations       SQLite
Validation
Uncertainty
     │
     ▼
Provenance & Reports
```

The architecture separates business and calculation logic from the user interface and persistence mechanisms.

---

## ✅ Software Verification

The documented MVP verification includes:

- **39 / 39 automated tests passed**
- **97% coverage in domain and service layers**
- SQLite database verification;
- report-export verification;
- local Streamlit execution;
- synthetic institutional data loading;
- navigation through the twelve main application modules.

The interface was executed locally on Windows with Python 3.13.x and Streamlit 1.60.0.

---

## 📸 Visual Evidence

The technical and user documentation contains real screenshots and diagrams from the executed prototype.

Selected public visual evidence can include:

- main dashboard;
- system workflow;
- architecture diagram;
- uncertainty-analysis output;
- scenario comparison;
- provenance results;
- institutional reporting views.

These screenshots allow the functioning prototype to be evaluated without publicly distributing the complete source implementation.

---

## 📤 Institutional Reporting

CarbonTrace-DI can export structured analytical results.

### Excel

The documented institutional workbook may include sections such as:

- executive summary;
- inventory;
- energy;
- cloud;
- artificial intelligence;
- circularity;
- scenarios;
- emission factors;
- methodological limitations.

### CSV

Structured operational/calculation outputs.

### JSON

Complete structured analytical information for reproducibility and integration.

---

## 🧪 Synthetic Demonstration Data

The academic MVP includes synthetic datasets intended for controlled demonstrations.

Documented contexts include examples related to:

- universities;
- banking;
- mining;
- construction.

Synthetic data allows the system to be demonstrated without exposing confidential institutional information.

---

## 🔐 Public vs. Private Scope

### Publicly presented in this repository

✅ Project problem  
✅ Business and sustainability context  
✅ High-level architecture  
✅ Functional capabilities  
✅ Technology stack  
✅ Verified software metrics  
✅ General calculation methodology  
✅ General uncertainty methodology  
✅ Selected dashboard screenshots  
✅ Selected architecture diagrams  
✅ Experimental/demo evidence  
✅ Project documentation  

### Maintained privately

🔒 Complete Python source code  
🔒 Internal calculation modules  
🔒 Full database files  
🔒 Complete automated test suite  
🔒 Internal service implementation  
🔒 Configuration files  
🔒 Private datasets  
🔒 Internal scripts  
🔒 Detailed implementation documentation  

This separation allows technical and professional evaluation of CarbonTrace-DI without publicly distributing the complete software implementation.

---

## ⚠️ Scope & Limitations

CarbonTrace-DI is an **academic applied-research MVP**.

It is not presented as:

- an official greenhouse-gas inventory;
- an environmental certification system;
- a regulatory reporting platform;
- an externally certified carbon calculator;
- a production institutional deployment.

Emission factors used in demonstrations may be illustrative and must be replaced with verified institutional or authoritative factors before real-world use.

The prototype is designed for:

**technical demonstration + experimental validation + analytical exploration**

---

## 📚 Project Status

**Software:** v2.0.0  
**Documentation:** v2.0.2

**Status:** Suitable for controlled technical demonstration and experimental validation.

---

## 👤 Author

**Juan Miguel Alonso Cerna Saavedra**

Business Engineering  
Universidad Continental — Peru

### Areas of Interest

- Data & Business Analytics
- Business Intelligence
- Sustainability Analytics
- Decision Support Systems
- Python Software Engineering
- Operations Research
- Uncertainty Analysis
- Auditable Analytics

---

## 🌎 Professional Context

CarbonTrace-DI demonstrates how business analytics and software engineering can be applied to sustainability management.

The project connects:

**Business + Data Analytics + Sustainability + Software Engineering + Decision Support**

It illustrates the use of Python not only for calculation, but also for:

- structured data management;
- dashboards;
- simulation;
- scenario analysis;
- uncertainty;
- reporting;
- traceability.

---

## 📫 Contact

[LinkedIn](https://www.linkedin.com/in/jmacerna)

GitHub: [@juanmiguelcerna](https://github.com/juanmiguelcerna)

---

## © Portfolio Notice

**Copyright © Juan Miguel Alonso Cerna Saavedra. All rights reserved.**

This repository is intended as a technical and academic portfolio showcase.

The complete source implementation is not distributed through this public repository.

No private databases, credentials, internal source modules or unpublished implementation components are included here.

---

**CarbonTrace-DI**

*Turning digital environmental data into traceable sustainability decisions.*
