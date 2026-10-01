# Proposal templates

**How to use these.** Upwork flags duplicate proposal text and pasted-template
proposals convert at close to zero. So: pick the matching template, then rewrite
every sentence in your own words with the client's actual nouns. Keep the
*structure* (hook → diagnosis → proof → concrete offer) because the structure
is what works. Delete anything you cannot make true.

**Before you send any of them**, you need the job's actual text in front of you.
Six sentences of personalisation beats any template.

---

## Template A — "our data is wrong" / pipeline bugs

```
Hi [Name],

"[Their exact symptom, in their words]" is usually one of three things, and I
can tell you which without a three-week engagement.

[Diagnostic sentence based on the job text — e.g. the counts differ between
the raw file and the report, which points at the join or the filter rather
than the loader.]

What I'd do:
1. Reproduce it on a sample of your real file — your data, not a fixture.
   Free, and it tells us whether this is a one-hour fix or a rebuild.
2. Show you the exact rows and line numbers where the two outputs disagree.
3. Fix it with a test per failure mode, so it stays fixed.

On rate: I've quoted [X] for [scope] because that's what step 2 actually
comes back with. If it turns out to be simpler, you pay the smaller number.

[Link to one relevant repo or a 3-line code sample, not a wall.]

Happy to start with the diagnostic before you commit to anything.
```

## Template B — format conversion / data migration

```
Hi [Name],

[Specific detail from the job text — file type, volume, where it comes from.]

The reason this migration usually goes sideways is the input, not the
transformation: [delimiter that changes between exports / BOM on Windows
exports / multi-line fields inside quoted cells / a column that is a string
on one supplier and a number on the next]. The conversion itself is the easy
part.

Proposed approach:
- Parse and validate against an explicit schema, so a changed column name
  fails loudly on day 1 instead of silently on day 30
- Reject bad rows with their line numbers, into a report you can send back to
  the supplier
- Idempotent re-runs, so a retry can't double-count

Deliverable: the script, the test suite, a README with the run command, and a
sample output from your data.

[Price] fixed, [timeline]. [One relevant proof link.]
```

## Template C — API integration

```
Hi [Name],

[One sentence proving you read the post — name the endpoint, the auth scheme,
the pagination style, or the specific failure you noticed.]

The three things that break this kind of integration in production, in order:
rate limits at the wrong time, cursor pagination that quietly truncates
results, and webhook retries that process the same event twice.

I'd build it with bounded backoff and jitter, uniform cursor/page handling,
idempotency keys on anything that writes, and a dry-run mode that points at a
shadow target before we touch production.

[Price] fixed. First deliverable: the integration running against your sandbox
with the retry and pagination behaviour tested, in [N] days.
```

## Template D — automation of a manual process

```
Hi [Name],

Right now [describe their current manual step] happens [frequency] and takes
[their stated hours, or your estimate].

I'd automate it so it runs on a schedule and tells you when it can't finish,
instead of failing quietly at 3am. That's usually the part people actually
care about — not the automation, the confidence that it ran.

Specifics I'd need confirmed: [data source] · [where the output goes] ·
[what "done" looks like] · [who gets notified on failure]

[Price] fixed. I'd rather agree the definition of "done" before starting than
after.

[Relevant proof link.]
```

## Template E — when you are underqualified (still worth sending)

Honesty wins jobs you are borderline for. Send this when you know you cannot
do the whole scope but can do a real slice of it.

```
Hi [Name],

Full disclosure first: [the specific part] is outside what I'd deliver
confidently, and I'd rather say that than discover it in week two.

What I can do well: [2-3 concrete things, with proof links].

If the [part you can do] is separable from the rest, I'm interested —
[price] for that scope, and I'll tell you what I'd hand off to someone else
for the remainder, so you're not blocked on me.
```

## Per-proposal checklist

Before sending:

- [ ] First sentence names something only in *their* post
- [ ] Zero sentences copied verbatim from a template
- [ ] At least one claim I can prove with a link or a pasted command
- [ ] A price and a timeline, both concrete
- [ ] Diagnostic framing ("let me reproduce it first, free") present where it
      applies — it de-risks them and filters out the clients who want free work
- [ ] Read as if I am paying them my rate: no gushing, no "I would love to"

## Sending discipline

Upwork bills roughly $0.90-3.60 per proposal in Connects. At 5 targeted
proposals a day you need about $15-18/day of Connects. Two rules:

1. **Never apply to a job older than 24h with more than 10 proposals.** You
   will not be the first bid and you cannot win on price against a
   fifteen-proposal queue.
2. **Track what gets replies.** `~/.config/freelance/log.csv`: date, job title,
   price, template used, reply yes/no. Twenty proposals is a sample, not a
   strategy. Without this you are guessing which template works.