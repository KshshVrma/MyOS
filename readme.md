\# MyOS – Personal AI Assistant



MyOS is a local-first personal AI assistant built to automate everyday tasks and provide conversational assistance through Telegram.



The initial prototype runs locally using an LLM hosted through Ollama, with n8n handling workflow orchestration and integrations.



\## Architecture



```text

Telegram

&#x20;  |

&#x20;  v

ngrok (Public HTTPS Tunnel)

&#x20;  |

&#x20;  v

n8n (Docker)

&#x20;  |

&#x20;  v

Llama 3.2 3B (Ollama)

&#x20;  |

&#x20;  v

Intent Detection \& Validation

&#x20;  |

&#x20;  +---- CREATE\_REMINDER --> Google Calendar

&#x20;  |

&#x20;  +---- CREATE\_TASK ------> Planned

&#x20;  |

&#x20;  +---- ASK\_QUESTION -----> LLM Response

&#x20;  |

&#x20;  +---- GENERAL\_CHAT -----> LLM Response

```



\## Tech Stack



\- \*\*Workflow Orchestration:\*\* n8n Community Edition

\- \*\*LLM Runtime:\*\* Ollama

\- \*\*Model:\*\* Llama 3.2 3B

\- \*\*Containerization:\*\* Docker Desktop

\- \*\*Messaging Interface:\*\* Telegram Bot API

\- \*\*Calendar Integration:\*\* Google Calendar API

\- \*\*Tunnelling:\*\* ngrok

\- \*\*Custom Logic:\*\* JavaScript



\## Current Progress



\- \[x] Local n8n deployment using Docker Compose

\- \[x] Ollama and Llama 3.2 3B integration

\- \[x] Telegram bot integration through ngrok

\- \[x] Natural language intent detection

\- \[x] JavaScript-based JSON parsing and validation

\- \[x] Date/time validation and IST-to-UTC conversion

\- \[x] Google Calendar event creation

\- \[x] Conversational responses through Telegram

\- \[ ] Task creation and persistent storage

\- \[ ] Conversation memory

\- \[ ] Calendar event querying and management

\- \[ ] Gmail integration



\## Local Setup



\### Prerequisites



\- Docker Desktop

\- Ollama

\- ngrok

\- Telegram Bot Token

\- Google Calendar OAuth credentials



\### Start Ollama



```bash

ollama pull llama3.2:3b

ollama run llama3.2:3b

```



\### Start n8n



```bash

docker compose up -d

```



Access n8n at:



`http://localhost:5678`



\### Expose n8n for Telegram webhooks



```bash

ngrok http 5678

```



Configure n8n's webhook URL using the generated HTTPS URL.



\## Project Goals



MyOS aims to evolve into a personal productivity assistant capable of:



\- Managing reminders and tasks.

\- Interacting with Google Calendar and Gmail.

\- Providing daily briefings.

\- Tracking learning and career goals.

\- Understanding natural language commands.



\*\*Current focus:\*\* Building a reliable local-first assistant before moving towards persistent storage, additional integrations, and eventual VPS deployment.

