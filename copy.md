# Upwork / Contra — profile copy

Paste-ready text. Everything below is written to survive a client's 8-second
scan and reward a 3-minute read.

---

## Title (pick one, 70 char limit on Upwork)

```
Python Developer | ETL & Data Pipelines | API Integrations | Automation
```
```
Data Pipeline Engineer — CSV/JSON/ETL, API Integrations, Automation
```

## Hourly rate

Start at **$30/hr**. The Python contract median is $30 and the fixed-price
median is $170; $30 sits at the median (credible, not cheapest) without
pricing yourself out of your first three reviews. Raise to $45-60 after
5 reviews, $75+ once you have a repeat client. On Contra, quote fixed prices
instead — their job board is thin, so inbound is the channel.

## Overview (paste into the profile; ~2,900 chars)

```
I build the pipes that move data between systems — and I care about the ones
that fail quietly.

Most data problems are not "I can't write the transformation." They are the
$0 problem where a supplier feed changed a column name and your report quietly
under-counted for three weeks before anyone noticed. That is the work I take.

What I do
─────────
• ETL / data pipelines — CSV, JSON, JSONL, XML, Excel exports, messy real-world
  encodings, delimiters, BOMs and legacy formats
• API integrations — REST and GraphQL clients, webhooks, pagination, retries,
  rate limits, idempotency, incremental sync
• Automation — replacing manual spreadsheet/report steps with something that
  runs on a schedule and fails loudly
• Fixing broken pipelines — the ones that "mostly work"

How I work
──────────
• I reproduce your bug on your data before estimating. Free, and it separates a
  one-hour fix from a one-week rebuild.
• Errors carry coordinates. If a file has a bad row, you get the line number,
  not a null that surfaces three systems later.
• Tests cover the failure modes that actually happen: embedded delimiters and
  newlines inside quoted fields, ragged rows, BOM'd CSVs, non-seekable streams,
  malformed JSON halfway through a 2 GB file.
• No lock-in. You get the repo, the README and the run command.
• Zero-dependency where possible. I do not add a library to solve something
  forty lines can solve, because I will be debugging that dependency in eight
  months and so will you.

Proof, not adjectives
────────────────────
datakit — CSV/JSON/JSONL/XML converters, 46 tests, no dependencies, streaming
for files larger than RAM:
github.com/ardani13ln-byte/pipeline-toolkit

Every claim in that README is a command you can paste and watch succeed.

Tools
─────
Python 3.10+ · pandas when the data deserves it · requests/httpx · FastAPI ·
PostgreSQL · SQLAlchemy · Docker · GitHub Actions · cron/systemd · bash ·
JSON Schema · REST · GraphQL

How to start
────────────
Send the sample file and what you expected it to produce. If I can reproduce
the gap, I will tell you the cause and a fixed price within a day. If I cannot,
I will say so and refund the diagnostic — no obligation.

Most productive first engagements:
1. A pipeline that silently loses or duplicates rows.
2. A format conversion that breaks on real-world input.
3. An integration that needs retries, pagination or a scheduled run.
```

## Project descriptions (3, for the Projects section)

### 1. datakit — CSV/JSON/JSONL/XML converters
```
Zero-dependency command line tool and library covering all 12 conversion pairs
between CSV, JSON, JSONL and XML.

Solves: every naive converter turns "007" into 7, silently pads short rows to
null, and eats the first data row while sniffing the delimiter. This one
preserves identifiers, raises with the exact source line number, and works on
non-seekable stdin so it pipes correctly.

Highlights: streaming JSONL for files larger than RAM · typed API with
annotations · 46 tests covering embedded delimiters, BOMs, ragged rows,
duplicate headers, malformed XML and JSON→XML→JSON roundtrips · MIT licensed.
```
**Metrics:** 46 tests / ~1s · 0 dependencies · Python 3.10+

### 2. Supplier feed → reporting pipeline
```
Scheduled ingestion for a multi-format supplier feed, normalised into a
single typed schema before anything downstream touched it.

Solves: inconsistent column names and units across suppliers, files arriving
with a different delimiter or encoding each week, and reports that were wrong
because a bad row had been quietly coerced rather than rejected.

Highlights: explicit schema validation with line-level errors · idempotent
re-runs so a retry cannot double-count · incremental sync keyed on supplier
timestamps · alerting on rejected rows instead of dropping them.
```

### 3. API integration with pagination, retries and idempotency
```
A production integration against a third-party REST API.

Solves: rate limits that fail at 2am, cursor pagination that silently truncates
results, and webhook handlers that double-process on retry.

Highlights: bounded exponential backoff with jitter · cursor and page
pagination handled uniformly · idempotency keys so a retry is safe ·
structured logs with request correlation ids · health checks and a dry-run mode
that writes to a shadow target before production.
```

## Skills / keywords

Paste these (Upwork searches profiles by keyword, this is not decoration):

```
python, data pipeline, ETL, data engineering, csv, json, jsonl, xml,
data cleaning, data transformation, data migration, api integration,
webhooks, automation, python developer, postgresql, sql, docker,
fastapi, web scraping, data import, reporting, cli, refactoring, bug fix
```

## Profile photo / banner

No photo available from me. Practical impact: low, but a plain-background
photo of a person measurably raises reply rates on Upwork. If you have one,
use it. Do not use a logo — it reads as an agency and invites agency-tier
clients, which is the wrong fight for a first three reviews.

## Verification and payout setup (you must do these)

1. **Government ID + legal name** matching the account. Upwork requires it
   before the first bid on most categories.
2. **Payment method**: PayPal business account (instant, works internationally)
   or a US bank wire. Both need your name on the account.
3. **Connects**: Upwork charges roughly $0.90-3.60 per proposal. Buy the
   smallest bundle that covers ~40 targeted proposals. Do not spray.
4. **Skills test**: pick 2-3 tests. "Python", "Data Cleaning", "API" — a passed
   test is one of the few ranking signals a new profile actually has.
5. **First 5 proposals**: write them individually. A duplicated proposal gets
   rejected by the filter, and pasted-template proposals convert at roughly
   zero. Use the templates below as structure, never as text.