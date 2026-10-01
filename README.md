# Hi, I'm Ardani 👋

Backend engineer. I build **data pipelines and API integrations** in Python —
the kind of glue that has to be boring, testable, and still working in six
months when nobody remembers why it was written that way.

**Focus:** ETL · API integration · automation · AI agents

## Current work

### [datakit — CSV/JSON/JSONL/XML converters](https://github.com/ardani13ln-byte/pipeline-toolkit)

Zero dependencies. No pip install, no lockfile, Python 3.10+.

```bash
python3 -m datakit csv jsonl < orders.csv
```

All 12 format pairs, streaming for files larger than RAM, and the error
behaviour that matters: a malformed row fails with **its source line number**
instead of becoming a silent `null` three layers downstream. 46 tests, ~1s.

It exists because every "convert CSV to JSON" snippet on the internet quietly
turns `007` into `7` and swallows short rows. See the
[comparison table](https://github.com/ardani13ln-byte/pipeline-toolkit#why-it-exists).

## How I work

- **Errors carry coordinates.** An error without a line number is an error
  you'll debug twice.
- **Dependencies are a cost, not a feature.** A library that sits inside
  someone else's cron job for years should never need a resolver.
- **Tests that cover the actual failure modes**, not the happy path — embedded
  delimiters, BOMs, non-seekable `stdin`, ragged rows, tag names starting with
  a digit.
- **Verify by running it.** Every claim in a README should be a command you
  pasted and watched succeed.

## Stack

Python 3.10+ · JSON Schema · REST/GraphQL integrations · PostgreSQL · Docker ·
GitHub Actions · Linux/bash · `unittest`, `pytest`, `httpx`

## Available for

ETL and data-migration work · API integrations and webhooks · automation of
repetitive spreadsheet/reporting flows · fixing pipelines that silently lose
rows · internal tools and CLIs.

**Remote.** Prefers async work with clear acceptance criteria. Small, concrete
tasks convert fastest — see [datakit](https://github.com/ardani13ln-byte/pipeline-toolkit)
for the standard I hold work to before handing it over.