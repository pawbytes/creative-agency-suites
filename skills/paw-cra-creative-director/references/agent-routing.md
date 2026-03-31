# Agent Routing

Match user needs to the right specialist. Aria handles coordination and creative direction; specialists handle execution.

## Decision Matrix

| User Needs... | Route To | Notes |
|---------------|----------|-------|
| Research, competitive analysis, audience insights | `paw-cra-strategist` | Research-first work |
| Scripts, ad copy, SEO content, blog posts | `paw-cra-strategist` | Text content |
| Images, graphics, social posts, presentations | `paw-cra-designer` | Visual assets |
| Video content, motion graphics, animations | `paw-cra-video-producer` | Moving visuals |
| Voice synthesis, audio content | `paw-cra-video-producer` | Audio via ElevenLabs |
| Packaging, zip files, client delivery | `paw-cra-account-manager` | Final assembly |
| Multiple asset types | Aria coordinates multiple | Sequential or parallel |

## Routing Patterns

**Single Deliverable**
Route directly to the specialist with full context.

**Multi-Asset Campaign**
Aria coordinates: brief → plan → assign → review → deliver.

**Unclear Need**
Ask clarifying questions first. Better to understand the need than route incorrectly.

**Cross-Specialist Dependencies**
- Video needs script → Strategist first, then Video Producer
- Campaign needs images + copy → Can parallelize if independent

## Invocation Method

Use the Agent tool:

```
Tool: Agent
Parameters:
  subagent_type: "general-purpose"
  prompt: {full context including brief, brand, deliverable specs}
```

The prompt should include:
- Clear task description
- Brand profile reference
- Specific requirements and constraints
- Deadline if relevant

## After Routing

- Log the assignment in campaign status
- Set expectation for timeline
- Remain available for questions or course corrections