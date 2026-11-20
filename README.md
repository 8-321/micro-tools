# Micro-tools — 9 working tools rebuilt from AI startups

Nine single-page tools, each modeled on the real product flow of a YC-backed company.
No backend, no API keys, no build step. Open a folder, paste your own data, get an output you can copy or download.

Live: https://8-321.github.io/micro-tools/

| # | Tool | What it does | Benchmark |
|---|---|---|---|
| 01 | [Inbox → Actions](inbox/) | Chat thread → tasks with due dates, open questions, draft replies, tomorrow brief | Caddy (caddy.app) |
| 02 | [Visa Pack Builder](visa/) | Route + citizenship → document checklist, timeline, fees, refusal reasons, progress | Veeza AI (veeza.ai) |
| 03 | [Group Plan Finder](group/) | Group chat → ranked time slots, invite/poll text, booking brief | Anywhere / Alfi (text.ai) |
| 04 | [Career Story Builder](career/) | Ten answers → three pitches, privacy switches, warm-intro email, agent-readable JSON | Pluto (talentpluto.com) |
| 05 | [Application Kit](apply/) | JD + resume → keyword gap, cover letter, screening answers, application tracker | Tsenta (tsenta.com) |
| 06 | [Backtest Lab](backtest/) | Daily prices → equity curve, CAGR, max drawdown, win rate vs buy-and-hold | Scalar Field (scalarfield.io) |
| 07 | [Portfolio X-Ray](portfolio/) | Holdings + targets → weights, concentration flags, rebalance share counts | Volaren (volaren.ai) |
| 08 | [Trade Brief](tradebrief/) | Idea + entry/stop/target → position size, R multiple, invalidation list, journal row | Conviction (convictiontrade.ai) |
| 09 | [Alert Forge](alert/) | Conditions → Pine Script v5 alert block, plain-English rule, confluence score | Instinct (instinct.xyz) |

## Run locally

```powershell
cd micro-tools
python -m http.server 8899
# open http://127.0.0.1:8899/
```

Opening `index.html` directly works for most pages, but `file://` blocks the shared
`assets/base.js` under the CSP, so use a local server.

## Structure

```
index.html            hub
assets/base.css       shared design system
assets/base.js        copy / download / csv / storage helpers
<tool>/index.html     one self-contained tool per folder
```

Every page carries its own CSP (`default-src 'none'`, `connect-src 'none'`), so a tool
cannot phone home even if someone edits it later.

## What is deliberately missing

These are the parts a startup has and a static page does not: live market data, broker
connections, calendar/email APIs, model access for free-text generation. Everything here
is either arithmetic, a curated rule set, or a parser you can read in one sitting.

That is also the honest limit: the tools are the thinking, not the integration.

## License

Source is provided as-is for personal and commercial use. The company names above are
references to publicly documented products, not affiliations.

## Buy / download

- Capafy listing (9 installable skills, one folder each with SKILL.md): **live**, US$39 → https://capafy.ai/agent/9-micro-tools-rebuilt-from-ai-startups/8720081509?ct=mt_github
- Skill-pack ZIP: `micro-tools-9skills-capafy.zip` (37 files, 9 x SKILL.md)
- Free live preview: https://8-321.github.io/micro-tools/

