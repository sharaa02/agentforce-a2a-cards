# agentforce-a2a-cards
# 🤖 HVAC AgentForce A2A Demo

This project demonstrates a cross-org Agent-to-Agent (A2A) interaction between two Salesforce AgentForce agents:

- **SmartQuotingAgent** (hosted in Org 1)
- **FinancingAgent** (hosted in Org 2)

The agents collaborate to guide customers through HVAC product selection, quote generation, and financing options—using the A2A protocol and public Salesforce Sites as webhook endpoints.

---

## 🧠 Agents Overview

### 🔹 SmartQuotingAgent
- Evaluates customer profiles (purchase history, LTV, sentiment) to determine quote-readiness.
- Recommends HVAC products based on environmental and budget preferences.
- Generates a quote and offers to route the customer to financing if needed.
- Hosted at: `[https://in1749020246754-dev-ed.develop.my.salesforce-sites.com](https://in1749020246754-dev-ed.develop.my.salesforce.com/)`

### 🔹 FinancingAgent
- Receives quote handoffs and analyzes credit history.
- Presents tailored loan options.
- Logs the selected financing plan and generates a customer reference ID.
- Hosted at: `[https://in1749822082981.my.salesforce-sites.com](https://in1749822082981.my.salesforce.com/)`

---

## 🔗 Agent Cards

Agent metadata is published in [`agent-cards.json`](agent-cards.json), which includes:

- Agent name and description
- Capabilities (`task/send`, `task/status`)
- Webhook callback URLs
- Authentication type (none for demo)

---

## 🛠️ Webhook Setup

Each agent exposes a public webhook via Salesforce Sites:

- SmartQuotingAgent:  
  `https://in1749020246754-dev-ed.develop.my.salesforce-sites.com/services/apexrest/agentforce/quotingwebhook`

- FinancingAgent:  
  `https://in1749822082981.my.salesforce-sites.com/services/apexrest/agentforce/financingwebhook`

Apex classes handle incoming A2A callbacks.

---

## 🧪 Demo Flow

1. SmartQuotingAgent finalizes a quote and sends a `task/send` to FinancingAgent via Mulesoft (https://agentforce-hackathon-4sb3kn.5sc6y6-2.usa-e2.cloudhub.io).
2. FinancingAgent processes the request and responds via `task/status`.
3. SmartQuotingAgent receives the callback and displays financing options.

---

## 🚀 Try It Out

- View the [Agent Cards](agent-cards.json)
- Explore the [Landing Page]([agent-cards.json](https://sharaa02.github.io/agentforce-a2a-cards/))
- Explore the [Landing Page]([[https://<your-username>.github.io/<repo-name>/](https://sharaa02.github.io/agentforce-a2a-cards/)])
- Use Postman to simulate A2A requests

---

## 🏁 Built With

- Salesforce AgentForce
- Apex REST APIs
- Mulesoft
- GitHub Pages

---

## 📬 Contact

For questions or collaboration, reach out to [Amit Sharan] at [your.email@example.com].
