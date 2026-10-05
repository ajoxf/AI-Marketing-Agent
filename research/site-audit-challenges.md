# Biggest challenges: NordStar Pro + Fincoursa (audit, 2026-10-05)

**Method:** the live sites (nordstarpro.com, fincoursa.com) were blocked by this
environment's network policy, so this audit reviews the **code both sites are built from**
(`ajoxf/NorthStar-Research`, `ajoxf/Fincoursa_LMS`). The live site's settings (environment
variables, admin toggles) may differ from the code defaults. Items marked *(check live)*
depend on those settings. Key findings were spot-checked against the code.

## The short version

1. **NordStar Pro is a well-built product whose public face undersells it and isn't
   trustworthy enough yet** for $199/month, RIAs, or brokers.
2. **Fincoursa is a polished clickable prototype, not a product.** It can't take money or
   deliver a course, and it contains invented logos, people, and testimonials that must
   never go live.
3. **The real constraint is focus and founder time,** not ideas. Two half-ready products,
   with every operation done by hand, compete for the same person.

## Top challenges, in priority order

### 1. Trust: the sites don't yet look like a business a professional would pay

**NordStar Pro:**
- **No company identity anywhere:** no legal entity name, address, support email, or
  jurisdiction. The footer is just "© NordStar Pro" (`site-chrome.tsx:161`).
- **Privacy policy shows a "Placeholder pending review" banner**
  (`privacy-policy/page.tsx:22`).
- **No Terms of Service page exists**, though the site sells auto-renewing subscriptions
  with a no-refund cancellation policy.
- No track record, sample report, or testimonials on the public site.

**Fincoursa:**
- **Invented social proof:**
  - logos of Goldman Sachs, McKinsey, J.P. Morgan, BlackRock and others
    (`IndustryExperts.tsx:16-25`)
  - fake instructors and bios ("Ex-Goldman Sachs")
  - invented ratings and student counts
  - a made-up "Meridian Bank" testimonial
  - "240 courses" when 6 exist
- Shipping any of this would be a trademark and false-advertising problem and would
  destroy credibility with exactly the CMT, RIA, and institutional buyers you want.

**Why it's #1:** every plan (CMT community, RIAs, brokers, exit) runs on trust. Brokers and
RIAs will check who you are on the first call.

### 2. Regulatory exposure in the wording

- **NordStar Pro:** the disclaimer is thorough, but it calls the content **"trading ideas,
  signals, setups, open positions"** (`disclaimer.tsx`). Elsewhere the site presents
  itself as educational research. "Signals" is the language regulators associate with
  advice. That has to be resolved before the publisher position holds up, especially for
  B2B and brokers.
- **Fincoursa:**
  - "Turn knowledge into real returns" is a performance-style claim.
  - "Accredited tracks" is claimed with no accreditation.
  - A "30-day refund guarantee" is promised with no policy behind it.
  - **Permanent strike-through prices** ($149 ~~$249~~) count as fake discounts.
  - **No "not financial advice" wording at all**, while the site sells trading,
    crypto, and FX courses.
- **Action:** the securities-lawyer opinion (in `b2b-plan.md` §10.5) should also cover
  site wording on both sites.

### 3. Buying is fragile and slow

- **Email is a single point of failure.** Every buyer, card or crypto, gets access only
  through an emailed code. The code's **default sender is `team@fincoursa.com`**, so
  NordStar Pro customers would get their access email from a different brand. The
  disclaimer tells members only nordstarpro.com is official, so a mismatched sender looks
  like phishing and is more likely to land in spam. *(Check live: whether `EMAIL_FROM` is
  set and the domain is verified in Resend.)*
- **Long funnel:** pay → wait for the email → enter the code → 3-step wizard → account
  with a required mobile number. Card buyers go through it too, even though Stripe
  confirms payment instantly.
- **Crypto doesn't auto-renew,** so crypto members churn by default unless they pay again
  each period. The homepage trust row still says "Cancel any time"; the code's own
  comment notes that's misleading for crypto.
- **Payment and launch checklist:** in the code, Stripe and Cregis credentials ship as
  placeholders and the GO-LIVE production checks are unticked. *(Check live: confirm both
  payment paths work end to end with a real purchase.)*
- **Lead capture is dead:** the free trial only appears when an admin opens one, and the
  sample-report form isn't used on any page.
- **Fincoursa can't take payment at all.** There is no auth, database, checkout, video
  hosting, or certificates; the "Enrol" button goes straight to a demo dashboard.

### 4. The marketplace is invisible and not yet operable

- **NordStar Pro hides its best asset.** The expert and marketplace view (named experts,
  credentials, per-expert packages, `/experts`, `/coverage`) is **off by default**. While
  it's off, the public sees one anonymous $199 membership. *(Check live: is the "sections
  public" toggle on?)*
- **No payout system:**
  - Expert revenue share isn't stored or calculated anywhere.
  - There's no Stripe Connect and no earnings view for experts.
  - Experts have no login.
  - Affiliates earn on the first payment only, and payouts are manual.
- **Fincoursa's mock instructor portal contradicts your agreed split.** It shows **70%**
  revenue share on one page and **75%** on another (`instructor/earnings:38`,
  `instructor/settings:120`). The agreed rule is a flat **50%**. Recruits who see the
  prototype will anchor on the higher number.
- **No B2B plumbing** (seats, invoicing, VAT) and USD only. That's fine for now, since
  B2B can start manually (`b2b-plan.md` §6).

### 5. Nobody can find it, and you can't measure it

- **No analytics on either site.** You can't see where visitors drop off.
- **NordStar Pro sitemap** lists 5 pages and leaves out `/experts`, `/coverage`, and
  `/trial`.
- No Open Graph or social preview tags, so shared links look bare on LinkedIn and X,
  which are your main channels.
- No public content (insights or knowledge base) for SEO or AI search to find.

### 6. Supply: experts and content are the product

- The whole model depends on experts publishing reliably every week. Broker licensing
  needs **daily** notes.
- Expert contracts must give the platform rights to license and assign the content (see
  `broker-licensing-and-exit.md` §9). Without that, there's no B2B and no exit.
- Few experts means key-person risk. Every instrument and subject needs a backup author.

### 7. Founder bandwidth: everything is manual

One operator does all of this today:
- uploads every PDF
- edits the extracted text
- publishes
- issues access codes
- reconciles underpaid crypto
- settles affiliate and expert payouts
- handles support

Admin two-factor login is still listed as open, and that's a security gap on a site
holding member data.

Fincoursa adds a second product, and its homepage already sells **four offers** (courses,
1:1 coaching, corporate and university programmes, and research) before the core purchase
works.

### 8. Focus: two half-ready products at once

- **NordStar Pro** is close to sellable.
- **Fincoursa** needs either a full backend (auth, payments, video, progress,
  certificates) or Thinkific behind its front end. The project's own Thinkific feature
  audit hasn't been run yet.
- The two brands share a look (same lime accent), but the relationship isn't defined. The
  "Visit NordStar PRO" link on Fincoursa goes to a page that doesn't exist.

## Recommended order

| # | Do | Site change? |
|---|---|---|
| 1 | Securities-lawyer opinion covering regulatory position **and** site wording ("signals", "returns", "accredited", refund promises) | No (advice) |
| 2 | **Fincoursa: make sure no fabricated logos, people, stats, or testimonials are live.** If they are, take them down first. | Yes, urgent if live |
| 3 | NordStar Pro trust basics: company identity and contact details, final privacy policy, Terms of Service, consistent "Cancel any time" wording | Yes, on a preview branch |
| 4 | Verify the purchase path live: sender domain on nordstarpro.com, a real card purchase and a real crypto purchase, email delivered | Config check |
| 5 | Turn on the expert and marketplace view once experts' profiles and credentials are ready | Admin toggle |
| 6 | Analytics, full sitemap, social preview tags | Yes, on a preview branch |
| 7 | Expert contracts: flat 70% / 50%, licensing and assignment rights, backup authors | No (legal) |
| 8 | Fincoursa: sell on Thinkific at $199/module first; align the instructor pages to 50%; build a custom backend only after demand is proven | Later |

All site changes follow the "live site is frozen" rule: preview branch first, owner merges.
