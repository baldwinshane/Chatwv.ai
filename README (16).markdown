# KanawhaAI: Matrix-Based Email Platform with Appalachian AI Assistant

## Overview
**KanawhaAI** is a privacy-focused email platform built on the [Matrix.org protocol](https://matrix.org), integrated with a Grok 3-powered **KanawhaAI Assistant** chatbot and search engine, featuring a warm, folksy Appalachian personality (e.g., “y’all,” “fixin’ to”). Hosted on [kanawha.ai](https://kanawha.ai), it rivals Gmail with decentralized messaging, unlimited searches, 30 minutes of daily chat, and 50 emails/day for free-tier users, and unlimited access for premium users at $32.99/month. Developed by **Matrix LLC** in West Virginia, the platform scales to 60 million users within a $500/month initial budget, with revenue from ads ($5/CPM), subscriptions, and the **KanawhaAI API** ($0.001/request). iOS/Android apps (`KanawhaAI Email`, `KanawhaAI Assistant`) are planned. A **Genuine Indian** chatbot model, inspired by cultural heritage and designed with sensitivity, is coming soon (in development, details TBD).

## Features
- **Email Platform**: Gmail-like UI with Matrix SSO (`@username:kanawha.ai`), SMTP bridge for Gmail interoperability, and AI-driven features (smart replies, spam detection).
- **KanawhaAI Assistant**: Grok 3 Mini-powered chatbot with Appalachian tone, offering chat and search (unlimited for free tier).
- **KanawhaAI API**: Developer access for search, chat, and email integration ($0.001/request, $50–$500/month subscriptions).
- **Genuine Indian Model**: Coming soon, a culturally inspired AI model (details TBD, developed with community input to ensure respect for Native American and South Asian heritage).
- **Monetization**:
  - Free Tier: Ads in email app and search results.
  - Premium Tier: Ad-free, unlimited usage ($32.99/month).
  - API: $25/month free credits for testing.
- **Scalability**: Supports 1,000 to 60M users with RunPod infrastructure.
- **Privacy**: End-to-end encryption (Matrix Olm/Megolm), GDPR/CCPA-compliant.

## Tech Stack
- **Frontend**: React, Tailwind CSS, Matrix JS SDK (`index.html`, artifact ID `8e01fedb-49cd-497a-ad97-aae10233145c`).
- **Backend**: Node.js, Express, Redis (`chatbot-backend.js`, artifact ID `9d619758-d93f-4188-9f8a-6fd5efca363b`).
- **Matrix**: Synapse homeserver for federation and SSO.
- **AI**: xAI Grok 3 Mini API ($0.35/$0.55 per million input/output tokens).
- **Infrastructure**: RunPod (Synapse, SMTP bridge, web app, storage), Qdrant for real-time search.
- **Mobile**: React Native (planned iOS/Android apps).
- **Domain**: `kanawha.ai` for branding and Matrix server.

## Prerequisites
- Node.js v18+
- Redis server (RunPod-hosted)
- xAI API key (`console.x.ai`, $25/month free credits)
- RunPod account
- Matrix Synapse server
- Domain: `kanawha.ai` (~$50–$90/year)

## Installation
1. **Clone Repository**:
   ```bash
   git clone https://github.com/matrix-llc/kanawha-ai.git
   cd kanawha-ai
   ```
2. **Install Dependencies**:
   ```bash
   npm install
   ```
3. **Configure Environment**:
   - Create `.env` file:
     ```env
     XAI_API_KEY=your_xai_api_key
     REDIS_HOST=your-runpod-redis-host
     REDIS_PORT=6379
     REDIS_PASSWORD=your-redis-password
     MATRIX_SERVER=https://kanawha.ai
     ```
4. **Set Up Synapse**:
   - Deploy Synapse on RunPod (~$0.02/hr).
   - Configure `homeserver.yaml` with `server_name: kanawha.ai`.
   - Enable OAuth2 for SSO.
5. **Set Up SMTP Bridge**:
   - Deploy on RunPod (~$0.01/hr).
   - Configure Matrix-to-SMTP mapping.
6. **Deploy Web App**:
   - Host React app on RunPod or Vercel (~$20/month).
   - Update `index.html` with `kanawha.ai` endpoints.
7. **Start Backend**:
   ```bash
   node chatbot-backend.js
   ```
8. **Domain Setup**:
   - Register `kanawha.ai` (GoDaddy/Dynadot, ~$50–$90/year).
   - Configure SRV (`_matrix._tcp.kanawha.ai`) and MX records.
   - Use Let’s Encrypt TLS via Caddy.

## Usage
- **Web App**: Access at `https://kanawha.ai`.
  - Sign in with Matrix ID (`@username:kanawha.ai`).
  - Free Tier: Unlimited searches, 30 min chat/day, 50 emails/day.
  - Premium Tier: Unlimited access ($32.99/month via Stripe).
- **KanawhaAI Assistant**:
  - Chat: `POST /chat` with prompt (e.g., “What’s the weather in Charleston, WV?”).
  - Search: `POST /search` with query (e.g., “Kanawha River history”).
- **KanawhaAI API**:
  - Endpoints: `/chat`, `/search`, `/email/send`.
  - Auth: Matrix OAuth2 token.
  - Docs: `https://api.kanawha.ai/docs` (planned).
- **Genuine Indian Model**: Coming soon, pending cultural consultation.
- **Mobile Apps**: Planned for iOS/Android (React Native, Q1 2026).

## Budget and Revenue
- **Initial (1,000 users)**:
  - Cost: ~$244.60–$247.93/month (API $150.725, infrastructure $65.77–$69.10, LLC $18.75).
  - Revenue: $714.945/month (ads $5.145, subscriptions $659.80, API $50).
  - Surplus: $467.02–$470.35/month.
- **60M Users**:
  - Cost: ~$14.5M/month (API $14.33916M, infrastructure $154,858.33).
  - Revenue: $348.563M/month (ads $308.7M, subscriptions $39.588M, API $0.275M).
- **No Debt**: Shutdown protocols cap API usage ($150.725/month).

## Development Roadmap
- **Q3 2025**: Launch with 1,000 users, deploy `kanawha.ai`.
- **Q4 2025**: Scale to 5,000–1M users, add Qdrant, plan Genuine Indian model.
- **Q1 2026**: Release iOS/Android apps ($5,000–$10,000).
- **2026–2027**: Reach 60M users, launch Genuine Indian model post-consultation.

## Contributing
- Fork the repository.
- Submit pull requests to `main` branch.
- Follow code style (ESLint, Prettier).

## License
- **KanawhaAI**: Apache 2.0 (Matrix components), proprietary for custom code.
- **Genuine Indian Model**: Common law copyright notice (see [LICENSE_GENUINE_INDIAN.md](#)) applies, pending development.

## Contact
- Matrix LLC, West Virginia
- Email: support@kanawha.ai
- Matrix: @admin:kanawha.ai
- X: @KanawhaAI

**Disclaimer**: The Genuine Indian model is in development and will be designed with cultural sensitivity, in consultation with Native American and South Asian communities, to avoid misrepresentation.