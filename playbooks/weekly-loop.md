# Weekly loop

Each step names the skill or tool to use. Outputs go to `drafts/YYYY-WW/` for human
approval. Nothing is published or sent without approval (see `CLAUDE.md`).

## Monday: metrics report (30 min)

- Pull last week's numbers from GA4 (MCP), Search Console (`mcp-gsc`), and the admin export
  (members, trials, conversions, affiliate referrals).
- Report the funnel: visits → trial starts / sample requests → paid → churned, broken down
  by `utm_source` and `?ref=`.
- Name one thing to double down on and one thing to cut.
- Skills: `analytics` + `attribution` from `marketingskills`.

## Report day: content repurposing (per report)

Inputs come from the human: the report PDF/HTML **plus a note on what may go public**
(delayed, excerpt-only, or teaser).

1. **Public insight page** (`/insights/...`, 600–1,200 words). Include the thesis, key
   levels/catalysts, one chart, an author byline, the date, the disclaimer, and a trial
   CTA. Add FAQ and Article schema. Skills: `copywriting`, `ai-seo`, `schema`, and `claude-seo`
   schema checks.
2. **Social posts:** an X thread (5–8 posts), one LinkedIn post, and a 45-second
   short-video script, each with a UTM'd trial link. Queue them as drafts in Postiz or
   Buffer.
3. **Newsletter teaser** for the free list. This is opt-in only.
4. **Compliance self-check.** Before handing over, fail the draft if it contains
   personalised advice, performance promises, current paid content beyond the approved
   excerpt, or a missing disclaimer.

## Wednesday: nurture and retention

- **Trial users:** check the 5-step trial→paid sequence (day 0 welcome + how to read, day 2
  best section, day 4 archive highlight, day 6 trial ends + offer, day 9 last call). Adjust
  it based on open and click data.
- **Sample-report enquiries** (`PricingEnquiry` with status `new`): draft personal
  follow-ups for the human to send.
- **Crypto members** renewing in the next 7 days: confirm reminders went out.
- **Members with low read rates** (admin engagement panel): draft a "here's what you
  missed" check-in.
- **Churned members** 30–60 days ago: draft a single win-back email.
- Skills: `emails`, `onboarding`, `churn-prevention`.

## Thursday: partners (affiliates)

- Research 5–10 finance creators, newsletters, podcasts, or trading communities whose
  audience matches the product. Record follower counts, recent topics, and contact route
  in `partners.csv`.
- Draft individual partnership pitches with an affiliate slug and terms. This is B2B, so
  1:1 outreach to a creator's business contact is acceptable; a human sends it.
- Skills: `referrals`, `influencer-marketing`, `cold-email` (partner pitch only).

## Friday: SEO / GEO maintenance

- Use Search Console queries to refresh pages that rank between positions 5 and 20.
- Check AI-search citations (Otterly) for prompts like "best commodities research
  newsletter" or "weekly FX research subscription". Note which competitors get cited and
  why.
- Monthly: run a `claude-seo` technical audit of nordstarpro.com.
