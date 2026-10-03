# Smart Schedule AI Agent

> An AI-powered scheduling assistant built with **n8n** that lets users manage calendar events and email through natural-language messages on Telegram.

## 🎯 Business Problem

Managing a schedule can involve switching between messaging apps, calendars, and email to complete simple tasks.

This project turns those actions into a conversational workflow. Instead of manually creating a calendar event or composing an email, the user can describe what they want through Telegram and let the AI agent handle the appropriate action.

## 🏗️ Architecture

```text
                         User
                          │
                          ▼
                    ┌───────────┐
                    │ Telegram  │
                    └─────┬─────┘
                          │
                          ▼
                  ┌────────────────┐
                  │   n8n AI Agent │
                  └───────┬────────┘
                          │
              ┌───────────┼───────────┐
              │           │           │
              ▼           ▼           ▼
        OpenAI Model    Memory    Tool Selection
                                      │
                              ┌───────┴───────┐
                              │               │
                              ▼               ▼
                       Google Calendar      Gmail
                         Create Event      Send Email
                              │               │
                              └───────┬───────┘
                                      ▼
                                Telegram Reply
```

## ⚙️ How It Works

1. The user sends a natural-language request through Telegram.
2. The Telegram trigger passes the message to the n8n AI Agent.
3. The OpenAI chat model interprets the request.
4. Conversational memory maintains context across messages.
5. The AI Agent selects the appropriate tool based on the request.
6. Google Calendar creates an event when scheduling is requested.
7. Gmail sends an email when an email action is requested.
8. The workflow sends the result back to the user through Telegram.

## 🧰 Tech Stack

- **n8n** — workflow orchestration
- **n8n AI Agent** — agent and tool orchestration
- **OpenAI GPT-5-mini** — language model
- **Telegram** — conversational interface
- **Google Calendar** — calendar automation
- **Gmail** — email automation
- **Simple Memory** — conversational context
- **AI Tool Calling** — connecting the agent to external actions

## 👨‍💻 My Contribution

I designed and built the workflow end-to-end in n8n. I configured the AI Agent and OpenAI model, added conversational memory, connected Google Calendar and Gmail as agent tools, and built the Telegram input and response flow.

## 💬 Example Requests

### Calendar

**User:**

> Schedule a project review tomorrow from 4 PM to 5 PM.

**Workflow:**

```text
Natural-language request
        ↓
    AI Agent
        ↓
Extract event details
        ↓
Google Calendar
        ↓
Telegram confirmation
```

### Email

**User:**

> Send an email to Alex saying our project review is tomorrow at 4 PM.

**Workflow:**

```text
Natural-language request
        ↓
    AI Agent
        ↓
Extract recipient, subject and message
        ↓
      Gmail
        ↓
Telegram confirmation
```

## 📊 Result

The workflow turns natural-language requests into actions across multiple productivity tools, reducing the need to manually switch between applications.

The project demonstrates:

- AI agent orchestration
- Tool calling
- Conversational memory
- Workflow automation
- External service integration
- Natural-language interfaces

## 🎥 Demo

**Loom:** Add demo link here

## 📂 Repository Structure

```text
smart-schedule-ai-agent/
├── README.md
├── .gitignore
├── architecture/
│   └── architecture.md
├── docs/
│   └── setup.md
├── examples/
│   └── example-interactions.md
└── workflows/
    └── smart-schedule.json
```

## 🚀 Setup

1. Import `workflows/smart-schedule.json` into your n8n instance.
2. Configure credentials for:
   - Telegram
   - OpenAI
   - Google Calendar
   - Gmail
3. Configure your Google Calendar.
4. Configure the Telegram trigger.
5. Test the workflow with a simple calendar or email request.
6. Activate the workflow after testing.

See [`docs/setup.md`](docs/setup.md) for additional setup notes.

## 🔐 Security

The workflow export in this repository has been sanitized for public sharing.

Do **not** commit:

- API keys
- OAuth tokens
- Telegram bot tokens
- Gmail credentials
- Google Calendar credentials
- `.env` files
- Private webhook URLs

## 📄 Workflow

The sanitized n8n workflow is available at:

[`workflows/smart-schedule.json`](workflows/smart-schedule.json)

---

Built as an AI automation project demonstrating how an AI agent can connect natural-language conversations with real productivity tools.
