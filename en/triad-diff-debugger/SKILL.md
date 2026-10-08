---
name: triad-diff-debugger
description: Root-cause debugging and incident triage skill using the three-question breakdown method (What changed, What is still working, What is broken). Use when debugging broken code, troubleshooting outages, analyzing regressions, or triaging system errors.
---
# Triad Diff Debugger (Three-Pillar Debugging)

Systematic root-cause analysis and debugging framework based on the strict three-pillar diagnostic discipline: "1. What changed? 2. What is still working? 3. What is broken?". Prevents wild guessing and isolates regressions rapidly.

## When to Use

- When an application, service, or feature was previously working but suddenly broke or degraded
- When analyzing Git diffs, deployment failures, or unexpected regression test results
- When debugging cryptic error logs, stack traces, or silent failures
- When conducting post-mortems or creating reproducible bug triage reports

## The Three Diagnostic Pillars

### Pillar 1: What Changed?
- Audit recent code commits, PR merges, or Git diffs.
- Identify configuration, environment variable, or secret changes.
- Check dependency updates, runtime/compiler version bumps, or OS package changes.
- Check infrastructure updates (DNS, TLS certs, firewall rules, cloud provider events).
- Inspect changes in incoming payload schemas, external API responses, or traffic volume spikes.

### Pillar 2: What is Still Working?
- Identify unaffected modules, endpoints, and upstream/downstream components that remain healthy.
- Validate health checks and database connectivity that pass without error.
- Pinpoint the exact boundary where valid inputs still produce valid intermediate outputs.
- This boundary isolates where the problem is NOT, narrowing the search space dramatically.

### Pillar 3: What is Broken?
- Extract the exact error message, stack trace, HTTP status code, or panic log.
- Pinpoint the exact line of code, query, or network packet where failure triggers.
- Formulate the minimal reproduction step (curl command, unit test, or payload).

## Synthesis & Resolution Protocol

1. Overlay "What Changed" onto "What is Broken" to establish correlation and causality.
2. Formulate the single most probable root-cause hypothesis.
3. Propose the minimal surgical fix (do not refactor unrelated code).
4. Provide a regression test to verify the fix and prevent future recurrence.

## Gotchas

- Never guess solutions before completing all three diagnostic pillars.
- Do not assume an error message is the root cause; always verify if it is merely a symptom of an upstream state change.
