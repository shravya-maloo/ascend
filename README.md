# Ascend

Ascend is an AI-powered employee training and performance platform built during the Quadrant Technologies internship program. The project combines employee management, training, quizzes, performance tracking, and AI-powered tools into a centralized platform.

The project was originally connected to Azure resources for its backend services, database, AI functionality, and deployment pipeline. Those Azure resources are no longer active, so the application is **not currently functional as a live deployed system**. The codebase and infrastructure configuration remain available, and the application can be brought back online by reconnecting it to the required Azure resources.

## Features

- 👥 **Employee management** — Manage employee information and organize users within the platform
- 📚 **Training & certifications** — Provide employees with training materials and track completion and certification requirements
- 📝 **AI-powered quiz generation** — Generate training quizzes from available learning content
- 🤖 **AI chatbot** — Provide employees with an interactive assistant for training and platform-related questions
- 📊 **Performance tracking** — Track employee progress, quiz results, training completion, and other performance metrics
- 🏆 **Leaderboards** — Use points and performance data to visualize employee progress
- 📄 **Document processing** — Work with training and other uploaded documents as part of the platform's learning workflow
- ☁️ **Azure infrastructure** — Originally designed to use Azure services for application hosting, backend functionality, data storage, and AI capabilities
- 🔄 **CI/CD pipelines** — Includes Azure Pipeline configurations for frontend and backend deployment

## Project status

**Current status: Not currently live**

Ascend was functional during the Quadrant Technologies internship program with its Azure resources connected. The Azure environment used for the project is no longer available, so the deployed application cannot currently be accessed.

The repository contains the application code, infrastructure configuration, deployment pipelines, demo data, and supporting documentation. With the appropriate Azure resources and environment variables reconnected, the application can be configured and deployed again.

## Tech stack

- **Python** — backend services, APIs, and application logic
- **TypeScript / JavaScript** — frontend and web application development
- **Azure** — cloud infrastructure, deployment, and connected services
- **Azure Pipelines** — CI/CD for frontend and backend
- **AI / LLM services** — chatbot and AI-powered quiz generation
- **Database** — persistent employee, training, quiz, and performance data
- **REST APIs** — communication between application components

## Project structure

```text
ascend/
├── api/                         # API endpoints and backend interfaces
├── chatbot/                     # AI chatbot functionality
├── data/
│   └── documents/               # Application and training documents
├── db/                          # Database configuration and operations
├── demo-data/                   # Sample data for development and testing
├── docs/                        # Project documentation
├── functions/                   # Backend/serverless functions
├── infra/                       # Infrastructure and Azure configuration
├── quizgen/                     # AI-powered quiz generation
├── scripts/                     # Development and deployment scripts
├── src/                         # Application source code
├── tests/                       # Automated tests
├── web-app/                     # Web application
├── web/                         # Web-related application components
├── .github/
│   └── workflows/               # GitHub Actions workflows
├── azure-pipelines-backend.yml  # Backend CI/CD pipeline
├── azure-pipelines-frontend.yml # Frontend CI/CD pipeline
├── requirements.txt             # Python dependencies
└── .env.example                 # Environment variable template
```


## Architecture

Ascend was designed as a cloud-connected application with separate frontend, backend, database, AI, and infrastructure components.

```text
                    ┌──────────────────┐
                    │     Web App      │
                    │    Frontend     │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │   API / Backend  │
                    └───────┬───┬──────┘
                            │   │
                 ┌──────────┘   └──────────┐
                 ▼                         ▼
        ┌─────────────────┐       ┌─────────────────┐
        │    Database     │       │   AI Services   │
        │ Employee / Data │       │ Chatbot / Quiz  │
        └─────────────────┘       └─────────────────┘
                            │
                            ▼
                    ┌──────────────────┐
                    │  Azure Resources │
                    │  & Deployment    │
                    └──────────────────┘
```


## Data model

Ascend organizes data around employees, teams, training, quizzes, and performance tracking.

```text
Employee
├── id
├── name
├── email
├── role
└── teamId

Team
├── id
├── name
└── employeeIds

Training
├── id
├── title
├── description
├── documents
└── completionStatus

Quiz
├── id
├── trainingId
├── questions
├── answers
└── score

Performance
├── employeeId
├── attendance
├── quizScores
├── trainingProgress
└── points

Certification
├── id
├── employeeId
├── trainingId
├── status
└── completionDate
