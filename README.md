# GTM Health Scorecard

A Claude Code skill that diagnoses any company's GTM infrastructure health in 60 seconds.

Give it a domain. It scrapes their career page, detects their tech stack, reads their job descriptions, and scores them across 7 dimensions of GTM infrastructure maturity. No API keys. Free data only.

## What It Produces

```
═══════════════════════════════════════════
  GTM HEALTH SCORECARD: Warmly
  warmly.ai | Website visitor identification + intent
═══════════════════════════════════════════

  Overall: 4/10 🟡

  1. Sales/Ops Ratio       🔴 2/10  6 revenue roles, 0 ops — no denominator
  2. Enrichment Maturity   🟢 7/10  Dogfooding their own enrichment product
  3. Outbound Infra        🟡 5/10  No sequencing tool; likely HubSpot sequences
  4. Data Hygiene          🔴 3/10  SDR JDs include "manage pipeline data"
  5. Automation Signals    🟡 4/10  Zapier only — no integration layer
  6. Role Scope Creep      🔴 2/10  SDRs doing CRM admin + process docs
  7. Ops Hire Timing       🔴 2/10  Series A+, 40 employees, zero ops hires

  DIAGNOSIS: Severe GTM infrastructure gap. SDRs spending
  30-40% of time on non-selling work.

  PRIORITY FIXES:
  1) RevOps hire — before next SDR quits
  2) Remove ops work from SDR job descriptions
  3) Outreach/Salesloft for dedicated outbound
═══════════════════════════════════════════
```

## The 7 Dimensions

Built from direct GTM Engineering experience — building enrichment workflows and AI qualification systems for enterprise clients, and having been the SDR suffering without infrastructure.

| # | Dimension | What It Catches |
|---|-----------|----------------|
| 1 | **Sales/Ops Ratio** | Scaling sellers without ops support |
| 2 | **Enrichment Maturity** | SDRs manually researching vs using Apollo/Clay/ZoomInfo |
| 3 | **Outbound Infrastructure** | Sequencing tools vs sending from Gmail |
| 4 | **Data Hygiene** | CRM admin dumped on sellers vs owned by ops |
| 5 | **Automation Signals** | Tools connected via Zapier/Make vs manual CSV exports |
| 6 | **Role Scope Creep** | "Wearing many hats" = no infrastructure |
| 7 | **Ops Hire Timing** | When the company should have hired ops vs when they did |

## Install

```bash
# Clone into your Claude Code skills directory
git clone https://github.com/lucasvibecoder/gtm-scorecard.git ~/.claude/skills/gtm-scorecard

# Install dependency
pip install httpx
```

## Usage

In Claude Code:

```
/gtm-scorecard ramp.com
```

Or just say:

```
Score the GTM health of ramp.com
```

## How It Works

1. **Homepage scrape** → detects GTM tools from HTML signatures (Salesforce, HubSpot, Outreach, Apollo, Gong, Segment, Zapier, 30+ others)
2. **Career page discovery** → tries common paths + Greenhouse/Lever/Ashby job boards
3. **Role classification** → categorizes open roles as SDR, AE, RevOps, GTM Engineer, etc.
4. **JD deep-dive** → reads individual job descriptions for strain signals (CRM admin in sales roles, "wearing many hats," manual prospecting, spreadsheet tracking)
5. **Claude analysis** → scores each dimension using the framework + Claude's knowledge of the company

Zero API keys. Zero cost. Just `httpx` and public web pages.

## Data Sources

All free:
- Company homepage HTML (tech stack detection via script/pixel signatures)
- Career pages (direct paths + Greenhouse/Lever/Ashby boards)
- Individual JD pages (strain signal parsing)
- Claude's training data (company context, funding stage, headcount)

## What This Is For

- **Consulting:** Walk into calls with a pre-built diagnosis
- **Outbound:** Lead with evidence instead of generic pitches
- **Competitive intel:** Score your prospect's infrastructure gaps
- **Self-assessment:** Score your own company honestly

## License

MIT
