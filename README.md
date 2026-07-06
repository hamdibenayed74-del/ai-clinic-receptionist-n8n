# 🏥 AI Clinic Receptionist (n8n)

> A modular AI-powered clinic receptionist built with **n8n**, demonstrating workflow orchestration, appointment scheduling, conversation memory, WhatsApp integration, centralized configuration, and global error handling using a service-oriented architecture.

---

## 📖 Overview

This project is a portfolio demonstration of designing scalable automation systems with **n8n**.

Instead of building one large workflow, the solution is organized into independent services that communicate through standardized contracts. Each workflow has a single responsibility, making the system easier to understand, maintain, and extend.

> **Note:** This is a learning and portfolio project. Google Sheets is intentionally used as the storage layer to keep the project simple while demonstrating workflow architecture and automation design principles.

---

# ✨ Features

* 🤖 AI-powered receptionist
* 📅 Intelligent appointment scheduling
* 💬 Conversation memory management
* 📱 WhatsApp message delivery
* ⚙️ Centralized configuration service
* 🛡️ Global error handling
* 🧩 Modular workflow architecture
* 🔄 Reusable workflow contracts
* 📊 Structured logging and validation

---

# 🏗️ System Architecture

```text
                Patient
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
                Patient

         EW-00 Global Error Handler
               (All Workflows)
```

---

# 📂 Workflow Overview

| Workflow                        | Responsibility                                                      |
| ------------------------------- | ------------------------------------------------------------------- |
| **MW-00 Router**                | Main orchestration workflow that coordinates the entire system.     |
| **SW-01 Conversation Memory**   | Stores and retrieves conversation context.                          |
| **SW-01B Appointment Storage**  | Provides a storage abstraction for appointment data.                |
| **SW-02 AI Receptionist**       | Interprets patient requests and produces structured AI responses.   |
| **SW-03 Appointment Scheduler** | Validates scheduling requests and coordinates appointment creation. |
| **SW-05 Reply Dispatcher**      | Routes outgoing responses to the correct communication channel.     |
| **SW-06 WhatsApp Sender**       | Sends outbound WhatsApp messages with retry handling.               |
| **CFG-01 Configuration**        | Centralized provider for clinic configuration and business rules.   |
| **EW-00 Global Error Handler**  | Captures, normalizes, logs, and classifies workflow failures.       |

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
├── docs/
│   ├── architecture.png
│   ├── workflow-map.png
│   ├── screenshots/
│   └── demo.gif
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
└── examples/
    ├── incoming-message.json
    ├── scheduler-result.json
    ├── agent-result.json
    └── delivery-result.json
```

---

# 🔄 Workflow Design Principles

This project follows several software engineering principles:

* **Single Responsibility Principle** — Each workflow performs one specific task.
* **Separation of Concerns** — AI, scheduling, storage, messaging, configuration, and error handling are isolated into dedicated services.
* **Reusable Contracts** — Workflows exchange standardized request and response objects.
* **Configuration Centralization** — Business configuration is managed through a dedicated workflow instead of being duplicated.
* **Fault Tolerance** — Validation, retries, and centralized error handling improve reliability.

---

# 🚀 Example Flow

1. A patient sends a WhatsApp message.
2. **MW-00 Router** receives the request.
3. Conversation history is retrieved.
4. **SW-02 AI Receptionist** interprets the request.
5. If scheduling is required, **SW-03 Appointment Scheduler** is invoked.
6. Appointment data is stored through **SW-01B Appointment Storage**.
7. **SW-05 Reply Dispatcher** selects the delivery channel.
8. **SW-06 WhatsApp Sender** sends the response.
9. Any unexpected failures are handled by **EW-00 Global Error Handler**.

---

# 📸 Screenshots

Add screenshots of the following workflows:

* MW-00 Router
* SW-02 AI Receptionist
* SW-03 Appointment Scheduler
* SW-06 WhatsApp Sender
* System Architecture

Store them in:

```text
docs/screenshots/
```

---

# 🎥 Demo

Record a short demonstration (3–5 minutes) showing:

* Receiving a patient message
* AI interpretation
* Appointment scheduling
* Storage update
* WhatsApp reply
* Error handling

Add the recording to the repository or link to YouTube.

---

# 🔮 Future Improvements

Possible enhancements include:

* PostgreSQL storage backend
* Calendar integration
* Multi-clinic support
* Authentication and user roles
* Analytics dashboard
* Automated workflow testing

---

# 📄 License

This project is released under the MIT License.

---

# 👨‍💻 Author

Created as a portfolio project to demonstrate workflow architecture, automation design, and AI-powered business process automation using n8n.
