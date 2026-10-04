# Open-source sales & marketing agents on GitHub (2026-10-04)

Star counts are approximate, taken from GitHub search on the date above. "Fit" is the fit
for NordStar Pro, a B2C financial-research subscription.

**Summary:** most standalone "AI SDR" apps are abandoned demos. The active, maintained work
in 2026 is in **Claude skill/plugin packs** and **official MCP servers**.

## Claude skills & plugins: start here

| Repo | ★ | Licence | Status | What it is | Fit |
|---|---|---|---|---|---|
| [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) | ~53k | MIT | Very active | 60+ skills: CRO, copywriting, emails, ai-seo, programmatic SEO, referrals, churn, ads, pricing, launch | **Core** |
| [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) | ~26k | Apache-2.0 | Official, active | Marketing & Sales plugins; connectors for HubSpot, Canva, Klaviyo, Ahrefs, SimilarWeb, Clay… | **Core** (connector wiring) |
| [AgriciDaniel/claude-seo](https://github.com/AgriciDaniel/claude-seo) | ~18k | MIT | Active | 26 sub-skills: technical SEO, E-E-A-T, schema, GEO/AEO, backlinks; PDF reports | **Core** |
| [AgriciDaniel/claude-blog](https://github.com/AgriciDaniel/claude-blog) | ~2.3k | — | Main dev in a paid community | Blog pipeline | Optional |
| [nowork-studio/notfair-plugin](https://github.com/nowork-studio/notfair-plugin) | ~3.9k | MIT | Active | SEO/GEO + Google/Meta Ads skills | Later, for ads |
| [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | ~27.6k | — | Active | 380+ skills, broad but uneven | Browse only |
| [zubair-trabzada/ai-marketing-claude](https://github.com/zubair-trabzada/ai-marketing-claude) | ~2.7k | MIT | Single push (Mar 2026) | 15 skills | Skip (unmaintained) |
| [zubair-trabzada/ai-sales-team-claude](https://github.com/zubair-trabzada/ai-sales-team-claude) | ~1.4k | MIT | One-time release | B2B BANT/MEDDIC sales skills | Skip (B2B) |

## Analytics & ads MCP servers

| Repo | ★ | Licence | Notes | Fit |
|---|---|---|---|---|
| [googleanalytics/google-analytics-mcp](https://github.com/googleanalytics/google-analytics-mcp) | ~3.4k | Apache-2.0 | **Official** GA4, read-only | **Core** (after GA4 is installed on the site) |
| [AminForou/mcp-gsc](https://github.com/AminForou/mcp-gsc) | ~1.8k | MIT | Search Console | **Core** |
| [googleads/google-ads-mcp](https://github.com/googleads/google-ads-mcp) | ~1k | Apache-2.0 | **Official** Google Ads, mostly read | Later |
| [pipeboard-co/meta-ads-mcp](https://github.com/pipeboard-co/meta-ads-mcp) | ~1.3k | Non-standard | Funnels to the hosted vendor service | Check licence first |
| [iannuttall/seo](https://github.com/iannuttall/seo) | ~550 | — | 70+ local audit tools on your own GSC/GA4 data; young | Watch |
| irinabuht12-oss/google-ads-meta-ads-mcp | ~3.7k | MIT | README for a hosted vendor (Ryze) | Vendor product |
| cohnen/mcp-google-ads | ~700 | — | Stale since 2025-10 | Use the official one instead |

## Social media

| Repo | ★ | Licence | Notes | Fit |
|---|---|---|---|---|
| [gitroomhq/postiz-app](https://github.com/gitroomhq/postiz-app) | ~36.7k | AGPL-3.0 | Production-grade self-hosted scheduler with AI/agent hooks | **Core** (or Buffer) |
| [langchain-ai/social-media-agent](https://github.com/langchain-ai/social-media-agent) | ~2.8k | MIT | LangGraph curate→draft→human approve→schedule | Reference design |
| ZJU-REAL/Easel | ~3.1k | Apache-2.0 | Built for Chinese platforms | No |
| ScrapeCreators/social-media-research-skills | ~3.2k | — | Funnel to a paid API | Optional |

## Sales outreach / SDR

| Repo | ★ | Licence | Status | Fit |
|---|---|---|---|---|
| [eracle/OpenOutreach](https://github.com/eracle/OpenOutreach) | ~3.2k | GPL-3.0 | Active, Docker; ICP→licensed data→email from your mailbox | B2B only (e.g. a team licence for funds/RIAs) |
| filip-michalsky/SalesGPT | ~2.8k | MIT | **Abandoned** (last push 2024-09) | Reference only |
| kaymen99/sales-outreach-automation-langgraph | ~400 | None | Stale demo, no licence | No |
| iPythoning/b2b-sdr-agent-template | ~190 | MIT | Early, export-business niche | No |
| mayooear/ai-company-researcher | ~215 | — | Archived | No |

## CRM

| Repo | ★ | Notes | Fit |
|---|---|---|---|
| [twentyhq/twenty](https://github.com/twentyhq/twenty) | ~58k | Leading open-source CRM | Not needed yet: the site's admin already acts as the CRM (Member, PricingEnquiry, Affiliate, Referral) |
| trycompai/crm | ~11k | "Agent-first", new (Jul 2026), unproven | Watch |
| stickerdaniel/linkedin-mcp-server | ~3.7k | Scrapes LinkedIn | **Avoid** (ToS / ban risk) |
| Apollo MCP servers | <10 each | Toys | Avoid |

## Frameworks

- **Claude Agent SDK + skills + MCP:** where most 2026 momentum is. Most active repos above
  target it, and it is what this project uses.
- **LangGraph:** best for long-running agents with human-approval interrupts.
- **n8n:** common GTM automation glue. [enescingoz/awesome-n8n-templates](https://github.com/enescingoz/awesome-n8n-templates) (~25.7k★).
- **CrewAI** (~59k★): popular for demos, but nearly every "CrewAI marketing team" repo is a
  tutorial with very few stars.
