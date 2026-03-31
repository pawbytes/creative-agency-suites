# Competitor Research

Analyze competitor content, positioning, and market gaps using proven frameworks.

**Key Methodologies:** SWOT Analysis, Porter's Five Forces, Strategic Group Analysis, Perceptual Mapping, Competitive Profile Matrix. Load `./methodologies.md` for detailed framework templates.

## Input

Gather from conversation or brand context:
- Brand name and industry
- Known competitors (if any)
- Research scope (broad scan vs. specific competitors)
- Focus areas (content types, platforms, messaging)

## Research Process

### Choose Your Framework

Before diving in, select the right tool for the situation:

| Situation | Framework |
|-----------|-----------|
| Fast competitive overview | SWOT Analysis |
| Entering a new market | Porter's Five Forces |
| Too many competitors | Strategic Group Analysis |
| Repositioning brand | Perceptual Mapping |
| Quantitative comparison | Competitive Profile Matrix |

### Step 1: Identify Competitors

If not provided, discover competitors:

- Search "{industry} brands similar to {brand}"
- Use Exa `web_search_exa` for discovery
- Check industry directories and rankings

### Step 2: Analyze Competitors

**For Public Content (Exa MCP Tools):**
- Website content via `crawling_exa`
- Published articles and blog posts
- Press releases and news coverage

**For Social Media Profiles (Agent-Browser):**

Use agent-browser with authenticated Chrome profile to access competitor social profiles:

```bash
# LinkedIn company page
agent-browser --profile ~/.strategist-profile open https://linkedin.com/company/{competitor}
agent-browser wait --load networkidle
agent-browser screenshot --full ./research/{competitor}-linkedin.png

# Instagram profile (requires login)
agent-browser --state "{project-root}/.pawbytes/creative-suites/.auth/session.json" open https://instagram.com/{competitor}
agent-browser snapshot -i  # Get interactive elements
agent-browser screenshot --full ./research/{competitor}-instagram.png

# Extract post text for analysis
agent-browser get text article > ./research/{competitor}-posts.txt
```

See `./browser-tools.md` for authentication setup.

**Analysis Checklist:**
- Website and content strategy
- Social presence and engagement patterns
- Messaging themes and brand voice
- Content gaps and opportunities
- Recent campaigns and promotions

### Step 3: Synthesize Findings

- Positioning map (how competitors differentiate)
- Content gaps (what's missing in the market)
- Opportunity areas (where to compete)

## Output

Create `{brand-name}/research/competitor-analysis.md`:

```markdown
# Competitor Analysis: {Brand}
## Executive Summary
## Competitor Profiles
### {Competitor 1}
- Positioning
- Content strategy
- Strengths
- Weaknesses

### {Competitor 2}
...

## Market Gaps
- Gap 1: {description}
- Gap 2: {description}

## Recommendations
- Opportunity 1: {specific action}
- Opportunity 2: {specific action}

## Sources
- [Source 1](url)
- [Source 2](url)
```

## Completion Criteria

Research is complete when:
- [ ] At least 3 competitors analyzed with full profiles
- [ ] Market gaps identified with specific opportunity descriptions
- [ ] All sources cited with URLs
- [ ] Actionable recommendations tied to brand strengths

## Quality Standard

- Cite all sources with URLs
- Focus on actionable insights, not just observations
- Highlight gaps that align with brand strengths
- Recommend specific content opportunities