# My-Portfolio

<div align="center">

# ⚡ csalioha.com.ng

### My personal portfolio, built with AI, powered by Next.js, and editable without touching code.

**From the helpdesk to the cloud.**

[🌐 Live Site](https://csalioha.com.ng) · [▲ Vercel Deployment](https://personal-site-nu-sandy.vercel.app/) · [💼 LinkedIn](https://www.linkedin.com/in/chigoziealioha) · [🐙 GitHub](https://github.com/chigozieali)

![Next.js](https://img.shields.io/badge/Next.js-black?style=for-the-badge&logo=nextdotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![AI Assisted](https://img.shields.io/badge/Built%20with-AI-8A2BE2?style=for-the-badge)
![Custom Domain](https://img.shields.io/badge/Domain-csalioha.com.ng-success?style=for-the-badge)

</div>

---

## 🚀 What is this?

This is the source code for my personal portfolio site: a fast, modern, database-backed Next.js app that tells the story of my move from **5+ years of IT support** to **Azure Cloud Engineering**.

It isn't a static page. Everything on it, from the headline and "Right now" status to the projects, skills, certificates and services, is stored in **PostgreSQL** and managed from a built-in **Site Settings** panel. When I earn a new certificate or finish a lab, I update it from the browser. No redeploy, no code edits.

> **Built with AI as a co-pilot.** I used AI-assisted development to design, scaffold and iterate on this site, then reviewed, tested and shipped it myself. It's a real example of how I work: use the best tools, understand what they produce, and deliver.

---

## ✨ Features

| | Feature | Details |
|---|---|---|
| ⚙️ | **Site Settings panel** | Update hero text, status, stats, projects, skills, certificates and services from a settings page |
| 🤖 | **Built-in AI content assistant** | Writes, rewrites and polishes site content right inside Site Settings |
| 🗄️ | **PostgreSQL-backed content** | Content lives in a database, not hard-coded in components |
| 🌗 | **Clean, responsive design** | Looks sharp on phones, tablets and desktops |
| 📬 | **Contact form** | Visitors can reach me directly from the site |
| 🔎 | **SEO-ready** | Meta description, titles and semantic structure for search engines |
| 🔒 | **HTTPS by default** | Automatic SSL through Vercel on a custom `.com.ng` domain |
| 🔁 | **Continuous deployment** | Push to `main` and Vercel builds and ships it |

---

## 🧱 Tech Stack

- **Framework:** [Next.js](https://nextjs.org/) (React)
- **Database:** PostgreSQL
- **AI Assistant:** LLM-powered content writing and editing, integrated into the admin panel
- **Hosting:** [Vercel](https://vercel.com/)
- **Domain & DNS:** Custom domain `csalioha.com.ng` connected to Vercel (see my [domain setup guide](https://github.com/chigozieali/Connecting-a-Vercel-Deployment-to-a-Custom-Domain))
- **Workflow:** AI-assisted development, Git & GitHub

---

## 🗺️ Architecture

```
            ┌──────────────────────┐
 Visitor ──▶│  csalioha.com.ng     │  (custom domain + HTTPS)
            └──────────┬───────────┘
                       │ DNS → Vercel
                       ▼
            ┌──────────────────────┐
            │   Next.js on Vercel  │◀── GitHub push (auto deploy)
            └──────────┬───────────┘
                       │ reads / writes
                       ▼
            ┌──────────────────────┐
            │      PostgreSQL      │  site content & settings
            └──────────────────────┘
                       ▲
                       │ edits content
            ┌──────────┴───────────┐      ┌──────────────────────┐
   Me ─────▶│    Site Settings     │─────▶│  AI Content Assistant │
            │ (protected admin)    │◀─────│  write · rewrite · polish │
            └──────────────────────┘      └──────────────────────┘
```

---

## 🤖 AI Content Assistant

The site ships with its own **AI assistant for writing and modifying content**, so keeping the portfolio fresh takes minutes instead of hours.

**What it can do**
- ✍️ **Draft** new copy: project descriptions, service blurbs, "About" text
- 🔧 **Rewrite** existing content: tighten, change tone, fix grammar, simplify jargon
- 🎯 **Tailor** wording for a specific audience, such as recruiters or clients
- ⚡ **Apply changes** to site content from the Site Settings panel, with me reviewing before anything goes live

**How it works**
1. I open a section in Site Settings (for example a project description).
2. I give the assistant an instruction like *"make this more concise and results-focused."*
3. The assistant returns a suggestion.
4. I review, edit if needed, and save. The change is written to PostgreSQL and the live site updates.

**Design principles**
- 🧑‍💻 **Human in the loop:** AI suggests, I approve. Nothing is published automatically.
- 🔐 **Protected:** the assistant is only available inside the authenticated admin area, and the API key stays server-side.
- 🎛️ **Scoped:** it works on my site's content, not as a general-purpose chatbot for visitors.

---

## 📄 What's on the Site

- **Hero:** who I am, what I'm doing right now, key stats
- **About & Experience:** the story from helpdesk to cloud
- **Services:** helpdesk support, network setup, reporting tools, websites and web apps
- **Skills:** Cloud, Infrastructure, Networking, Support, Build
- **Certificates:** Google IT Support, Cisco, and the Azure roadmap (AZ-900 → AZ-104 → Security+)
- **Projects:** Azure labs, networking, web apps and my home lab
- **Contact:** a direct line for roles and projects

---

## 🛠️ Run It Locally

### Prerequisites
- Node.js 18+ and npm
- A PostgreSQL database (local, or a hosted one such as Neon, Supabase or Vercel Postgres)

### 1. Clone the repo
```bash
git clone https://github.com/chigozieali/<your-repo-name>.git
cd <your-repo-name>
```

### 2. Install dependencies
```bash
npm install
```

### 3. Configure environment variables
Create a `.env.local` file in the project root:

```env
# Database
DATABASE_URL="postgresql://USER:PASSWORD@HOST:5432/DATABASE"

# Admin / Site Settings protection
ADMIN_PASSWORD="choose-a-strong-password"

# AI content assistant (use the variable name your provider/code expects)
AI_API_KEY="your-ai-provider-api-key"

# Add any other variables your project uses (auth secret, email provider keys, etc.)
```

> 🔐 Never commit `.env.local`. It's already in `.gitignore`.

### 4. Set up the database
Run your migrations or seed script to create the tables and add starter content (use whichever command your project defines, for example `npm run db:migrate` and `npm run db:seed`).

### 5. Start the dev server
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000).

---

## ☁️ Deploy Your Own

1. Push the repo to GitHub.
2. Import it into [Vercel](https://vercel.com/new).
3. Add your environment variables (`DATABASE_URL`, `ADMIN_PASSWORD`, `AI_API_KEY`, etc.) under **Settings → Environment Variables**.
4. Deploy, then add your custom domain under **Settings → Domains**.
5. Update your DNS records at your registrar and wait for HTTPS to activate.

Full walkthrough: [Connecting a Vercel Deployment to a Custom Domain](https://github.com/chigozieali/Connecting-a-Vercel-Deployment-to-a-Custom-Domain).

---

## 📁 Project Structure

```
.
├── app/ (or pages/)      # Routes and pages
├── components/           # Reusable UI sections (Hero, Projects, Skills...)
├── lib/                  # Database client and helpers
├── public/               # Static assets
├── .env.local            # Local secrets (not committed)
└── package.json
```
*(Adjust to match your repo's actual layout.)*

---

## 🧠 What I Learned

- Designing a content model so a site can be updated without redeploying
- Connecting a managed PostgreSQL database to a serverless Next.js app
- Integrating an LLM into a real app: prompt design, keeping API keys server-side, and keeping a human approval step
- Handling environment variables safely across local, preview and production
- Pointing a `.com.ng` domain at Vercel: A/CNAME records, propagation and SSL
- Using AI as a force multiplier while still reviewing, testing and owning the result

---

## 🔭 Roadmap

- [ ] Blog / write-ups for my Azure labs, drafted with the AI assistant
- [ ] Version history and one-click undo for AI-edited content
- [ ] Dark / light theme toggle
- [ ] Analytics dashboard in Site Settings
- [ ] Case-study pages for each project

---

## 📬 Let's Connect

I'm open to **cloud and IT support roles, remote worldwide**.

- 🌐 [csalioha.com.ng](https://csalioha.com.ng)
- 💼 [LinkedIn](https://www.linkedin.com/in/chigoziealioha)
- 🐙 [GitHub](https://github.com/chigozieali)

---

<div align="center">

**Chigozie Alioha** · IT Support → Cloud Engineer · Nigeria 🇳🇬

*Built with Next.js, PostgreSQL, Vercel and a lot of curiosity.*

© 2026 Chigozie Alioha. All rights reserved.

</div>
