# Brief Analysis

Transform a creative brief or loose requirements into structured, actionable specifications for the specialist team.

## Goal

Ensure every stakeholder (user, specialists, Aria) shares the same understanding of what's being created and why.

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

Before proceeding, confirm with the user:
- "Here's what I understand you need..."
- Highlight any gaps or assumptions
- Get explicit approval before routing to specialists