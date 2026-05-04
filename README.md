# AI Marketing Campaign Generator

A browser-based marketing tool that uses a locally-run Ollama LLM to generate personalized outbound campaigns. Built as a demo for a financial services use case (Home Credit Bank Kazakhstan), the tool covers campaign creation, a campaign queue, and an analytics dashboard.

## Features

**Campaign Builder**
Configure and generate personalized marketing messages powered by a local Ollama LLM. Settings include:
- **AI Parameters** — Adjustable temperature and top-p values to control generation style
- **Campaign Settings** — Channel (Email, SMS, Push Notification), product, start date, word limit, and language (English or Kazakh)
- **Brand Guidelines** — Persistent brand voice and compliance instructions injected into every prompt
- **Customer Profiles** — A sample audience table (name, age, account type, income, credit score, spending habits) used to personalize each generated message
- Generated campaigns display a subject line and full message body, and are saved to the browser via localStorage

**Campaign Queue**
Stores sent campaigns from the builder. Each entry shows recipient count, channel, and start date. Generated campaigns display individual subject lines and allow direct editing of the first email body.

**Dashboard**
Static analytics view intended to track campaign volume, types, costs, and engagement metrics. Charts were generated using Matplotlib in a Jupyter Notebook.

## Tech Stack

| Layer | Technology |
|---|---|
| Structure | HTML |
| Styling | CSS |
| Functionality | JavaScript |
| AI Generation | Ollama (local LLM via REST API) |
| Data Persistence | localStorage |
| Dashboard Charts | Python · Matplotlib · Jupyter Notebook |

## Running the Project

Ollama must be running locally for message generation to work. Start it with:

```bash
ollama serve
```

Then open any `.html` file directly in your browser. No server setup required.

## Notes

- The dashboard and parts of the campaign queue use static data to simulate a live environment
- The builder connects to `http://localhost:11434/api/generate` to call the Ollama API
