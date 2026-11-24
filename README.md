*Bismillahir Rahmanir Rahim*

# Masjid Musab bin Umair — Next-Gen Platform

Assalamu Alaikum Warahmatullahi Wabarakatuh!

This repository houses the next-generation web application for **Masjid Musab bin Umair (West Forsyth Islamic Center)**, a 501(c)(3) non-profit organization serving the Muslim community in Cumming and Forsyth County, Georgia. Built by community volunteers as *Sadaqah Jariyah*, this platform is engineered for sub-second mobile performance, offline reliability, and real-time community engagement.

- **Live Production Website:** [https://masjidmusab.com](https://masjidmusab.com)
- **GitHub Organization:** [github.com/masjidmusab](https://github.com/masjidmusab)
- **Technical Inquiries:** [tech@masjidmusab.com](mailto:tech@masjidmusab.com)

---

## Definitive Platform Capabilities

1. **Native Live Prayer & Iqamah Engine:** Real-time countdown to the next Adhan and Iqamah synced with our official **AthanPlus (`Vdw3z7de`) / MasjidDashboard** schedule, featuring automatic Hijri–Gregorian dates, Sunrise/Zawal markers, and downloadable monthly timetables.
2. **Friday Jumu'ah & Khutbah Archive:** Dynamic Friday banner highlighting our two Jumu'ah sessions (`1:45 PM` & `2:45 PM`), weekly Khatib details, parking guidelines, and searchable Khutbah recordings/summaries.
3. **Contextual Giving & Zakat Calculator:** Built-in Nisab/Zakat estimator and quick-preset giving flows integrated seamlessly with our **MOHID** donation portal.
4. **Filterable Programs & One-Click Calendar Sync:** Dedicated tracks for Brothers, Sisters, Youth, Quran & Sunday School with instant `.ics` (Apple/Google/Outlook) calendar exports.
5. **Urgent Janazah & Moon Sighting Alerts:** High-visibility, dismissible alert banners for time-sensitive Janazah prayers, weather closures, and Ramadan/Eid announcements.
6. **Offline-First PWA & Lobby Display (`/display`):** Installable mobile Progressive Web App with offline prayer caching, plus a dedicated full-screen TV signage view powered by the same data layer.

---

## Tech Stack

- **Framework:** Next.js (App Router) + React + TypeScript
- **Styling & UI:** Tailwind CSS + Shadcn/UI (Accessible Radix Primitives, Dark/Light themes, RTL Arabic support)
- **Data Fetching:** TanStack Query + Edge Caching with LocalStorage offline fallback
- **Integrations:** AthanPlus / MasjidDashboard (Prayer Schedules), MOHID (Donations & Community Portal)
- **CI/CD & Hosting:** GitHub Actions + Vercel Preview Deployments on every Pull Request

---

## Prerequisites

- [Node.js](https://nodejs.org/) **v20 LTS** or newer
- **npm** v10+ (included with Node.js)
- [Git](https://git-scm.com/)

---

## Local Development Setup

1. **Fork and clone the repository:**
   ```bash
   git clone https://github.com/masjidmusab/musab-connect.git
   cd musab-connect
   ```
   *(If contributing from a personal fork, clone your fork and add upstream: `git remote add upstream https://github.com/masjidmusab/musab-connect.git`.)*

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure environment variables:**
   ```bash
   cp .env.example .env.local
   ```
   > **Security Notice:** Never commit `.env` or `.env.local` files containing API keys or secrets.

4. **Start the local development server:**
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000) in your browser.

5. **Run linting, type-checking, and production build:**
   ```bash
   npm run lint
   npm run build
   ```

---

## Project Architecture

```text
musab-connect/
├── public/                     # PWA manifest, service worker, icons, Masjid branding
├── src/
│   ├── app/                    # Next.js App Router pages (/, /prayer-times, /programs, /donate, /display)
│   ├── components/
│   │   ├── prayer/             # Live Iqamah countdown, daily timetable, Jumu'ah card
│   │   ├── layout/             # Navbar, Footer, Urgent Alert Banner, Mobile Action Bar
│   │   └── ui/                 # Accessible Shadcn/UI primitives (buttons, modals, tabs)
│   ├── lib/
│   │   ├── prayer-api.ts       # AthanPlus / MasjidDashboard parser & offline cache
│   │   ├── hijri.ts            # Hijri-Gregorian calendar utilities
│   │   └── calendar-ics.ts     # One-click .ics event generator
│   └── data/                   # Masjid metadata, Jumu'ah schedules, and static configuration
├── .env.example                # Template for local environment variables
├── .gitignore                  # Excludes node_modules, .next, and .env secrets
├── package.json                # Dependencies and build scripts
└── README.md                   # Platform documentation
```

---

## Product Roadmap

- [ ] **Phase 1 — Core Foundation:** Mobile-first Home, Live Iqamah Countdown Widget, Dual Jumu'ah Card, Urgent Alert Banner, and MOHID Giving Integration
- [ ] **Phase 2 — Community & Education Hub:** Filterable Programs directory (Quran/Sunday School, Youth, Sisters), `.ics` calendar sync, and Khutbah archive
- [ ] **Phase 3 — Ramadan & Eid Command Center:** Suhoor/Iftar countdowns, Taraweeh schedule, Zakat-ul-Fitr deadlines, and Eid prayer logistics
- [ ] **Phase 4 — Offline PWA & `/display` Signage Mode:** Service worker offline support and unified Lobby TV view

---

## How to Contribute

We welcome pull requests from volunteer engineers, UI/UX designers, and community members:

1. **Check open issues** or create a [Bug Report](https://github.com/masjidmusab/musab-connect/issues/new?template=bug_report.yml) / [Feature Request](https://github.com/masjidmusab/musab-connect/issues/new?template=feature_request.yml).
2. **Create a feature branch** from `staging` using `kebab-case`:
   ```bash
   git checkout staging
   git pull origin staging
   git checkout -b feat/live-iqamah-countdown
   ```
3. **Verify quality gates before pushing:**
   - Test across both **mobile** and **desktop** screen sizes.
   - Confirm prayer times, Jumu'ah schedules, and MOHID donation links render accurately.
   - Confirm `npm run lint` and `npm run build` pass with zero errors.
4. **Commit using Conventional Commits:**
   ```bash
   git commit -m "feat: add live countdown timer to next Iqamah"
   ```
   *(Accepted prefixes: `feat:`, `fix:`, `docs:`, `style:`, `chore:`)*
5. **Open a Pull Request** targeting **`staging`** (change the **base** branch dropdown from `main` to **`staging`**) and include screenshots for UI changes. *(Direct PRs to `main` from feature branches or forks are blocked; maintainers promote verified changes from `staging` to `main`.)*

Review our [Contributing Guidelines](https://github.com/masjidmusab/.github/blob/main/CONTRIBUTING.md) and [Code of Conduct](https://github.com/masjidmusab/.github/blob/main/CODE_OF_CONDUCT.md) for full details.

---

## Security

If you discover a security vulnerability, exposed credential, or donor privacy concern, **do not open a public issue**. Please email **[security@masjidmusab.com](mailto:security@masjidmusab.com)** privately per our [Security Policy](https://github.com/masjidmusab/.github/blob/main/SECURITY.md).

---

## License

This project is open-source software maintained for the benefit of the community. *JazakAllahu Khairan* for your contributions!
