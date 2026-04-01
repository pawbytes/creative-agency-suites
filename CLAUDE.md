# Aria Creative Suite

## Naming Convention

All skills in this module use the `paw-cra-*` prefix instead of the standard BMad `bmad-*` prefix.

- `paw` = PawBytes (organization)
- `cra` = Creative Agency (module)

This is intentional to namespace the creative agency module under the PawBytes organization. The convention applies to all skill directory names, SKILL.md `name` fields, and cross-skill references (e.g., `paw-cra-agent-designer`, `paw-cra-video-shortform`).

When creating new skills for this module, always use the `paw-cra-` prefix.

## Architecture

**Agent skills** (persistent personas with memory):
- `paw-cra-agent-creative-director` — Aria, the orchestrator and entry point
- `paw-cra-agent-designer` — Visual production specialist
- `paw-cra-agent-strategist` — Research and content strategy (service agent, on-demand)
- `paw-cra-agent-video-producer` — Video production specialist

**Workflow skills** (deterministic pipelines):
- `paw-cra-campaign-orchestration` — Multi-deliverable campaign execution
- `paw-cra-content-research` — Research bundles with production recommendations
- `paw-cra-design-social` — Social post and carousel production
- `paw-cra-design-brand` — Logo, icon, flyer, banner production
- `paw-cra-design-batch` — Bulk visual asset generation
- `paw-cra-video-shortform` — TikTok/Reels/Shorts vertical video
- `paw-cra-video-longform` — YouTube/web horizontal and episodic video
- `paw-cra-video-clips` — Clip extraction and repurposing
- `paw-cra-multi-platform-export` — Final-mile resize and encode
- `paw-cra-quality-control` — Campaign-level QC with severity-rated report

## Routing Rule

**Production-first routing** — when a user requests a visual or video deliverable, route directly to the production agent (Designer or Video Producer). The Strategist is a service agent invoked on demand, not a mandatory gate.
