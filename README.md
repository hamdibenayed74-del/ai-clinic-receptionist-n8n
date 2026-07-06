# 🏥 AI Clinic Receptionist

> **A modular AI-powered clinic receptionist built with n8n, showcasing workflow orchestration, AI-driven appointment scheduling, WhatsApp integration, conversation memory, centralized configuration, and global error handling.**

![n8n](https://img.shields.io/badge/n8n-Automation-EA4B71?style=for-the-badge\&logo=n8n)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT-412991?style=for-the-badge\&logo=openai)
![WhatsApp](https://img.shields.io/badge/WhatsApp-Cloud%20API-25D366?style=for-the-badge\&logo=whatsapp)
![Portfolio](https://img.shields.io/badge/Portfolio-Project-blue?style=for-the-badge)

---

# 📖 Overview

This project demonstrates how to design a **modular automation system** using **n8n**.

Rather than building a single large workflow, the application is divided into independent services, each with a single responsibility. These workflows communicate through standardized data structures, making the system easier to understand, maintain, and extend.

The project simulates an AI-powered clinic receptionist capable of understanding patient requests, managing appointment scheduling, maintaining conversation history, and delivering responses through WhatsApp.

> **Note**
>
> This is a portfolio project created to demonstrate workflow architecture, automation design, and AI orchestration using n8n.
>
> Google Sheets is intentionally used as the storage backend to keep the project simple while focusing on architecture and workflow design rather than infrastructure.

---

# ✨ Features

* 🤖 AI Receptionist
* 📅 Intelligent Appointment Scheduling
* 💬 Conversation Memory
* 📱 WhatsApp Cloud API Integration
* ⚙️ Centralized Configuration Service
* 🛡️ Global Error Handling
* 🔄 Modular Workflow Architecture
* 📊 Structured Validation & Logging

---

# 🏗️ Architecture
https://github.com/hamdibenayed74-del/ai-clinic-receptionist-n8n/blob/main/architecture.png.png?raw=true
---

# 📂 Workflow Overview

| Workflow                        | Responsibility                                                       |
| ------------------------------- | -------------------------------------------------------------------- |
| **MW-00 Router**                | Main orchestration workflow and system entry point.                  |
| **SW-01 Conversation Memory**   | Stores and retrieves conversation history.                           |
| **SW-01B Appointment Storage**  | Handles appointment persistence through a storage abstraction layer. |
| **SW-02 AI Receptionist**       | Interprets patient requests and generates structured AI responses.   |
| **SW-03 Appointment Scheduler** | Validates scheduling requests and coordinates appointment creation.  |
| **SW-05 Reply Dispatcher**      | Routes responses to the appropriate communication channel.           |
| **SW-06 WhatsApp Sender**       | Sends WhatsApp messages with validation, retry, and logging.         |
| **CFG-01 Configuration**        | Centralized provider for clinic configuration and business rules.    |
| **EW-00 Global Error Handler**  | Normalizes, logs, and classifies workflow errors.                    |

---

# 🔄 System Flow

```text
Patient Message
        │
        ▼
 MW-00 Router
        │
        ▼
 SW-02 AI Receptionist
        │
        ▼
 SW-03 Appointment Scheduler
        │
        ▼
SW-01B Appointment Storage
        ▲
        │
 CFG-01 Configuration
        │
        ▼
 SW-05 Reply Dispatcher
        │
        ▼
 SW-06 WhatsApp Sender
        │
        ▼
 Patient Response
```

Every workflow is designed around the **Single Responsibility Principle**, allowing services to evolve independently while remaining easy to maintain.

---

# 🛠️ Technology Stack

* **n8n**
* **OpenAI**
* **Google Sheets**
* **WhatsApp Cloud API**
* **JavaScript**
* **JSON Schema Validation**

---

# 📁 Repository Structure

```text
.
├── README.md
├── LICENSE
│
├── workflows/
│   ├── MW-00 Router.json
│   ├── SW-01 Conversation Memory.json
│   ├── SW-01B Appointment Storage.json
│   ├── SW-02 AI Receptionist.json
│   ├── SW-03 Appointment Scheduler.json
│   ├── SW-05 Reply Dispatcher.json
│   ├── SW-06 WhatsApp Sender.json
│   ├── CFG-01 Configuration.json
│   └── EW-00 Global Error Handler.json
│
├── docs/
│   ├── architecture.png
│   ├── workflow-map.png
│   ├── screenshots/
│   └── demo.gif
│
└── examples/
```

---

# 🎯 Design Principles

The project is built around several software engineering principles:

* **Single Responsibility Principle** — Every workflow performs one well-defined task.
* **Separation of Concerns** — AI, scheduling, storage, messaging, configuration, and error handling are isolated into dedicated workflows.
* **Modular Architecture** — Components communicate through standardized request and response structures.
* **Centralized Configuration** — Business settings are managed through a single configuration service.
* **Reliability** — Validation, retry strategies, and centralized error handling improve resilience.

---

# 🚀 Example Execution

1. A patient sends a WhatsApp message.
2. The Router receives the request.
3. Conversation history is retrieved.
4. The AI Receptionist interprets the patient's intent.
5. Appointment requests are delegated to the Appointment Scheduler.
6. Confirmed appointments are stored.
7. The Reply Dispatcher selects the delivery channel.
8. The WhatsApp Sender delivers the response.
9. Unexpected failures are processed by the Global Error Handler.

---

# 📸 Screenshots

Screenshots of the main workflows will be added here.

* MW-00 Router
* SW-02 AI Receptionist
* SW-03 Appointment Scheduler
* SW-06 WhatsApp Sender
* System Architecture

---

# 🎥 Demo

A short walkthrough demonstrating the complete workflow will be added soon.

---

# 🔮 Future Improvements

* PostgreSQL storage backend
* Google Calendar integration
* Multi-clinic support
* Authentication & authorization
* Analytics dashboard
* Automated workflow testing

---

# 📄 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

**Taleb Rkik**

Built as a portfolio project to demonstrate automation architecture, workflow orchestration, and AI-powered business process automation using n8n.
