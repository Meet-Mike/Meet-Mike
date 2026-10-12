# Projects Page Copy & Site-Wide Content Spec

## Page Title & Intro

# Demo Projects

Self-initiated projects I built to practise production patterns: concurrency control, performance, offline sync and payments. These are demos, not client work. Each one links to a live demo and its source, and says what I tested and what I didn't.

---

## Demo Projects List

### 1. Ticket Booking with Redis Locking

**Label:** Demo project
**Tech Stack:** Next.js · Redis · PostgreSQL · Prisma

* **What it explores:** How to stop two buyers claiming the last ticket when many checkouts hit at once.
* **Approach:** A Redis lock with a TTL on each ticket, a PostgreSQL row-level lock inside the transaction, and client retries with exponential backoff.
* **Limits:** Single Postgres instance. The live demo runs on mocked client-side state.

**Links:** [Live Demo](https://booking-bwm.netlify.app/) · [Source Code](https://github.com/mrmikeade)

---

### 2. Inventory Dashboard: Zustand + Web Workers

**Label:** Demo project
**Tech Stack:** React · Zustand · Web Workers · IndexedDB

* **What it explores:** Keeping a UI responsive while it recalculates a large multi-warehouse inventory.
* **Approach:** Replaced prop drilling with a Zustand store using fine-grained selectors, moved the heavy calculation into a Web Worker, and cached lookups in IndexedDB.
* **Limits:** Sample data only. The live demo runs with mocked client-side state.

**Links:** [Live Demo](https://auto-bwm.netlify.app/) · [Source Code](https://github.com/mrmikeade)

---

### 3. Headless Storefront with Shopify

**Label:** Demo project
**Tech Stack:** Next.js · Shopify Storefront API · ISR · Tailwind

* **What it explores:** A fast, SEO-friendly storefront on a headless Shopify backend.
* **Approach:** ISR with a 60s revalidate, Next.js image optimisation, fixed aspect ratios to prevent layout shift, and SWR for cart and live inventory.
* **Limits:** Built with sample products. No real traffic or sales data.

**Links:** [Live Demo](https://luxe-bwm.netlify.app/) · [Source Code](https://github.com/mrmikeade)

---

### 4. Offline-First Sync Demo

**Label:** Demo project
**Tech Stack:** React · Firebase · Cloud Functions · LocalForage

* **What it explores:** Letting users edit offline and merge changes cleanly when they reconnect.
* **Approach:** Edits queue locally, then sync with ordering using timestamps for conflict resolution and a merge UI for conflicts.
* **Limits:** Sample client-side demo (TastyHub). Not production-scale.

**Links:** [Live Demo](https://tastyhub-bwm.netlify.app/) · [Source Code](https://github.com/mrmikeade/tastyhub)

---

### 5. D2C Store: Payload CMS + Stripe

**Label:** Demo project
**Tech Stack:** Next.js · Payload CMS · TypeScript · Stripe (test mode)

* **What it explores:** Handling Stripe webhook retries without duplicate orders.
* **Approach:** An idempotent webhook handler that checks the Stripe event ID in Redis before fulfilling, plus server-side analytics events and Payload for editable content.
* **Limits:** Stripe test mode only. No real payments.

**Links:** [Live Demo](https://mguc-bwm.netlify.app/) · [Source Code](https://github.com/mrmikeade)

---

### 6. Voidesk

**Label:** Demo project
**Tech Stack:** Next.js · TypeScript · Tailwind

* **What it explores:** A dark-mode launcher that organises useful web tools in one dashboard, with instant search.
* **Approach:** Search index built at compile time and queried in memory on the client.
* **Limits:** Small set of tools indexed. Not tested on large datasets.

**Links:** [Live Demo](https://voidesk.netlify.app/) · [Source Code](https://github.com/mrmikeade/Voidesk)

---

## Site-Wide & Homepage Fixes Directive

1. **Card Labels:** Change the "Case Study" label on each project card to "Demo project".
2. **Repository Count:** Replace "50+ public projects" with "30 public repositories" across all sections.
3. **Hero Counters:** Remove unverified "System Uptime" and "Test Coverage" hero counters.
4. **Card Metrics Section:** Remove "Quantifiable Business Outcome". Structure card details exclusively under "Verified" (where measured) and "Limits".
5. **Homepage Experience Bullets:** Remove unverified metrics ("LCP to 1.1s" and "20% faster development").
