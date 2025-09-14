# Company Website Spec (US-English) — v0.1.1

Brand: funs.cool  •  Primary domain: [`https://funs.cool/`](https://funs.cool/)

Reference inspiration: [`helloo.work`](https://helloo.work/). We will improve clarity, accessibility, structure, and SEO for a US audience.

## 1. Information Architecture (IA)
- Home (`/`)
- Services (`/services`)
- Work / Projects (`/work`)
- Case Study (`/work/{slug}`)
- Blog (`/blog`)
- Blog Post (`/blog/{slug}`)
- About (`/about`)
- Contact (`/contact`)
- Legal: Privacy, Terms (`/privacy`, `/terms`)

## 2. Global SEO
- Brand: TBD (US-English). Title pattern: `{Page Title} — {Brand}` (40–60 chars).
- Meta description: 150–160 chars, action + benefit.
- Canonical URLs; sitemap.xml; robots.txt.
- Open Graph: `og:title`, `og:description`, `og:image` (1200x630), `og:type`.
- Twitter Card: `summary_large_image`.
- JSON-LD on homepage:

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "{Brand}",
  "url": "https://www.example.com",
  "logo": "https://www.example.com/assets/logo.svg",
  "sameAs": [
    "https://www.linkedin.com/company/{brand}",
    "https://twitter.com/{brand}"
  ]
}
```

```json
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "url": "https://www.example.com/",
  "name": "{Brand}",
  "potentialAction": {
    "@type": "SearchAction",
    "target": "https://www.example.com/search?q={search_term_string}",
    "query-input": "required name=search_term_string"
  }
}
```

## 3. Page Blueprints

### 3.1 Home
- Goal: Communicate value quickly; drive to contact/lead.
- Sections (order):
  1) Hero (headline, sub, primary CTA, secondary CTA, hero image/video)
  2) Value props (3–6 items)
  3) Services overview (link to services)
  4) Featured work (3–6 cards)
  5) Testimonials (2–4 quotes)
  6) Process overview (3–4 steps)
  7) CTA banner
- SEO: H1 aligned to primary keyword; one H1 only.
- Example title: "Custom Web Design That Converts — {Brand}"
- Example description: "We build fast, accessible sites that turn visitors into customers. Book a free consult."

### 3.2 Services
- Goal: Present offerings and outcomes; qualify leads.
- Sections: Intro, Service list (cards with outcomes), Process, FAQs, CTA.
- Each service gets its own detail anchor or page in v1.1.

### 3.3 Work / Projects
- Grid of projects with filters (industry / type optional in v1.1).
- Card content: cover image, title, 10–16 word summary, tags.

### 3.4 Case Study
- Structure: Context → Objective → Approach → Results → Gallery → Testimonial → CTA.
- KPI examples: +X% conversion, -Y% bounce, +Z Core Web Vitals improvements.
- JSON-LD: `CreativeWork` or `Article` with `image`, `author`, `datePublished`.

### 3.5 Blog
- Grid with categories and search (optional in v1.1).
- Post card: 16:9 cover, title, 20–28 word excerpt, author, date, tag.

### 3.6 Blog Post
- Structure: H1 → intro (40–60 words) → sections (H2/H3) → summary → CTA.
- SEO: target 900–1500 words; include internal links; one primary keyword.
- JSON-LD: `Article` with `headline`, `author`, `datePublished`, `image`.

### 3.7 About
- Story, mission/values, team, credibility (logos/certifications), CTA.

### 3.8 Contact
- Form fields: name, email, company (optional), budget (select), timeline (select), message.
- Anti-spam: honeypot + server validation. Success state with clear next steps.

### 3.9 Footer
- Primary nav (top-level), legal links, social links, small newsletter form (optional), copyright.

## 4. Component Inventory (MVP)
- Button (primary/secondary/ghost; sm/md/lg)
- Navbar (sticky)
- Section header (eyebrow, title, subtitle)
- Card (work, service, blog)
- Testimonial (quote + author)
- Step list (process 1–4)
- Stats (KPI with label)
- Form (contact)
- Footer

## 5. Copy Style (US-English)
- Benefit-first, outcome-driven, concrete verbs; avoid buzzwords.
- Keep headings ≤ 7 words; paragraphs ≤ 3 sentences; bullets preferred.
- Use numerals for quantities ("11 years", not "eleven").

## 6. Visual & Layout Rules (summary)
- Follow `.cursorrules` tokens and breakpoints.
- Minimum body text size 16px; line-height ~1.6.
- Hit targets ≥ 44×44px; focus states always visible.

## 7. Image & Media Requirements (Provide Assets)
Please supply the following. If unavailable now, placeholders will be used; we’ll swap later.

### 7.1 Brand
- Logo (primary): SVG (preferred), plus PNG fallback (1024×1024). Shapes only, no text rasterization.
- Favicon: 16×16, 32×32 PNG; `apple-touch-icon` 180×180 PNG; `mask-icon` SVG (monochrome).

### 7.2 Social & Sharing
- Open Graph default: 1200×630 JPG or PNG (< 600KB), plus WebP. Safe text zone: center 70%.

### 7.3 Homepage
- Hero image: 1920×1080 (16:9) WebP (≤ 800KB), subject right or left with safe bleed; supply a 1280×720 fallback.
- Value props icons: 48×48 SVG (1-color or 2-color).
- Featured work covers: 1280×853 (3:2) WebP (≤ 500KB); also 960×640 for mobile.

### 7.4 Services
- Section illustration (optional): 1600×1000 (8:5) WebP or SVG.

### 7.5 Work / Case Studies
- Cover: 1920×1280 (3:2) WebP; 1280×853 alt.
- Gallery: 1600×1000 (8:5) WebP, 4–8 images per project.
- Metrics screenshots (if any): 1600px width PNG/WebP with sensitive info redacted.

### 7.6 Blog
- Post cover: 1280×720 (16:9) WebP or JPG; ≤ 400KB.
- Author headshot: 512×512 WebP/PNG, centered, simple background.

### 7.7 Team (About)
- Portraits: 1200×1500 (4:5) WebP, consistent framing and lighting.

### 7.8 Video (optional)
- MP4 (H.264) 1080p, ≤ 30s for hero loop; provide poster image 1280×720 JPG/WebP.

## 8. Color & Type (initial)
- Brand primary (Neon Violet Scheme C): Violet 700 `#6d28d9` on white `#ffffff` (contrast AA+).
- Hover/active tiers: `#5b21b6` (hover), `#4c1d95` (active); Elevated surfaces use shadow tokens.
- Accent (cool contrast): Cyan 500 `#0ea5e9` for highlights and charts.
- Neutral text: `#0b1220`; body bg: `#ffffff`; muted bg: `#f9fafb`.
- Font: Inter / system stack; body 16–18px; headings use fluid clamp.

## 9. Performance & Accessibility
- Core Web Vitals targets: LCP ≤ 2.5s (4G), CLS < 0.1, INP ≤ 200ms.
- Provide alt text for all non-decorative images; keyboard-accessible navigation; visible focus.
- Serve AVIF/WebP first with PNG/JPG fallbacks; responsive `srcset`.

## 10. Roadmap (post-MVP)
- Service detail pages; search on blog; industry filters on Work; dark mode; newsletter.

---

## 11. Open Questions / Inputs Needed
- Brand name, tagline, value proposition (US-English).
- Target industries (for Work filters) and 2–4 flagship case studies.
- Testimonials (2–4, US-English). Include name, role, company, headshot (optional).
- Preferred primary color (optional), else keep `#1e40af`.
- Provide the asset set listed in Section 7. If helpful, I can generate temporary placeholders.

## 12. What We Improve vs Inspiration
- Clearer IA and CTA flow; stricter heading hierarchy; stronger SEO structure; consistent tokenized design system; explicit performance budgets.


## 13. Page Content Drafts (v0.1)

### 13.1 Homepage
- SEO
  - Title: "Launch & Scale Your Web3 Project on Telegram — funs.cool"
  - Meta description: "We build high-performance Telegram Mini Apps & Bots for Web3. Frictionless onboarding, smart bots, and scalable architecture that drive on-chain growth. Book a free strategy call."
  - Slug: "/"
  - OG image: 1200×630 (center-safe), with headline and brand mark
- Hero
  - H1: Launch & Scale Your Web3 Project on Telegram
  - Subheadline: In the battle for users, Telegram isn't just a chat app—it's the ultimate Web3 super-portal. We are your expert development partners, architecting high-performance Telegram Mini Apps & Bots that convert users, supercharge community engagement, and drive real on-chain activity.
  - Primary CTA: Book Your Free Strategy Call
- Section: Our Core Services: From Concept to Code (H2)
  - Custom Telegram Mini Apps & Bots (H3)
    - We offer end-to-end, full-stack development to build robust, scalable applications that live directly inside Telegram.
    - Intelligent Bots: We go beyond simple community management. We build sophisticated bots that act as 24/7 extensions of your operations team—executing complex airdrop mechanics, broadcasting real-time on-chain alerts, automating governance, and serving as an intelligent voice for your brand.
    - Immersive Mini Apps: We embed your entire dApp—DeFi protocols, GameFi experiences, NFT marketplaces—into a seamless, high-performance interface within Telegram. Users get a native-app-level experience without ever leaving their chat, crushing the friction points that kill conversion funnels.
  - Frictionless Web3 Onboarding & UX (H3)
    - We believe great tech should feel invisible. Forget clunky browser extensions and seed phrase anxiety; we design user journeys built for mass adoption.
    - Zero-Friction Onboarding: Leveraging cutting-edge tech like Account Abstraction (AA) and MPC wallets, we enable social logins, one-click wallet creation, and intuitive recovery methods. Our mission is to make your Web3 app so easy to use, anyone can be onboarded in under 60 seconds, unlocking the widest possible user base for your project.
    - Intuitive On-Chain Interaction: We design interfaces that intelligently merge on-chain actions (like signing and authorizing transactions) with the user's natural workflow. This builds trust and encourages deeper, more confident engagement with your protocol.
  - Full-Lifecycle Development & Strategic Partnership (H3)
    - We deliver far more than just code. We are the embedded technical partners you need to navigate the complexities of the Web3 space.
    - Architectural & Strategic Planning: Before a single line of code is written, we act as your technical counsel. We dive deep into product architecture, tokenomics integration, security modeling, and scalability planning to build a rock-solid foundation for long-term success.
    - Full-Cycle Development & Support: We operate on agile sprints with rigorous code reviews and comprehensive automated testing. Post-launch, we provide ongoing support, maintenance, and strategic roadmapping to ensure your application not only launches flawlessly but also evolves and scales securely.
- CTA Section
  - H2: Ready to Build Your Telegram Super App?
  - Subheadline: A great vision deserves world-class execution.
  - Body: A deep-dive conversation is the catalyst for a successful partnership. We invite you to a complimentary 30-minute strategy call where we'll analyze your goals, identify technical challenges, and outline a preliminary framework for execution. No sales pitch. Just pure value.
  - Primary CTA: Book Your Free Strategy Call
- Structured Data (Homepage)
  - Use Organization + WebSite (see Section 2). Consider `Service` objects for key offerings in v1.1.

### 13.2 Contact Us
- SEO
  - Title: "Contact — Build on Telegram with funs.cool"
  - Meta description: "Start your Web3 project on Telegram. Reach us via Telegram or email. Share your brief and our solutions architect will schedule a 30-minute consult."
  - Slug: "/contact"
  - OG image: 1200×630 contact-themed visual with brand mark
- Content
  - H1: Let's Build Together
  - Subheadline: Start the conversation about your next big project. We're here to answer your questions and explore how we can bring your vision to life on Telegram.
  - Body: Thank you for your interest in our expertise. We believe the most effective collaborations are born from clear, direct communication. Telegram is at the core of our workflow and our preferred channel for seamless client synergy. Use your preferred method below to get in touch, and our Web3 solutions architect will schedule a dedicated meeting to begin your project assessment.
  - H2: Contact Information
    - Preferred Channel | Telegram: @YourStudio_Contact
    - Email: service@funs.cool
    - Availability: Monday - Friday, 9:00 AM - 5:00 PM (PST)
  - H2: Send Us Your Project Brief
    - Form Fields
      - Your Name / Company Name — Text Field
      - Your Telegram Handle or Email (for our reply) — Text Field
      - Project Overview — Text Area with placeholder: "Please provide as much detail as possible: describe your core concept, target audience, key features, competitive landscape, and your expected timeline or roadmap."
      - Submit button: "Submit Project Brief"
- Structured Data (ContactPage)
```json
{
  "@context": "https://schema.org",
  "@type": "ContactPage",
  "name": "Contact — Build on Telegram with {Brand}",
  "url": "https://www.example.com/contact",
  "about": {
    "@type": "Organization",
    "name": "{Brand}",
    "contactPoint": {
      "@type": "ContactPoint",
      "contactType": "customer support",
      "availableLanguage": ["English"],
      "areaServed": "US",
      "hoursAvailable": {
        "@type": "OpeningHoursSpecification",
        "dayOfWeek": [
          "Monday","Tuesday","Wednesday","Thursday","Friday"
        ],
        "opens": "09:00",
        "closes": "17:00"
      }
    }
  }
}
```

## 14. CSS-only Illustration Policy (MVP)
- All decorative visuals are CSS-only (no raster/SVG imagery) for hero, section dividers, abstract motifs.
- Foreground text remains selectable and transparent-reveal compatible (use `.text-reveal` when appropriate).
- Background system: container `.illustra` + layered pseudo-graphics via gradients, masks, blend modes, and keyframe motion.
- Motion respects `prefers-reduced-motion`.
- Token-driven colors from `.cursorrules`.
- Provide a public demo at `/demo.html` to validate performance and accessibility over different devices.


## 15. Brand Wordmark Usage
- Always render the brand as the CSS wordmark: `funs` + dot + `cool` using the `.brand` (links/buttons) or `.brand-inline` (inline text) structures.
- Typeface: Inter (var(--font-sans)); weight 800; tight letter-spacing (-0.01em).
- The dot uses `--color-accent` with a subtle glow; do not replace with a plain period character.
- Sizes: navbar `.brand` uses `clamp(1.15rem, 2.6vw, 1.6rem)`; footer `1rem`; inline follows surrounding text size.
- Never rasterize the wordmark or embed it as an image; keep it selectable and accessible.


