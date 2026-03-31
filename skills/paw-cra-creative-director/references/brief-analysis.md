# Brief Analysis

Transform a creative brief or loose requirements into structured, actionable specifications. **Always route through Strategist for validation against agency standards before proceeding to campaign planning.**

## Workflow

1. **Aria receives brief** — User provides verbal description, document, or reference materials
2. **Route to Strategist** — Invoke `paw-cra-strategist` to validate and analyze against agency standards
3. **Strategist validates** — Checks brief completeness, brand alignment, strategic fit, and flags gaps
4. **Aria reviews findings** — Incorporates Strategist's analysis into campaign planning

## Why Strategist Validates

The Strategist ensures every brief meets creative agency standards:
- **Completeness** — All required elements present (what, why, who, when, context)
- **Brand alignment** — Consistent with brand voice, positioning, and guidelines
- **Strategic fit** — Realistic scope, clear objectives, measurable success criteria
- **Research grounding** — Identifies what additional research might be needed

This gate prevents vague or misaligned briefs from reaching production.

## Goal

Ensure every stakeholder (user, specialists, Aria) shares the same understanding of what's being created and why — and that it meets agency quality standards.

## Input Sources

- User's verbal description
- Provided brief document
- Email or message content
- Reference materials (links, files)

## Extraction Framework

**1. The What**
- What is being created? (format, quantity, scope)
- What channels/platforms? (social, web, print, video)
- What constraints? (dimensions, duration, file types)

**2. The Why**
- What's the goal? (awareness, conversion, engagement, launch)
- What success looks like (metrics, outcomes)

**3. The Who**
- Target audience
- Existing brand (from memory or new)

**4. The When**
- Deadlines
- Dependencies
- Review cycles

**5. The Context**
- Background or backstory
- Reference examples
- Things to avoid

## Output

Create a structured brief in memory: `{project-root}/.pawbytes/creative-suites/briefs/{brief-name}.md`

```markdown
# {Brief Name}

## Deliverables
- {format}: {quantity} × {dimensions/specs}
- {format}: ...

## Objective
{goal statement}

## Audience
{audience description}

## Brand
{brand name or profile reference}

## Timeline
- Brief received: {date}
- Draft due: {date}
- Final due: {date}

## Constraints
- Must: {requirements}
- Must not: {restrictions}

## References
- {links or file paths}

## Notes
{additional context}
```

## Validation

**Route to Strategist first.** Invoke `paw-cra-strategist` with the extracted brief and brand context. The Strategist will:

1. **Check completeness** — Flag missing elements (audience, objective, timeline, constraints)
2. **Verify brand alignment** — Ensure positioning and voice are consistent
3. **Assess strategic clarity** — Objectives are measurable, scope is realistic
4. **Identify research needs** — Competitor analysis, audience insights, trend data

**Strategist output:** Validated brief with recommendations or flagged issues.

Then Aria confirms with the user:
- "Here's what I understand you need..."
- Highlight any gaps or assumptions the Strategist found
- Get explicit approval before routing to specialists