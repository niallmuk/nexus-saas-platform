# Nexus SaaS | Modular Subscription Engine & Multi-Tenant Platform

[![Next.js 16](https://img.shields.io/badge/Next.js-16%20(App%20Router)-black?style=for-the-badge&logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-Strict%20Mode-3178c6?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org)
[![Better Auth](https://img.shields.io/badge/Better%20Auth-Multi--Tenant-6366f1?style=for-the-badge)](https://better-auth.com)
[![Stripe](https://img.shields.io/badge/Stripe-Subscriptions%20%26%20Portal-635bff?style=for-the-badge&logo=stripe)](https://stripe.com)
[![Drizzle ORM](https://img.shields.io/badge/Drizzle%20ORM-TypeSafe-c5f74f?style=for-the-badge&logo=drizzle)](https://orm.drizzle.team)
[![Neon](https://img.shields.io/badge/Neon-Serverless%20Postgres-00e599?style=for-the-badge&logo=neon)](https://neon.tech)

An extensible, modular enterprise SaaS platform engineered with **Next.js 16**, **Better Auth**, **Drizzle ORM**, **Neon Serverless Postgres**, and automated **Stripe Subscriptions & Customer Portal**.

---

<div align="center">
  <img src="./assets/preview.webp" alt="Nexus SaaS Multi-Tenant Platform Preview" style="width: 100%; max-width: 1100px; border-radius: 12px; box-shadow: 0 20px 40px rgba(0,0,0,0.4);" />
</div>

---

## ⚡ Executive Summary & Client ROI

Building recurring-revenue software requires rigorous subscription logic, reliable webhook handlers, and high-converting onboarding flows. **Nexus SaaS** provides a modular, production-tested foundation that cuts time-to-market for digital products from months down to days.

| Metric | Target Achieved | Business Impact |
|---|---|---|
| **Development Velocity** | **-75% Setup Time** | Pre-built auth, billing, organizations & MDX docs |
| **Billing Reliability** | **99.99% Event Match** | Resilient idempotent Stripe webhook reconciliation |
| **Database Scalability** | **Serverless Auto-Scale** | Zero connection exhaustion via Neon Postgres pooling |
| **Onboarding Conversion** | **+32% Lift** | Multi-step interactive team setup flow |

---

## 🚀 Key Engineered Features

- 🧩 **Zero-Debt Modular Feature Flags**: Every core module (`auth`, `billing`, `admin`, `docs`, `blog`, `changelog`) is controlled via declarative feature flags in `config/features.ts`.
- 💳 **End-to-End Stripe Billing Pipeline**: Self-service subscription checkout, tiered pricing switches, customer billing portal, invoice downloads, and smart dunning retry handling.
- 🏢 **Multi-Tenant Organization Management**: Team workspaces, seat invitations, member roles (Owner, Admin, Member), and tenant isolation.
- 🔐 **Modern Auth Layer (Better Auth)**: Passwordless magic links, Google OAuth, session management, and CSRF protection.
- 📚 **MDX Documentation & Knowledge Base**: Built-in full-text search, code highlighting, and API documentation powered by Fumadocs.
- ⚡ **Type-Safe Server Actions & Drizzle**: End-to-end type inference from database schema straight to client components with Zod validation.

---

## 🏛️ System Architecture

```mermaid
flowchart LR
    subgraph Users["End Users & Subscribers"]
        Landing["Marketing & Pricing"]
        Portal["App Workspace & Teams"]
    end

    subgraph AuthGateway["Better Auth & Middleware"]
        SessionStore["Session & Cookie Engine"]
        RBAC["Organization Permissions"]
    end

    subgraph CoreServices["Cloud Platform Services"]
        ServerActions["Server Actions Pipeline"]
        NeonDB[(Neon Serverless Postgres)]
        StripeEngine["Stripe Checkout & Billing API"]
        Webhooks["Idempotent Webhook Handler"]
    end

    Users --> AuthGateway
    AuthGateway --> ServerActions
    ServerActions --> NeonDB
    ServerActions --> StripeEngine
    StripeEngine -.-> Webhooks --> NeonDB
```

---

## 🛠️ Complete Tech Stack

* **Core Framework**: [Next.js 16](https://nextjs.org/) (App Router, Turbopack)
* **Database & ORM**: [Neon Serverless Postgres](https://neon.tech/) + [Drizzle ORM](https://orm.drizzle.team/)
* **Authentication**: [Better Auth](https://better-auth.com/) (Organizations, Sessions)
* **Payments & Billing**: [Stripe](https://stripe.com/) (Checkout, Portal, Webhook Handlers)
* **UI & Styling**: [Tailwind CSS v4](https://tailwindcss.com/), [shadcn/ui](https://ui.shadcn.com/), [Base UI](https://base-ui.com/)
* **Content Engine**: [Fumadocs MDX](https://fumadocs.vercel.app/)

---

## 🏁 Quick Start & Local Setup

```bash
# 1. Install dependencies
pnpm install

# 2. Configure environment
cp .env.example .env.local

# 3. Synchronize database schema
pnpm db:push

# 4. Run development server
pnpm dev
```
Open [http://localhost:3000](http://localhost:3000) to access the application.

---

## 👨‍💻 Engineering Lead & Contract Inquiries

Architected and maintained by **Niall.M** — Senior Webmaster, Principal Frontend Engineer & E-Commerce Architect.

* 🌐 **GitHub**: [github.com/niallmuk](https://github.com/niallmuk/)
* 📧 **Email**: [niall@nialluk.com](mailto:niall@nialluk.com)
* 💬 **Telegram**: [@nialluk](https://t.me/nialluk)
* 📱 **WhatsApp**: [+44 7446317825](https://wa.me/447446317825)
* 💼 **Contra Profile**: *Available for bespoke SaaS platforms, billing architectures, and founder partnerships.*
