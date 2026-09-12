# 🚀 LeadForge AI

### AI-Powered B2B Lead Discovery & Qualification Platform

LeadForge AI is an early-stage sales intelligence platform designed to transform natural-language prospecting requirements into structured B2B leads.

Instead of manually searching across multiple sources, users can describe the type of prospects they are looking for, and LeadForge orchestrates the discovery and qualification workflow.

---

## 🎯 Problem

Finding relevant B2B prospects often requires:

- Manual searching
- Repetitive data collection
- Multiple lead-generation tools
- Identifying whether a business is actually relevant
- Manually qualifying prospects

LeadForge AI aims to automate this workflow through API integrations, workflow orchestration, and AI-powered qualification.

---

## 💡 What LeadForge Does

A user provides a prospecting requirement such as:

> Find sales-related businesses in Hyderabad

LeadForge processes the request through an automated workflow:

User Search Request
        ↓
Intent / Search Parameters
        ↓
Google Places API
        ↓
Business Lead Extraction
        ↓
Lead Normalization
        ↓
AI Lead Qualification
        ↓
Lead Scoring
        ↓
Qualified Leads

---

## 🏗️ Current MVP Architecture

┌──────────────────────┐
│   User Search Form   │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│      Edit Fields     │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│   Google Places API  │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│       Split Out      │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│  Lead Normalization  │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ AI Lead Qualification│
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│ Qualification Parser │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│   Lead Qualification │
└──────────┬───────────┘
           ↓
┌──────────────────────┐
│  Qualified Leads     │
└──────────────────────┘

---

## ⚙️ Current Features

### 🔎 Business Lead Discovery

Uses the Google Places API to discover businesses based on search requirements and location.

### 🧹 Lead Normalization

Converts raw API results into a consistent lead structure.

Example:

{
  "company_name": "Example Business",
  "address": "Hyderabad, Telangana",
  "google_maps_url": "Google Maps URL",
  "source": "google_maps"
}

### 🤖 AI Lead Qualification

Google Gemini is used as the qualification layer to evaluate whether a discovered business is relevant to the requested prospecting criteria.

The qualification engine considers:

- Business relevance
- Location relevance
- Potential B2B suitability
- Niche matching
- Lead score

### 📊 Lead Scoring

Leads can be classified using a score-based qualification system:

80–100 → High
50–79  → Medium
0–49   → Low

---

## 🛠️ Technology Stack

| Technology | Purpose |
|------------|---------|
| n8n | Workflow orchestration |
| Google Places API | Business discovery |
| Google Gemini | AI lead qualification |
| REST APIs | External service integration |
| JSON | Structured lead data |

---

## 🔌 Provider-Based Architecture

LeadForge is designed with a modular provider architecture.

The long-term architecture is:

                 ┌── Google Places
                 │
User Intent ──→ Search Orchestrator ──→ Lead Sources
                 │
                 ├── Apollo
                 │
                 └── Other Providers
                           ↓
                  Entity Normalization
                           ↓
                    AI Qualification
                           ↓
                       Scoring
                           ↓
                         Leads

This architecture allows additional data providers to be integrated without redesigning the entire system.

---

## 🔮 Roadmap

Future versions are planned to include:

- [ ] Natural-language intent extraction
- [ ] Apollo People Search integration
- [ ] Additional lead providers
- [ ] Company enrichment
- [ ] Contact enrichment
- [ ] LinkedIn-based prospect discovery
- [ ] PostgreSQL lead database
- [ ] Lead search and filtering
- [ ] Saved searches
- [ ] Lead lists
- [ ] Company profiles
- [ ] Lead detail pages
- [ ] CSV export
- [ ] Automated prospecting workflows
- [ ] Authentication and multi-user support
- [ ] Production deployment

---

## ⚠️ Current MVP Limitations

This repository represents an early-stage MVP/prototype.

The current implementation primarily demonstrates business discovery through Google Places and the architecture for AI-powered qualification.

Some planned integrations and production features are not yet implemented.

API credentials, tokens, and other secrets are intentionally not included in this repository.

---

## 🧠 Engineering Focus

The project explores practical implementation of:

- API integration
- Workflow automation
- AI-assisted decision making
- Structured data transformation
- Lead qualification
- Modular provider architecture
- Prompt engineering
- B2B sales intelligence systems
- Automated prospect discovery

---

## 📂 Repository Contents

LEAD_GENERATION/
│
├── LeadForge AI.json
│   └── n8n workflow exported from the LeadForge AI MVP
│
└── README.md
    └── Project documentation

---

## 🚀 Getting Started

### 1. Clone the repository

git clone https://github.com/shyamkumar2202/LEAD_GENERATION.git

### 2. Import the workflow into n8n

Open your n8n instance and use:

Import Workflow → Import from File

Select:

LeadForge AI.json

### 3. Configure credentials

Configure your own credentials for:

- Google Places API
- Google Gemini

Do not place API keys directly inside the workflow or repository.

### 4. Execute the workflow

Provide a business niche and location through the input form and execute the workflow.

---

## 🔐 Security

Never commit:

- API keys
- Access tokens
- Passwords
- .env files
- Private credentials
- Service account keys

Use n8n's credential management or environment variables for sensitive information.

---

## 📸 Workflow

The current MVP is implemented as an n8n automation workflow connecting business discovery with AI-powered lead qualification.

The workflow is designed to evolve into a larger sales intelligence platform with multiple data providers and enrichment services.

---

## 🔭 Future Vision

The long-term goal of LeadForge AI is to evolve into an Apollo-inspired B2B sales intelligence platform where users can:

Describe their ideal prospects
          ↓
AI understands the intent
          ↓
Multiple data providers search for prospects
          ↓
Entities are normalized
          ↓
Businesses & people are enriched
          ↓
AI evaluates buying relevance
          ↓
Leads are scored
          ↓
Users discover qualified prospects

---

## 👨‍💻 Author

### Shyam Kumar

Building LeadForge AI as an exploration into AI-powered sales intelligence, workflow automation, API orchestration, and B2B prospect discovery.

---

## ⭐ Project Status

**Status:** 🚧 Early-stage MVP / Active Development

LeadForge AI is continuously evolving from a workflow-based prototype toward a full-featured B2B sales intelligence platform.

---
