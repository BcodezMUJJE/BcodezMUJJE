<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0D1117,50:1F6FEB,100:0D1117&height=240&section=header&text=Matege%20Billbright&fontSize=62&fontColor=FFFFFF&fontAlign=50&fontAlignY=42&desc=Full%20Stack%20Engineer%20%20%C2%B7%20%20Cybersecurity%20Analyst&descColor=8B949E&descSize=18&descAlign=50&descAlignY=62&animation=fadeIn" width="100%"/>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=17&duration=3500&pause=1000&color=58A6FF&center=true&vCenter=true&repeat=true&width=700&lines=Building+secure%2C+scalable%2C+type-safe+systems;Full+Stack+Engineering+%2B+Cybersecurity-aware+design;Next.js+%7C+TypeScript+%7C+Supabase+%7C+PostgreSQL;Production-grade+architecture+by+default)](https://git.io/typing-svg)

<br/>

<a href="mailto:billbrightmatege@gmail.com">
  <img src="https://img.shields.io/badge/Email-161B22?style=for-the-badge&logo=gmail&logoColor=EA4335" />
</a>&nbsp;
<a href="https://linkedin.com/in/YOUR_LINKEDIN">
  <img src="https://img.shields.io/badge/LinkedIn-161B22?style=for-the-badge&logo=linkedin&logoColor=0A66C2" />
</a>&nbsp;
<a href="https://YOUR_PORTFOLIO_URL">
  <img src="https://img.shields.io/badge/Portfolio-161B22?style=for-the-badge&logo=vercel&logoColor=FFFFFF" />
</a>&nbsp;
<a href="https://github.com/YOUR_USERNAME">
  <img src="https://img.shields.io/badge/GitHub-161B22?style=for-the-badge&logo=github&logoColor=FFFFFF" />
</a>

<br/><br/>

<img src="https://komarev.com/ghpvc/?username=YOUR_USERNAME&color=1F6FEB&style=flat-square&label=Profile+Views" />

</div>

<br/>

---

## Overview

This is my personal **developer portfolio system** — built as a production-grade, full-stack application to demonstrate engineering depth, not just visual design.

The architecture is intentionally layered around three principles: **end-to-end type safety**, **secure-by-default data access**, and **clean separation of concerns** between the UI, API, and database. Every decision reflects real engineering practice, not portfolio aesthetics.

---

## System Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                        CLIENT LAYER                          │
│    Next.js App Router  ·  React Server Components            │
│    TypeScript (strict)  ·  TailwindCSS  ·  Framer Motion     │
└──────────────────────────┬───────────────────────────────────┘
                           │  REST  ·  Realtime WebSocket
┌──────────────────────────▼───────────────────────────────────┐
│                         API LAYER                            │
│    Supabase Client SDK  ·  Next.js Server Actions            │
│    Type-safe query layer  ·  Edge-ready endpoints            │
└──────────────────────────┬───────────────────────────────────┘
                           │
┌──────────────────────────▼───────────────────────────────────┐
│                      DATABASE LAYER                          │
│    PostgreSQL  ·  Row Level Security  ·  Supabase Auth       │
│    Hosted on Supabase Cloud (global edge replicas)           │
└──────────────────────────┬───────────────────────────────────┘
                           │
┌──────────────────────────▼───────────────────────────────────┐
│                     INFRASTRUCTURE                           │
│    Vercel  ·  CI/CD  ·  Edge Network  ·  Preview Deploys     │
└──────────────────────────────────────────────────────────────┘
```

---

## Tech Stack

<div align="center">

**Frontend**

<img src="https://skillicons.dev/icons?i=nextjs,react,typescript,tailwind&theme=dark" />

**Backend & Data**

<img src="https://skillicons.dev/icons?i=supabase,postgres,nodejs&theme=dark" />

**Infrastructure & Tooling**

<img src="https://skillicons.dev/icons?i=vercel,github,git,vscode&theme=dark" />

</div>

<br/>

| Layer | Technology | Role |
|:------|:-----------|:-----|
| Framework | Next.js 14 (App Router) | SSR, SSG, routing, server actions |
| Language | TypeScript — strict mode | End-to-end type safety |
| Styling | TailwindCSS + Framer Motion | Responsive UI + animations |
| Backend | Supabase BaaS | Auth, realtime, storage, SDK |
| Database | PostgreSQL | Relational data enforced with RLS |
| Deployment | Vercel | Edge deployment, CI/CD, previews |

---

## Features

| Feature | Status |
|:--------|:------:|
| Dynamic project listing from Supabase | `live` |
| Contact form with secure backend storage | `live` |
| Responsive, mobile-first UI | `live` |
| Animated interface via Framer Motion | `live` |
| Full-stack TypeScript type safety | `live` |
| Row Level Security enforcement | `live` |
| Admin dashboard for content management | `planned` |
| Blog system with Markdown support | `planned` |
| Auth-protected CMS panel | `planned` |
| AI-powered portfolio assistant | `planned` |
| Advanced analytics dashboard | `planned` |
| Multi-theme support: dark / light / system | `planned` |

---

## Database Schema

```sql
-- Projects: dynamically rendered portfolio entries
CREATE TABLE projects (
  id          uuid         PRIMARY KEY DEFAULT gen_random_uuid(),
  title       text         NOT NULL,
  description text,
  tech_stack  text[],
  github_url  text,
  demo_url    text,
  image_url   text,
  created_at  timestamptz  DEFAULT now()
);

-- Messages: contact form submissions
CREATE TABLE messages (
  id         uuid         PRIMARY KEY DEFAULT gen_random_uuid(),
  name       text         NOT NULL,
  email      text         NOT NULL,
  message    text         NOT NULL,
  created_at timestamptz  DEFAULT now()
);

-- Security: restrict public write access via RLS
ALTER TABLE projects ENABLE ROW LEVEL SECURITY;
ALTER TABLE messages ENABLE ROW LEVEL SECURITY;

CREATE POLICY "Public read"  ON projects FOR SELECT USING (true);
CREATE POLICY "Insert only"  ON messages FOR INSERT WITH CHECK (true);
```

---

## Engineering Principles

```typescript
const principles = {
  type_safety:     "Strict TypeScript across every layer — no implicit any, no escape hatches",
  security:        "RLS by default; the database is never exposed directly to the client",
  architecture:    "UI, API, and data layers are independently replaceable",
  performance:     "Server-side rendering where it matters, static generation where possible",
  scalability:     "Schema and components built to extend, not rewrite",
  maintainability: "Self-documenting code over clever code",
} as const;
```

---

## GitHub Stats

<div align="center">

<img height="175em" src="https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=github_dark&hide_border=true&bg_color=0D1117&title_color=58A6FF&text_color=8B949E&icon_color=1F6FEB&count_private=true&include_all_commits=true" />

<img height="175em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_USERNAME&layout=compact&theme=github_dark&hide_border=true&bg_color=0D1117&title_color=58A6FF&text_color=8B949E&langs_count=8" />

</div>

<div align="center">

<img width="56%" src="https://streak-stats.demolab.com/?user=YOUR_USERNAME&theme=github-dark-blue&hide_border=true&background=0D1117&stroke=1F6FEB&ring=58A6FF&fire=EA4335&currStreakLabel=58A6FF&sideLabels=8B949E&dates=8B949E" />

</div>

---

## Roadmap

```
  SHIPPED ─────────────────────────────────────────────────────
  [x]  Dynamic project listing from Supabase
  [x]  Contact form with secure backend storage
  [x]  Responsive, mobile-first UI
  [x]  Framer Motion animated interface
  [x]  Full-stack TypeScript — strict mode
  [x]  Row Level Security policies enforced

  NEXT ────────────────────────────────────────────────────────
  [ ]  Admin dashboard for project management         (v2)
  [ ]  Blog system with Markdown + CMS                (v2)
  [ ]  Auth-protected admin panel                     (v2)

  FUTURE ──────────────────────────────────────────────────────
  [ ]  AI-powered portfolio assistant                 (v3)
  [ ]  Advanced analytics dashboard                  (v3)
  [ ]  Multi-theme UI: dark / light / system          (v3)
```

---

## Contact

<div align="center">

<a href="mailto:billbrightmatege@gmail.com">
  <img src="https://img.shields.io/badge/billbrightmatege@gmail.com-161B22?style=for-the-badge&logo=gmail&logoColor=EA4335" />
</a>

<br/><br/>

<a href="https://linkedin.com/in/YOUR_LINKEDIN">
  <img src="https://img.shields.io/badge/LinkedIn-161B22?style=for-the-badge&logo=linkedin&logoColor=0A66C2" />
</a>&nbsp;
<a href="https://YOUR_PORTFOLIO_URL">
  <img src="https://img.shields.io/badge/Portfolio-161B22?style=for-the-badge&logo=vercel&logoColor=FFFFFF" />
</a>&nbsp;
<a href="https://github.com/YOUR_USERNAME">
  <img src="https://img.shields.io/badge/GitHub-161B22?style=for-the-badge&logo=github&logoColor=FFFFFF" />
</a>

</div>

---

<div align="center">

**Status** &nbsp;·&nbsp; Actively maintained &nbsp;·&nbsp; Production deployed &nbsp;·&nbsp; Continuously evolving

<br/>

*"Good systems are not built by adding more — but by designing better."*

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0D1117,50:1F6FEB,100:0D1117&height=120&section=footer" width="100%"/>

</div>
