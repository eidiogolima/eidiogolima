<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0A66C2,100:2F81F7&height=140&section=header&text=Diogo%20Lima&fontSize=48&fontColor=ffffff&fontAlignY=40" width="100%" />

<a href="https://github.com/eidiogolima">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=20&pause=1200&color=2F81F7&center=true&vCenter=true&width=640&lines=Senior+PHP+%2F+Laravel+Engineer;6+years+building+production+systems;APIs+%C2%B7+High+Availability+%C2%B7+Performance;Open+to+Senior+Back-end+roles" alt="Typing animation" />
</a>

</div>

**Senior PHP / Laravel engineer · 6 years in production.** I build APIs, high-availability systems and full-stack products where performance and uptime directly affect revenue.

I lead legacy modernization, architecture decisions and code quality, and connect technical work to business outcomes.

📍 Araraquara, SP, Brazil · 🌎 Open to Senior Back-end / Full-stack roles (remote) · 🗣️ Portuguese (native) · English (intermediate)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/diogo-lima-8117bb211/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:eidiogoadm@gmail.com)

---

## 📈 Selected results

| Area | Result |
| --- | --- |
| ⚡ **Performance** | Critical pages from ~60 s to 200 ms (**-99.7%**); complex queries from 10 min to 200 ms (**-99.9%**) |
| 🛡️ **Availability** | Designed HA with a standby server and Cloudflare Load Balancing: **failover under 1 minute**. Refunds and lost sales tied to outages dropped to **zero** |
| 🔁 **Resilience** | Decoupled checkout from an external API with async processing: order completion during its outages went from **0% to 100%** |
| 🤖 **Automation** | White-label stores and automatic payment split for **100+ partners**, eliminating **100%** of the manual commission reconciliation (7+ hours per cycle) |
| 🔧 **Modernization** | Led the API migration from **Laravel 8 to Laravel 12** |
| 📊 **Tracking** | Reached **~100% data coverage** (from no reliable data) across 50k+ sessions and 10k+ conversions |
| 🐞 **Quality** | **-50%** bug recurrence in legacy PHP systems with preventive fixes and structured triage |

---

## 🏗️ Architecture I designed

<details>
<summary><b>High availability with failover under 1 minute</b></summary>

<br/>

Outages of a few hours used to cause 50+ refund requests and lost sales. After this design, outages no longer produced refunds or lost sales.

```mermaid
flowchart LR
    U([Users]) --> CF{{"Cloudflare<br/>Load Balancing<br/>+ health checks"}}
    CF -->|healthy| P["Primary server"]
    CF -.->|"failover < 1 min"| S["Standby server"]
    P --> DB[("Database")]
    S --> DB
    P -.->|"unhealthy"| CF
```

</details>

<details>
<summary><b>Resilient checkout: decoupled from an external API</b></summary>

<br/>

Orders used to fail whenever the external API was down. Moving that call to background processing took order completion during its outages from 0% to 100%.

```mermaid
sequenceDiagram
    participant C as Customer
    participant K as Checkout
    participant Q as Queue
    participant W as Worker
    participant X as External API
    C->>K: Place order
    K->>Q: Enqueue integration job
    K-->>C: Order confirmed
    Q->>W: Dispatch job
    W->>X: Call API
    alt API unavailable
        X--xW: Error
        W->>Q: Retry later
    else API available
        X-->>W: Success
        W->>K: Update order
    end
```

</details>

---

## 💼 Experience

<details open>
<summary><b>SP Certificado Digital</b> · Full-Stack PHP/Laravel Developer · <i>Jan 2024 – present</i></summary>

<br/>

- Designed the high-availability architecture (standby server + Cloudflare Load Balancing) with failover under 1 minute.
- Decoupled checkout from an external API using background jobs, so orders complete even when that API is down.
- Optimized SQL and Laravel components behind dashboards, cutting load times by ~99.7%.
- Built white-label stores (own domain and branding, transparent checkout, automatic split) for 100+ partners with Vue.js and Inertia.js.
- Rebuilt event and conversion tracking to fix gaps in the purchase journey and guide campaign investment.
- Led the Laravel 8 → 12 migration, hardened document access control and added observability with Grafana.

</details>

<details>
<summary><b>BURH</b> · Full-Stack PHP/Laravel Developer · <i>Oct 2025 – Sep 2026</i></summary>

<br/>

- Worked on APIs and systems of a platform with 20+ products: architecture decisions, code reviews, CI/CD, Docker, queues and scheduled jobs.
- Led **Trackiou**: integrates browsing and conversion data with Google Ads and Meta Ads to follow the journey through to the sale.
- Led **Spotei**: internal SDR platform with pipeline, goals and automations, centralizing lead management.
- Built a React / Next.js scheduling interface on top of calendar APIs for recruiters.
- Defined guidelines for the safe adoption of AI in backend development, preserving code and security standards.

</details>

<details>
<summary><b>ZipSign</b> · Back-end PHP/Laravel Developer · <i>Jan 2023 – Jan 2024</i></summary>

<br/>

- Built credits, plans, dashboards and admin tools for an e-signature platform, plus payment gateway integrations.
- Contributed to moving private documents to Amazon S3 and built REST APIs with stronger access security.

</details>

<details>
<summary><b>Comprar Site</b> · PHP Developer · <i>Jan 2020 – Jan 2023</i></summary>

<br/>

- Built and maintained PHP/Laravel web solutions, REST integrations and SQL queries; helped raise delivery speed by ~50% through agile process improvements.

</details>

---

## 🧰 Stack

| Area | Tools |
| --- | --- |
| **Back-end** | PHP 8, Laravel, Lumen, Python, REST APIs, queues, jobs, Pub/Sub, async processing, caching, OOP, SOLID |
| **Data** | MySQL, PostgreSQL, Redis, query optimization |
| **Infra & delivery** | Docker, Kubernetes, Linux, Git, CI/CD, GitHub Actions, Cloudflare (Load Balancing, R2), Amazon S3, Grafana |
| **Front-end** | Vue.js, Inertia.js, React, Next.js, TypeScript, JavaScript, Tailwind CSS |
| **Quality & security** | PHPUnit, Laravel Dusk, Pest, PHPStan, automated testing, code review, OWASP Top 10 |

<p>
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/php/php-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/laravel/laravel-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mysql/mysql-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/redis/redis-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/kubernetes/kubernetes-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/linux/linux-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/githubactions/githubactions-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nextjs/nextjs-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" />
  <img height="32" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/grafana/grafana-original.svg" />
</p>

---

## 📌 Public work

### 🤝 Open source, built for the community

[![laravel-vue-boilerplate](https://img.shields.io/badge/laravel--vue--boilerplate-open%20source-2F81F7?style=for-the-badge&logo=laravel&logoColor=white)](https://github.com/eidiogolima/laravel-vue-boilerplate)
[![License: MIT](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)](https://github.com/eidiogolima/laravel-vue-boilerplate/blob/main/LICENSE)

**[laravel-vue-boilerplate](https://github.com/eidiogolima/laravel-vue-boilerplate)** is a free, MIT-licensed starting point for Laravel 13 + Vue 3 + Inertia projects, so other developers can skip the setup and start on the product:

- Authentication with passkeys and 2FA, admin panel and notifications
- Interface in English, Spanish and Brazilian Portuguese (i18n)
- Quality gates from day one: strict typing, PHPStan, Pest and a CI pipeline
- Project rules documented for AI-assisted development with Claude Code

Contributions, issues and stars are welcome.

### 🧩 Other

| Project | What it shows |
| --- | --- |
| [Trackiou](https://trackiou.cloud/) | Traffic, attribution and lead-tracking platform (UTMs, Google/Meta Ads, organic and AI referrals) |

> Most of my work lives in private repositories. Happy to walk through architecture and decisions in an interview.

## 🎓 Education

Systems Analysis and Development, UNINTER (in progress, expected 2029) · Certifications: Advanced PHP Development; PHP/WordPress REST API; Front/Back End & UX/UI Design.

---

## 📊 GitHub stats

<div align="center">

<img src="https://streak-stats.demolab.com?user=eidiogolima&theme=tokyonight&hide_border=true" />

<br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/eidiogolima/eidiogolima/output/github-contribution-grid-snake-dark.svg" />
  <img alt="Contribution snake" src="https://raw.githubusercontent.com/eidiogolima/eidiogolima/output/github-contribution-grid-snake.svg" />
</picture>

</div>

---

⭐ Hiring for a Senior Laravel / back-end engineer? **Let's talk.**
