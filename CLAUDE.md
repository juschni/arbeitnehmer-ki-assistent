# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is **not a software project** — there is no build system, package manager, linter, or test suite. It is the content/documentation repository for **"Juschni"**, a German-language company built around an AI assistant for employees ("Arbeitnehmer-KI-Assistent" / "CareerAI"). The repo holds:

- A public marketing landing page (`index.html`)
- Internal company/product documentation (`unternehmenssystem/`)
- GPT prompt configurations (`unternehmenssystem/04_gpts/`, `PROMPTS/`)
- Planning/status artifacts (`Projekt-Cockpit_v0.1.html`, `Projektplan_Juschni_v1.0.pdf`)

Because there's no toolchain, there are no build/lint/test commands to run. When asked to "verify" a change here, that means opening the HTML file in a browser and/or proofreading the Markdown — not running a test suite.

## Repository structure

```
index.html                          Public marketing landing page (German), links out to the
                                     actual chatbot app hosted on Hugging Face Spaces.
Projekt-Cockpit_v0.1.html            Standalone HTML status dashboard (mirrors DASHBOARD.md).
Projektplan_Juschni_v1.0.pdf         Project plan document.
PROMPTS/                             Standalone GPT prompt snippets for specific use cases
                                     (e.g. analyzing a boss's email, analyzing a Zeugnis/reference letter).
unternehmenssystem/                  The "company operating system" — single source of truth for
                                     strategy, methodology, GPT configs, and decisions.
```

### `unternehmenssystem/` (the company OS)

Numbered folders, each with one clear purpose (see its own `README.md` for the authoritative table):

| Folder | Purpose |
|---|---|
| `00_dashboard/` | `DASHBOARD.md` — current sprint status, active artifacts and their state, next output |
| `01_charta/` | `A-001_unternehmens-charta_*` — the immutable core: mission, guiding principles, legal scope |
| `02_marke/` | Brand DNA, language, positioning (referenced in the structure table but not yet created) |
| `03_methodik/` | `M-001_methodik_*` — the analysis method every product/GPT must follow |
| `04_gpts/` | Versioned GPT role/prompt configurations (e.g. `GPT-001_arbeitnehmer-kompass_*`) |
| `05_testing/` | Test protocols and feedback questions for validating a GPT with real users |
| `06_roadmap/` | Next milestones (referenced but not yet created) |
| `07_entscheidungen/` | `DECISIONS.md` — append-only decision log (`D-001`, `D-002`, ...) |
| `99_inbox/` | `IDEENPARKPLATZ.md` — parking lot for unsorted ideas (naming candidates, product ideas) |

Artifacts are versioned in the filename (`_v0.1`, `_v1.0`, ...) rather than relying on chat/edit history — see D-003. When updating an artifact to a new version, follow the existing pattern: bump the version suffix and update any status tables (`DASHBOARD.md`, `Projekt-Cockpit_v0.1.html`) that reference it, rather than silently overwriting history.

## Working conventions (from the Charta and decision log)

These rules apply to any content you write or edit in this repo, especially GPT prompts and anything touching German employment law:

- **KISS**: kurz, klar, vollständig genug (short, clear, complete enough) — D-006.
- **Aktualität vor Output**: for German labor law, authorities, and deadlines, verify currency before producing output; never state unverified §, invented deadlines, or outdated legal status — flag uncertainty explicitly instead of guessing (Charta, D-007).
- **Fakten, Bewertungen und Hypothesen werden getrennt**: keep facts, assessments, and hypotheses visibly separate in any analysis output.
- **Orientierung statt Rechtsberatung**: all GPT outputs are orientation/preparation, not binding legal advice — this boundary must stay explicit in any prompt/config work (see `GPT-001`'s "Grenze" section).
- **Sprache**: external language is precise, calm, resilient; internal language (decision logs, inbox) may be direct and unfiltered. GPT-facing language must be clear, direct, calm, understandable, free of unnecessary jargon, no fear-mongering, no false certainty.
- **Prefer robust formats over fragile ones for anything meant to be quickly viewed on mobile** — D-009 explicitly favors PDF/PNG over HTML prototypes for that purpose; the HTML dashboards here are internal/desktop artifacts, not the mobile-facing deliverable.
- New GPT configs should follow the existing response structure used in `GPT-001` (Kurzfassung → Gesicherte Informationen → Offene Punkte → Einordnung → Optionen → Folgen → Nächste Schritte → Formulierungshilfe) unless a change to that structure is itself the task.
- Log any non-trivial decision as a new entry in `unternehmenssystem/07_entscheidungen/DECISIONS.md` (append, don't renumber existing `D-xxx` entries).

## Editing the landing page (`index.html`)

Single-file HTML with inline `<style>`, no build step — edit and open directly in a browser to check. It's in German; keep new copy consistent with the existing tone (direct, benefit-led, no corporate jargon) and the Charta's language principles above. The primary CTA links out to the external chatbot app on Hugging Face Spaces — that URL is the actual product; this page is just marketing.
