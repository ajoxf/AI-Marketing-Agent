# Go-to-market plan: CMT community → RIAs → institutions

Status: **proposal, not approved.** No changes are made to the live site (`ajoxf/NorthStar-Research`)
without explicit sign-off. See "Open questions" at the bottom.

## How realistic is each buyer?

| Segment | Likelihood (next 12 months) | Why | What they need before buying |
|---|---|---|---|
| **CMT charterholders, candidates & members** (individuals) | **High** | They already pay out of pocket for technical tools and research (charting platforms, newsletters). Research written by fellow CMTs is credible to them. | Instructors they recognise, a free trial, an annual option, a candidate/student price |
| **Independent RIAs with a technical/tactical tilt** (1–20 advisers) | **Medium** | Most RIAs get research bundled with platforms (Morningstar, custodians) and are not technical. The minority who run tactical models, often with a CMT on staff, are the real target. | Firm licence (multi-seat), invoice/ACH (not crypto), vendor due-diligence pack, **rights to use charts with clients** |
| **Family offices** | **Low–medium** | Few in number, relationship-driven, rarely buy from a website. | A warm introduction, an analyst call, a track record |
| **Institutions** (hedge funds, asset managers, banks, prop desks) | **Low for 12–18 months** | They buy research through research budgets and vendor onboarding (compliance, MiFID II research-payment rules in UK/EU). They expect analyst access, a verifiable track record, and pricing in the $10K–$100K+/yr range. A $199/mo card checkout signals "retail". | 12+ months of timestamped calls, a named-analyst access tier, enterprise contract terms, delivery through the research marketplaces they already use |

**Bottom line:** start with the CMT community, where instructor credibility converts directly. Use
that base and an auditable track record to earn RIAs. Treat institutions as a year-two
outcome reached through warm introductions from CMT members who work inside them, not
through cold outreach.

## The realistic sales motion, by segment

### 1. CMT community (months 0–6): instructor-led

The site already supports per-author packages and affiliate links. That is the engine:
each instructor sells their own subject and shares the revenue.

1. **Instructors bring their own audience first.** Give each instructor a personal
   `?ref=` link and a trial link for their section. A first-month target of 10–20 paid
   members per instructor from their existing followers is realistic and shows proof.
2. **Give before asking.** CMT Association has 4,500+ members and 36 chapters
   ([source](https://cmtassociation.org/association/)). Instructors volunteer to
   **present at chapter meetings** and pitch articles to *Technically Speaking*, the
   association's member bulletin. They teach a method and mention NordStar Pro once, at
   the end.
3. **Sponsor, don't spam.** Chapter events and the Global Investment Summit accept
   sponsors (Optuma, OANDA, and Stocktwits appear in past materials). A small chapter
   sponsorship is cheap and puts the brand in the room. **Never scrape or mass-mail the
   member directory**; that burns the relationship the whole strategy depends on.
4. **A CMT candidate offer.** Offer a discounted annual plan for exam candidates and
   recent charterholders. They are early in their careers, stay members for years, and
   become the RIA and institutional analysts of tomorrow.
5. **Public weekly chart.** Each instructor posts one public chart a week on LinkedIn and
   X with their reasoning, linking to the trial. LinkedIn is where CMTs, RIAs, and
   institutional analysts actually are.

### 2. RIAs (months 3–12): "a technical research desk for advisers who don't have one"

1. **Packaging (needs your decision):** a firm licence (e.g. 3 and 10 seats), annual,
   invoiced. Optionally a **client-ready chart pack** with redistribution rights, which
   RIAs value most because it helps them write client letters.
2. **Due-diligence pack:** a one-page PDF covering who the analysts are (CMT
   credentials), methodology, conflicts-of-interest and personal-trading policy, the
   regulatory position, data sources, and the track-record method. Compliance officers
   ask for this before anyone can subscribe.
3. **Outreach is B2B, so it's allowed, but keep it 1:1.** Target RIAs whose ADV, website,
   or LinkedIn shows tactical or technical strategies or a CMT on staff (public SEC IAPD
   data). The agent researches and drafts; a human sends 10–20 personalised emails a
   week from a real mailbox, with an opt-out and postal address (CAN-SPAM). No sequences
   of 5 follow-ups, and no AI calls.
4. **Monthly 30-minute "market technicals for advisers" webinar** run by an instructor.
   The webinar is the conversion event. Look into whether CE credit (e.g. CFP Board) is
   feasible, since CE credit sharply raises adviser attendance.
5. **Referral loop:** an RIA client gets a discount for referring another firm.

### 3. Family offices & institutions (months 9–24): credibility first, then warm intros

1. **Track record:** publish a dated, unedited log of every call (entry, levels,
   invalidation, outcome), including the losers. Nothing else convinces institutional
   buyers. This takes 12 months to build, so **start now**.
2. **Institutional tier:** named-analyst access (monthly call, ad-hoc questions), custom
   coverage, and contract terms. Priced in the institutional range, invoiced.
3. **Distribution through marketplaces** institutions already use for independent
   research (e.g. Smartkarma, ResearchPool). Check each platform's current terms and
   fees.
4. **Warm introductions only.** CMT charterholders working at funds and banks are the
   bridge. Ask instructors for introductions once the track record exists.

## Step-by-step plan

**Nothing touches the live site until you approve it.** Site changes would go on a
separate branch with a **Vercel preview deployment** (a private test URL). Production
stays untouched until you review the preview and merge.

| Step | What | Touches live site? | Owner |
|---|---|---|---|
| 1 | Answer the open questions below | No | You |
| 2 | Verify the domain in Google Search Console (DNS TXT record) | No (DNS only) | You, with the agent guiding |
| 3 | Write the instructor kit: ref links, trial links, a post template, a chapter-talk outline | No | Agent drafts, you approve |
| 4 | Write the RIA due-diligence pack and the firm-licence offer (terms and price) | No | Agent drafts, you and a lawyer approve |
| 5 | Start the public, timestamped track-record log (a document, then a site page later) | No | Instructors + agent |
| 6 | Build an RIA target list from public SEC IAPD/ADV data and LinkedIn (no scraping of logged-in LinkedIn) | No | Agent researches; human reviews |
| 7 | Site changes on a branch with a preview URL: analytics, full sitemap, UTM capture, `/insights`, a `/for-advisers` page with a firm-licence enquiry form | **Preview only** | Agent builds; you review the preview |
| 8 | Merge to production after your review, then watch for errors for 48 hours | Yes, with your approval | You approve; agent monitors |
| 9 | Weekly loop starts (`weekly-loop.md`): instructor content, nurture, RIA 1:1 outreach, metrics | No | Agent + human approval |
| 10 | Day 90 review: cost per paid member by segment; keep or cut channels | No | You |

## Open questions (needed before step 3)

1. **Site changes:** may I work on a branch with a Vercel preview deployment (production
   untouched until you merge), or should the site stay frozen entirely for now?
2. **Regulatory position:** which country is the company in, and is NordStar Pro or any
   instructor registered (SEC/state RIA, FCA, etc.)? This decides what we can say to RIAs
   and institutions.
3. **Instructors:** how many, are they CMT charterholders, how big are their audiences,
   and what is their revenue share? Will they present at chapters or run webinars?
4. **Track record:** do timestamped historical calls exist that we can publish?
5. **Pricing:** are you open to annual plans, a CMT candidate price, firm licences with
   invoicing, and client redistribution rights for RIAs?
6. **People and budget:** who approves content and sends 1:1 emails, and what is the
   monthly budget for tools and sponsorships?
7. **CMT relationships:** is any instructor a chapter lead or active volunteer?
8. **Sample-report form:** the component exists in the code
   (`sample-report-form.tsx`) but does not appear to be used on any page. Is that
   intentional?
