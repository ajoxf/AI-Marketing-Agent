# AI Marketing & Sales Agent: NordStar Pro

This is the research and operating plan for an AI agent that handles marketing and sales for
**[nordstarpro.com](https://nordstarpro.com)**. NordStar Pro is a $199/month financial
research membership. Members get four weekly reports: commodities, international markets
and indices, options/crypto/spreads, and FX. They pay by card (Stripe) or crypto (Cregis).
The site also offers free trials, an affiliate program, and a "sample report" enquiry form.

Research was done on 2026-10-04. The details are in the files below.

| File | What's in it |
|---|---|
| [`research/github-agents.md`](research/github-agents.md) | Open-source sales and marketing agents, Claude skills, and MCP servers, each rated |
| [`research/commercial-tools.md`](research/commercial-tools.md) | Hosted AI SDRs, chat, SEO/GEO, social, ads, voice, and email tools, with prices and evidence |
| [`CLAUDE.md`](CLAUDE.md) | The agent's operating brief: business facts, funnel links, voice, and compliance guardrails |
| [`playbooks/`](playbooks/) | Weekly loop, go-to-market plan, marketplace sales and affiliates, Fincoursa plan, B2B plan |

---

## The short answer

**Most "AI SDR" products are the wrong tool for NordStar Pro.** They are designed for B2B
companies booking meetings with business contacts. NordStar Pro sells a **consumer
subscription to investment research**, which changes two things:

1. **Cold outreach to consumers is legally risky.** Under GDPR/PECR, B2C email generally
   needs consent. Under TCPA, AI voice calls to US cell phones need prior express written
   consent. A $199/month research product is also bought on trust, not by being emailed
   500 times. AI SDR churn is reported at 50–80% even for the B2B companies these tools are
   built for.
2. **Financial-promotion rules apply to everything the agent writes.** In the US, a research
   publisher stays outside investment-adviser registration only while it publishes
   *impersonal* research (see *Lowe v. SEC*). An AI chat or sales agent that tells a
   prospect "you should buy X" or "this fits your portfolio" can break that. Performance
   claims also fall under FTC truth-in-advertising rules. UK and EU audiences add
   financial-promotion rules (FCA) and the EU AI Act chatbot-disclosure rule (Art. 50, live
   since Aug 2026). **Have a lawyer confirm your position before scaling.**

The approach that works for a subscription research business is **"content-led, with the
agent as a tireless marketing operator and a human approving everything public"**:

```
   Weekly reports (your unfair advantage: original, expert, recurring)
                │
                ▼
   ┌──────────────────────── AI agent (Claude Code + skills + MCP) ────────────────────────┐
   │ 1. Repurpose: free market notes, charts, X/LinkedIn threads, YouTube/short scripts,  │
   │    newsletter teaser. Lagged or partial, never the paid report itself.               │
   │ 2. SEO + GEO: public market-commentary pages, expert pages, FAQ/schema, AI-search    │
   │    citation tracking                                                                 │
   │ 3. Nurture: sample-report enquiries and trial users → email/WhatsApp sequences       │
   │    (opt-in only)                                                                     │
   │ 4. Partners: find and brief finance creators for the existing ?ref= affiliate        │
   │    program                                                                           │
   │ 5. Retention: crypto-renewal reminders, low-read-rate members, win-back              │
   │ 6. Analytics: weekly GA4 + Search Console + Stripe funnel report                     │
   └───────────────────────────────────────────────────────────────────────────────────────┘
                │  every public output → human approval queue (compliance check)
                ▼
     /trial?item=…  →  /join  →  paid member  →  retained member
```

## Recommended stack (best of GitHub + commercial)

**Agent runtime:** Claude Code (or the Claude Agent SDK for scheduled runs) with this repo
as its workspace. The `CLAUDE.md` file gives it the business context and guardrails.

| Layer | Pick | Why | Cost |
|---|---|---|---|
| Marketing skills | [`coreyhaines31/marketingskills`](https://github.com/coreyhaines31/marketingskills) (~53k★, MIT) | Category leader: 60+ skills (CRO, copy, email, SEO/AI-SEO, launch, pricing) | Free |
| SEO / GEO skills | [`AgriciDaniel/claude-seo`](https://github.com/AgriciDaniel/claude-seo) (~18k★, MIT) | Technical SEO, E-E-A-T, schema, GEO audits | Free (+ optional DataForSEO) |
| Connector wiring | [`anthropics/knowledge-work-plugins`](https://github.com/anthropics/knowledge-work-plugins) Marketing plugin | Official; wires Canva, Klaviyo, Ahrefs, HubSpot, etc. | Free |
| Analytics data | Official [GA4 MCP](https://github.com/googleanalytics/google-analytics-mcp) + [`mcp-gsc`](https://github.com/AminForou/mcp-gsc) (Search Console) | Read-only, trustworthy | Free |
| Social publishing | [Postiz](https://github.com/gitroomhq/postiz-app) (self-host) **or** Buffer | Schedule X / LinkedIn / YouTube / Instagram from agent drafts | Free / ~$6/channel |
| Email nurture | Resend (already integrated) → Kit.com later (the codebase already has a `NotificationProvider` seam for Kit) | Opt-in sequences for trial users and enquiries | Low |
| AI-search visibility | Otterly.AI | Track whether ChatGPT/Perplexity/AI Overviews cite NordStar Pro | ~$29/mo |
| Website chat (optional) | Tidio Lyro, restricted to FAQ/billing/access answers, with AI disclosure | Handles "how do I redeem my code?"; **must not give investment advice** | ~$79/mo |
| Ads (later, small tests) | Google Search on high-intent terms; check financial-services/crypto ad eligibility first | Platforms restrict finance and crypto ads | Media spend |

**Skipped on purpose:** 11x / Artisan / Qualified ($36K+/yr, B2B meetings, high churn), AI
cold-calling (TCPA), LinkedIn scraping MCPs (ToS and account-ban risk), and mass AI blog
generation (Google "scaled content abuse"). OpenOutreach (best open-source SDR) is only
worth considering for **B2B** prospects such as family offices, RIAs, or prop desks, if you
ever sell a team or enterprise licence.

## Set it up

```bash
# 1. Skills (run inside this repo)
npx skills add coreyhaines31/marketingskills -a claude-code
npx skills add AgriciDaniel/claude-seo        # or follow its README's plugin install

# 2. In Claude Code: install Anthropic's marketing plugin
/plugin marketplace add anthropics/knowledge-work-plugins
/plugin install marketing@knowledge-work-plugins

# 3. Data MCP servers. Follow each README for Google service-account auth:
#    googleanalytics/google-analytics-mcp, AminForou/mcp-gsc
```

Check each project's README for the current install syntax before running these; plugin
CLIs change often.

## Quick wins found in the nordstarpro.com codebase (`ajoxf/NorthStar-Research`)

Do these **before** spending on any agent tooling. The agent cannot measure or improve what
the site doesn't track.

1. **No web analytics is installed.** No GA4, Plausible, PostHog, or Vercel Analytics was
   found. Add one, with conversion events for `trial_started`, `sample_requested`,
   `checkout_started`, and `member_activated`.
2. **The sitemap lists only 5 URLs** (`src/app/sitemap.ts`). It leaves out `/coverage`,
   `/experts`, and every `/experts/[slug]` page, which are the most search-worthy public
   pages on the site.
3. **There is no public, indexable content.** Everything valuable is behind the paywall. A
   `/insights` section with free, delayed or excerpted market notes is the single biggest
   SEO and GEO lever. Each piece needs author bylines (E-E-A-T), date, disclaimer, and a
   trial CTA.
4. **UTM capture.** Referral attribution exists (`?ref=`, 30-day cookie). Store
   `utm_source/medium/campaign` the same way, so the agent's weekly report can say which
   channel produced paying members, not just visits.
5. **Use the trial link for top-of-funnel CTAs everywhere** (`/trial?item=<slug>`). The
   codebase's own WhatsApp guide already notes that `/join` is a two-step flow that stalls
   on the access-code email.

## 90-day rollout

| Weeks | Focus | Success metric |
|---|---|---|
| 1–2 | Analytics + sitemap + UTM fixes; install skills; agent runs a CRO + SEO audit of the site | Funnel visible end-to-end |
| 3–6 | Weekly content engine: agent drafts 1 public insight page + 5–10 social posts per report cycle, human approves | Indexed pages, trial starts per week |
| 5–8 | Nurture: 5-email trial→paid sequence + sample-enquiry follow-up (opt-in) | Trial→paid conversion % |
| 6–10 | Affiliates: agent researches 30–50 finance creators/newsletters and drafts personalised partnership pitches; human sends | Active affiliates, referred revenue |
| 8–12 | Retention: crypto-renewal reminders, low-engagement member check-ins, win-back | Monthly churn % |
| 12 | Review: cut any channel or tool without measurable lift in paid members | Cost per paid member by channel |
