# GTM Health Scorecard

A Claude Code skill that diagnoses any company's GTM infrastructure health in 60 seconds.

Give it a domain. It researches their career page, reads their job descriptions, detects their tech stack, and scores them across 7 dimensions of GTM infrastructure maturity. No API keys. No dependencies. Just web search.

Built from direct GTM Engineering experience at Clay — building enrichment workflows and AI qualification systems for enterprise clients, and having been the SDR suffering without infrastructure.

## What It Produces

```
═══════════════════════════════════════════
  GTM HEALTH SCORECARD: Warmly
  warmly.ai | Autonomous revenue orchestration for SMB teams
  Series A · ~65 employees · $22.1M raised
═══════════════════════════════════════════

  ⚡ 3 RED FLAGS

  1. Role Scope Creep: 🔴 2/10
     Your "Founding Strategic Account Executive" JD includes
     prospecting, booking demos, AND "assisting in developing
     sales strategies and improving processes." That's an AE
     doing SDR work plus ops work plus building the playbook
     from scratch. Sellers miss quota or processes don't get
     built. Usually both.

  2. Sales/Ops Ratio: 🔴 3/10
     Multiple sales roles posted (AE, Strategic AE, SDR) with
     zero RevOps, Sales Ops, or GTM Ops roles anywhere. You sell
     a revenue orchestration platform but haven't hired the person
     who orchestrates your own revenue operations.

  3. Data Hygiene: 🟡 4/10
     No ops roles means nobody owns CRM quality, process
     documentation, or system maintenance. At 65 people you're
     past the stage where "everyone just knows" how things work.

  ─── FULL DIAGNOSTIC ───

  Overall: 5/10 🟡

  1. Sales/Ops Ratio       🔴 3/10  Multiple sales roles, 0 ops roles posted
  2. Enrichment Maturity   🟢 7/10  Integrates with Apollo; dogfooding own product
  3. Outbound Infra        🟢 8/10  HubSpot + Outreach + own orchestration platform
  4. Data Hygiene          🟡 4/10  No ops layer to own CRM/process maintenance
  5. Automation Maturity   🟢 8/10  Selling automation = likely dogfooding own product
  6. Role Scope Creep      🔴 2/10  AEs prospecting + building processes + selling
  7. Ops Hire Timing       🟡 4/10  65 people, Series A, no ops roles = overdue

  DIAGNOSIS: Warmly is scaling a revenue orchestration product
  without dedicated revenue operations infrastructure. The
  "Founding Strategic AE" language reveals the pattern: sellers
  are building the playbook while carrying quota. Automation
  without an ops layer means nobody owns configuration,
  optimization, or scaling the systems as the team grows.

  PRIORITY FIXES:
  1) Hire first RevOps/GTM Ops — "Founding Strategic AE" building
     processes = you're 6 months late
  2) Separate SDR and AE functions — AEs prospecting + booking
     demos = blurred roles that slow down both motions
  3) Document current systems before they break — next hire
     doesn't know what's automated vs manual

  ─── OUTREACH BRIEF ───

  Target: Max Greenwald, Co-Founder & CEO
  Why them: At 65 people Series A, CEO still directly feels
            GTM pain. "Founding Strategic AE" language suggests
            he's involved in building the playbook.
  Angle: Lead with Red Flag #1 — Role Scope Creep
═══════════════════════════════════════════
```

## The 7 Dimensions

| # | Dimension | What It Catches |
|---|-----------|----------------|
| 1 | **Sales/Ops Ratio** | Scaling sellers without ops support |
| 2 | **Enrichment Maturity** | SDRs manually researching vs using Apollo/Clay/ZoomInfo |
| 3 | **Outbound Infrastructure** | Sequencing tools vs sending from Gmail |
| 4 | **Data Hygiene** | CRM admin dumped on sellers vs owned by ops |
| 5 | **Automation Maturity** | Tools connected via Zapier/Make vs manual CSV exports |
| 6 | **Role Scope Creep** | "Wearing many hats" = no infrastructure |
| 7 | **Ops Hire Timing** | When the company should have hired ops vs when they did |

## Install

```bash
git clone https://github.com/lucasvibecoder/gtm-scorecard.git ~/.claude/skills/gtm-scorecard
```

That's it. No pip install. No API keys. No config.

## Usage
```
# Slash command
/gtm-scorecard ramp.com

# Or just tell Claude Code what you want
Score the GTM health of warmly.ai and run the prospect workflow — find the best contact and draft outreach

# Batch
Score these companies using the gtm-scorecard: warmly.ai, attio.com, ramp.com
```

## How It Works

1. **6 targeted web searches** — company info, SDR/AE hiring, ops hiring, JD deep-dive, tech stack, team structure
2. **7-dimension scoring** — each dimension scored 1-10 with specific evidence and "what most people miss" insights
3. **3 red flags first** — the biggest infrastructure gaps, highlighted for quick action
4. **Priority fixes** — what to fix, in what order, and why
5. **Prospect mode** — finds the right contact and drafts evidence-based outreach

Zero dependencies. Claude Code's native web search does all the data gathering.

## What This Is For

- **Consulting:** Walk into calls with a pre-built diagnosis
- **Outbound:** Lead with evidence instead of generic pitches
- **Job hunting:** Score a company before you interview there
- **Competitive intel:** Map your prospect's infrastructure gaps

## Demos

- [Ramp (8/10) — what "good" looks like](demos/demo-ramp.md)
- [Consulting DM example using scorecard output](demos/example-output.md)

## Framework Origin

Built from direct GTM Engineering experience at Clay — building enrichment workflows, AI qualification systems, and multi-stage automation pipelines for enterprise clients. The dimensions come from watching dozens of companies go through the exact moment when their manual GTM workflows stop scaling. The "What most people miss" insights come from being the SDR who suffered without infrastructure AND the engineer who built it after.

## License

MIT
