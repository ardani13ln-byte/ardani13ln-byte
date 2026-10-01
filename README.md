# Hi, I'm Ardani 👋

Backend engineer. I build **data pipelines and API integrations** in Python —
the kind of glue that has to be boring, testable, and still working in six
months when nobody remembers why it was written that way.

**Focus:** ETL · API integration · automation · AI agents

## Selected work

### [api-sync — REST client with retries, pagination, idempotency](https://github.com/ardani13ln-byte/api-sync)

Zero dependencies, Python 3.10+.

```bash
python3 examples/sync_demo.py     # runs end-to-end, no setup
```

Most integrations are written for the happy path and fail at 2am. This one
treats the unhealthy path as the main event: bounded backoff with **full
jitter**, `Retry-After` honoured in both its forms, `401`/`403` raised
immediately instead of burning the retry budget, cursor pagination that cannot
loop forever, and idempotency keys that stop a timed-out `POST` from creating
the order twice.

88 tests. The `Transport` seam means the failure paths are verified without a
network or a single `sleep` — and `tests/helpers.py` runs a real local HTTP
server too, so the wire behaviour is checked for real.

### [datakit — CSV/JSON/JSONL/XML converters](https://github.com/ardani13ln-byte/pipeline-toolkit)

Zero dependencies. No pip install, no lockfile.

```bash
python3 -m datakit csv jsonl < orders.csv
```

All 12 format pairs, streaming for files larger than RAM, and the error
behaviour that matters: a malformed row fails with **its source line number**
instead of becoming a silent `null` three layers downstream. 46 tests, ~1s.

It exists because every "convert CSV to JSON" snippet on the internet quietly
turns `007` into `7` and swallows short rows. See the
[comparison table](https://github.com/ardani13ln-byte/pipeline-toolkit#why-it-exists).

**134 tests between the two, all passing, no dependencies in either.**

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
tasks convert fastest — see [api-sync](https://github.com/ardani13ln-byte/api-sync)
for the standard I hold work to before handing it over.