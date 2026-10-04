# Selling NordStar Pro + Fincoursa, automated: experts, affiliates, and the flywheel

Status: **proposal.** Revenue-split variations and affiliate terms below are recommendations
for you to decide. They change contracts with experts. Nothing here changes either live
site.

## 1. What you are actually running

Both businesses are **two-sided marketplaces**. You sell to two groups:

| | Supply side (sell the platform *to* them) | Demand side (sell *their* work) | Platform share of net |
|---|---|---|---|
| **NordStar Pro** | Technical analysts / subject experts (CMT community first) | Research subscribers: traders, RIAs, institutions | **30%** (expert keeps 70%) |
| **Fincoursa** | Instructors (often the same people) | Students: CMT candidates, finance professionals, traders | **50%** (instructor keeps 50%) |

**The core strategy:** recruit experts who already have an audience, make it easy for
them to sell, and let the platforms cross-sell each other. Experts are your best
affiliates. A marketplace that relies on its own ads at a 30% take rate rarely makes money;
one where experts bring their audiences does.

## 2. Unit economics (worked example)

The definitions below are assumptions; confirm them in your expert contracts.
- **Net revenue** = gross − payment fees − refunds/chargebacks − sales tax/VAT −
  affiliate commissions.
- Example prices: a NordStar Pro subscription at $199/mo (net ≈ $192); a Fincoursa course
  at $499 (net ≈ $484). The course price is a placeholder; use your real price.

### NordStar Pro: $199/mo subscription (net ≈ $192/mo)

| Who brought the customer | Affiliate | Expert | Platform | Platform per year |
|---|---|---|---|---|
| Platform (SEO, content, platform ads) | — | 70% = $134 | 30% = **$58** | $691 |
| A third-party affiliate (20% of net for 12 months, off the top) | $38 | $108 | **$46** | $553 |
| The expert's own audience (recommended: 80/20 for 12 months) | — | 80% = $154 | 20% = **$38** | $461 at zero acquisition cost |

### Fincoursa: $499 course (net ≈ $484, one-time)

| Who brought the customer | Affiliate | Instructor | Platform |
|---|---|---|---|
| Platform | — | 50% = $242 | 50% = **$242** |
| A third-party affiliate (30% of net, off the top) | $145 | $169 | **$169** |
| The instructor's own audience (recommended: 70/30) | — | 70% = $339 | 30% = **$145** |

**Why channel-based splits matter:** under a flat 70/30, an expert has little reason to
push their own followers to your platform instead of their own Substack or Patreon.
Giving them more when they bring the customer is how the largest course marketplaces get
instructors to market for them. The platform still earns on customers it spent nothing to
acquire, and the experts do your marketing.

**Rule of thumb:** a customer's lifetime value at the platform's share must be at least 3×
what you spend to acquire them. At about $58/mo and a typical 6–9 month subscription, the
platform earns roughly $350–520 per research subscriber. Platform-funded paid ads should
cost well under $120–170 per paying member, or not run at all.

## 3. Affiliate strategy

### Five affiliate tiers

| Tier | Who | Terms (proposal) | How to recruit |
|---|---|---|---|
| **1. Experts and instructors** | Everyone publishing on either platform | Channel split above, plus standard affiliate commission when they refer to *another* expert's product | Built into onboarding: every expert gets links on day one |
| **2. Members and students (referral)** | Paying customers | Give one month free / get one month free (research); 20% off for the friend + store credit for the referrer (courses) | Automatic invite after the 2nd month or at course completion |
| **3. Finance creators** | YouTubers, newsletter writers, podcasters, Discord/Telegram community owners in trading and technical analysis | Research: 20% of net for 12 months. Courses: 30% of net. Top performers: 25–40% | Agent finds and drafts personal pitches weekly; a human sends them |
| **4. Professional partners** | CMT chapters, trading-tool vendors (charting platforms, brokers' education teams), exam-prep providers | Co-branded discount codes, a revenue share or sponsorship, and content swaps | Founder-led partnership conversations |
| **5. Institutional referrers** | RIAs or consultants who introduce firms | A one-time introduction fee on signed firm licences | Warm network only |

### Rules every affiliate agrees to

These matter because this is financial content.
- **Disclosure:** every promotion says it is an affiliate link (FTC Endorsement Guides).
- **No performance claims:** no "made 40% last month", no "guaranteed", and no personal
  advice. Affiliates use the **approved swipe copy** the agent maintains, or submit their
  own copy for approval.
- **Banned channels:** spam, buying email lists, bidding on "NordStar Pro" or "Fincoursa"
  brand keywords, coupon-site leakage, and self-referral.
- **Payout terms:**
  - Commissions are held for 30–45 days, past the refund window, then paid monthly with a
    minimum payout (e.g. $50).
  - Refunds and chargebacks are clawed back.
  - Collect W-9 forms from US affiliates and W-8BEN forms from non-US affiliates. Check
    the current 1099 reporting threshold with your accountant.
- **RIAs and FINRA-registered reps** who accept referral fees may have their own disclosure
  or outside-business-activity obligations. They must handle those themselves, and the
  agreement should say so.
- **Cookie window:** 30 days, last-click. The NordStar Pro code already uses 30 days.

### Affiliate enablement kit

The agent produces and refreshes this kit each month:
- A one-page program overview with commission examples
- Swipe copy: 3 emails, 10 social posts, and a YouTube description block, each with the
  disclosure built in
- A monthly "content drop": a free chart or market note affiliates can share, which gives
  them something to post besides "buy this"
- Banners and a brand kit (wordmark spec, `#D6FD3A` on dark)
- A leaderboard and a monthly email with each affiliate's stats

## 4. The flywheel between the two platforms

```
 Fincoursa course (e.g. CMT exam prep, technical analysis)  ──►  student finishes
        ▲                                                          │
        │  "learn the method behind the research"                 ▼  "see it applied every week"
 NordStar Pro research subscriber  ◄────────────────  free NordStar Pro trial on course completion
```

- **The biggest opportunity is CMT exam-prep courses on Fincoursa**, taught by your CMT
  experts. Candidates are motivated, they pay, they stay in the field for years, and they
  are exactly the people who later subscribe to research and work at RIAs and
  institutions.
- **Attribution across platforms:** a customer an expert brought should stay credited to
  that expert across both platforms for 12 months. Use one shared affiliate ID per
  person.

## 5. Automation: what runs by itself vs. what a human approves

The engine is the Claude agent on scheduled runs, plus the tools listed under "Tools".

### Supply side: recruiting experts

| Trigger | Automated action | Human gate |
|---|---|---|
| Weekly | Agent researches 10–20 candidate experts: CMT charterholders who publish on LinkedIn, X, YouTube, or Substack. Scores audience size, consistency, and topic gaps in your coverage. | You choose who to contact |
| Approved candidate | Agent drafts a personal invite (`docs/emails/expert-invitation` already exists in the site repo) | Human sends |
| Expert signs | Onboarding sequence: contract, profile, first report template, their personal links, the affiliate kit, a "your first 30 days" plan | Contract signature |
| Expert's first 60 days | Agent sends weekly "your stats + 3 promotion ideas" emails | None (internal) |

### Demand side: selling the work

| Trigger | Automated action | Human gate |
|---|---|---|
| Expert publishes a report or lesson | Agent repurposes it into public teasers, social posts, and an insights page, with expert byline and trial or course link | Expert + you approve |
| Trial started | 5-email nurture sequence over 9 days (see `weekly-loop.md`) | Template approved once |
| Trial ends without paying | One "what stopped you?" email; replies go to a human | Template approved once |
| Course completed | Certificate + NordStar Pro trial offer + referral invite | Template approved once |
| Member's 2nd renewal | Referral invite (give a month / get a month) | Template approved once |
| Crypto renewal due within 7 days | Reminder sequence (exists in the code already) | — |
| Low engagement (no reads for 14 days) | "Here's what you missed" email featuring their expert | Template approved once |
| Cancellation | Exit survey + one win-back after 30–60 days | Template approved once |
| RIA / institution enquiry | Agent researches the firm and drafts a reply + due-diligence pack | Human sends and takes the call |

### Affiliate side

| Trigger | Automated action | Human gate |
|---|---|---|
| Weekly | Agent finds 5–10 finance creators, logs them in `partners.csv`, and drafts pitches | Human sends |
| Affiliate approved | Welcome kit, links, swipe copy, the rules | Approval |
| Monthly | Stats email to each affiliate, new content drop, leaderboard | None |
| Monthly | Agent audits affiliate posts it can find for missing disclosure or performance claims, and flags them | You act on flags |
| Monthly | Payout report (eligible past the hold, minus clawbacks) | **You pay.** Never automated money movement without review |

### Tools

- **NordStar Pro:** the built-in affiliate system for now. Resend, moving to Kit, for
  sequences.
- **Fincoursa:** while courses run on Thinkific, use its built-in affiliate feature and
  check that your plan tier includes it.
- **If you want recurring commissions and automated affiliate payouts without building
  them:** a Stripe-native affiliate tool such as Rewardful, FirstPromoter, or Tolt. This
  only covers card payments, not Cregis crypto.
- **Expert payouts:** Stripe Connect is the standard way to split marketplace revenue
  automatically. Crypto revenue would still need a manual monthly statement.
- **Social:** Postiz or Buffer. **Analytics:** GA4 + Search Console (after the site fixes
  are approved).

## 6. Gaps in the current code (not changed; for your decision)

| Gap | Where | Why it matters |
|---|---|---|
| Affiliate awards are % of the **first payment only** | `src/lib/affiliates.ts` → `awardFor` / `describeReward` | 12-month recurring commissions (the standard for subscriptions) aren't supported. Creators earn about $38 once instead of about $460 a year, which is much less attractive to recruit with. |
| No expert revenue-share or payout ledger | `prisma/schema.prisma` (Author has no share/payout fields) | The 70/30 split, channel-based splits, and monthly expert statements are manual today |
| No cross-platform customer or affiliate identity | Two separate codebases | Credit for a customer an expert brought can't follow them from Fincoursa to NordStar Pro |
| Fincoursa has no backend (UI prototype with mock data) | `ajoxf/Fincoursa_LMS` | Courses must stay on Thinkific, or a backend is needed, before any of this automates there |

## 7. 90-day sequence

1. **Weeks 1–2:**
   - Decide the split and affiliate terms (section 2), and update expert and instructor
     contracts.
   - Write the affiliate agreement with a lawyer.
2. **Weeks 2–4:**
   - Onboard the current experts as Tier 1 affiliates.
   - Build the enablement kit.
   - Turn on the trial and course-completion sequences.
3. **Weeks 3–8:**
   - Launch a CMT exam-prep or technical-analysis course on Fincoursa, taught by your best
     CMT expert, with a NordStar Pro trial bundled in.
   - Start member referrals.
4. **Weeks 4–12:**
   - Recruit 20–30 finance creators as Tier 3 affiliates. Expect about 10–20% to produce
     any sales, and 2–3 to produce most of them.
   - Weekly expert recruiting runs alongside.
5. **Week 12 review:**
   - Revenue by channel (platform / expert / affiliate) and platform margin per channel.
   - Top affiliates move to higher tiers; inactive ones are removed.
