# PawBytes Naming Convention

## Overview

PawBytes agents use a custom naming prefix `paw-cra-*` instead of the standard BMad `bmad-agent-*` pattern. This is intentional and documented here.

## Convention

| Prefix | Meaning |
|--------|---------|
| `paw` | PawBytes organization |
| `cra` | Creative Agency suite |
| `*` | Agent role (e.g., `creative-director`, `designer`, `strategist`) |

## Rationale

1. **Suite identity** — The `cra` suffix groups all Creative Agency agents together
2. **Discoverability** — Users can find all PawBytes agents by searching `paw-*`
3. **Avoids collision** — Distinguishes PawBytes agents from standard BMad agents

## Valid Patterns

- `paw-cra-creative-director` — Creative director orchestrator
- `paw-cra-designer` — Visual production specialist
- `paw-cra-strategist` — Research and strategy specialist
- `paw-cra-video-producer` — Video production specialist
- `paw-cra-account-manager` — Delivery and packaging specialist

## Other PawBytes Suites

| Suite Prefix | Purpose |
|--------------|---------|
| `paw-mkt-*` | Marketing agents |
| `paw-cra-*` | Creative Agency agents |

## Decision

The naming convention deviation is intentional and documented. No changes required.