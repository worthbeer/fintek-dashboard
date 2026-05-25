# Fintek Dashboard

A financial dashboard built to explore production-grade fintech integrations — Plaid for bank account linking, Dwolla for ACH payment transfers, and Appwrite as the backend. Built while working through how these APIs fit together in a real banking product.

---

## What It Explores

| Integration | Role |
|---|---|
| **Plaid** | OAuth bank account linking, transaction history, balance data |
| **Dwolla** | ACH fund transfers between linked accounts |
| **Appwrite** | Auth, database, and server-side session management |
| **Sentry** | Error monitoring and performance tracking |
| **Chart.js** | Transaction category breakdowns and spending visualizations |

The goal was understanding how a fintech product wires together identity, bank connectivity, and payment rails — not just calling one API but seeing how the three layers interact.

---

## Stack

| Layer | Technology |
|---|---|
| Framework | Next.js 14 App Router |
| Language | TypeScript 5 (strict) |
| Styling | Tailwind CSS + Radix UI |
| Auth + Backend | Appwrite |
| Bank Linking | Plaid SDK + react-plaid-link |
| Payments | Dwolla v2 |
| Visualization | Chart.js + react-chartjs-2 |
| Forms | React Hook Form + Zod |
| Monitoring | Sentry |

---

## Status

This is a sandbox-state learning project. Plaid and Dwolla are connected to test environments with pre-seeded accounts. The dashboard layout and navigation are in place; some components are scaffolded but not fully wired to live API responses.

What works: auth flow, Plaid Link integration, sidebar navigation, transaction category styling, spending breakdown structure.

---

## Running Locally

Requires Appwrite, Plaid sandbox credentials, and Dwolla sandbox credentials.

Create a `.env.local` file in the project root:

```
APPWRITE_PROJECT_ID=
APPWRITE_DATABASE_ID=
APPWRITE_USER_COLLECTION_ID=
APPWRITE_BANK_COLLECTION_ID=
APPWRITE_TRANSACTION_COLLECTION_ID=
APPWRITE_SECRET=

PLAID_CLIENT_ID=
PLAID_SECRET=
PLAID_ENV=sandbox

DWOLLA_KEY=
DWOLLA_SECRET=
DWOLLA_BASE_URL=https://api-sandbox.dwolla.com
DWOLLA_ENV=sandbox

NEXT_PUBLIC_SITE_URL=http://localhost:3000
```

```bash
npm install
npm run dev
```

---

## Skills Demonstrated

- Integrating regulated financial APIs (Plaid, Dwolla) with proper OAuth flows
- Appwrite as a BaaS alternative to a custom backend — auth, collections, and server-side sessions
- Structuring a multi-service integration where each layer has distinct credentials and environments
- Tailwind design system with custom category color tokens
- Sentry wired in from the start, not added as an afterthought
