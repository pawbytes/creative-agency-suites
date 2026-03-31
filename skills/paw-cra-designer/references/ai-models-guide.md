---
name: ai-models-guide
description: AI model selection guide for each design capability with best practices for 2026
---

# AI Models Guide for Designer

This reference provides model recommendations for each design capability, optimized for quality, speed, and use case requirements in 2026.

## Model Ecosystem Overview

### Available on fal.ai

| Model | Best For | Speed | Quality | Text Rendering |
|-------|----------|-------|---------|----------------|
| **Nano Banana Pro** | Marketing, product shots, typography-heavy designs | Fast | Excellent | ⭐⭐⭐⭐⭐ |
| **FLUX.2 [pro]** | Premium marketing, high-detail imagery | Medium | Best-in-class | ⭐⭐⭐⭐ |
| **FLUX.2 [flex]** | Balanced quality/speed, typography | Fast | Excellent | ⭐⭐⭐⭐⭐ |
| **FLUX.1 [dev]** | High-quality with LoRA support | Medium | Excellent | ⭐⭐⭐ |
| **FLUX.1 [schnell]** | Rapid prototyping, bulk generation | Fastest | Good | ⭐⭐⭐ |
| **FLUX Kontext [pro]** | Image editing, style transfer, in-painting | Medium | Excellent | ⭐⭐⭐⭐ |
| **Recraft V4 Pro** | Brand assets, logos, vector-style graphics | Medium | Excellent | ⭐⭐⭐⭐ |
| **Seedream V4.5** | Stylized, artistic imagery | Medium | Excellent | ⭐⭐⭐ |

### Model Selection by Capability

---

## Social Post Design

### Recommended Models

| Priority | Model | Why |
|----------|-------|-----|
| **1st Choice** | Nano Banana Pro | Best text rendering, excellent for marketing copy on images |
| **2nd Choice** | FLUX.2 [flex] | Enhanced typography, good balance of speed/quality |
| **Fast/Prototype** | FLUX.1 [schnell] | Rapid iteration, 4-step generation |

### When to Use Each

**Nano Banana Pro:**
- Posts with text overlays, headlines, CTAs
- Product photography with brand messaging
- Quote graphics, announcement posts
- Any design requiring readable text in the image

**FLUX.2 [pro]:**
- Premium brand content requiring maximum quality
- Detailed product shots, lifestyle imagery
- When text is minimal or in separate layer

**FLUX.1 [schnell]:**
- Rapid A/B testing multiple concepts
- Background generation for layered designs
- Prototyping before premium generation

### Prompt Strategy

```
[Brand context] + [Subject] + [Platform specs] + [Brand colors] + [Text requirements]
```

**Example:**
> "Marketing post for tech startup. Young professional using laptop in modern cafe. Instagram 4:5 ratio. Brand colors: deep blue #1a365d, coral accent #f56565. Text overlay: 'Work Anywhere' in clean sans-serif. Lifestyle photography style, warm lighting, authentic mood."

---

## Carousel Design

### Recommended Models

| Priority | Model | Why |
|----------|-------|-----|
| **1st Choice** | FLUX.2 [flex] | Consistent style across slides, excellent typography |
| **2nd Choice** | Nano Banana Pro | Strong text rendering for educational content |
| **Budget** | FLUX.1 [dev] + LoRA | Style consistency via trained LoRA |

### Carousel-Specific Strategy

**Consistency is critical.** Use these approaches:

1. **Single Prompt with Variations:**
   - Keep core prompt identical
   - Only change subject/slide-specific content
   - Same style modifiers, seed if possible

2. **LoRA Training (FLUX.1 [dev]):**
   - Train LoRA on brand style
   - Apply to all slides for guaranteed consistency

3. **Background + HTML Overlay:**
   - Generate consistent backgrounds with AI
   - Apply text/content via HTML template
   - Combine using screenshot/render pipeline

### Prompt Template for Carousels

```
Slide {N} of {total}: [Specific content for this slide]
[Core style prompt identical across all slides]
[Brand colors], [Typography style], [Layout style]
```

**Example Series:**
> Slide 1: "5 Productivity Tips" headline with bold typography
> Slide 2-6: Individual tips with consistent layout
> Slide 7: CTA with brand colors and contact info
>
> Core style: "Modern minimalist design, clean white background, forest green #2C5F2D primary, amber #D4A574 accent, geometric shapes, sans-serif typography, Instagram carousel style, 1080x1350px"

---

## Flyer Design

### Recommended Models

| Priority | Model | Why |
|----------|-------|-----|
| **1st Choice** | FLUX.2 [pro] | Maximum detail, photorealistic, print quality |
| **2nd Choice** | Nano Banana Pro | Good text rendering for event info |
| **Digital Only** | FLUX.1 [schnell] | Fast digital flyers |

### Print Considerations

For print flyers (300 DPI):
- Generate at higher resolution (2K+)
- Use FLUX.2 [pro] for maximum detail
- Test color accuracy with CMYK conversion
- Account for bleed in generation

### Prompt Strategy

```
[Flyer type] flyer for [purpose]
[Main visual description]
[Text hierarchy: headline, key info, details]
[Style/aesthetic]
[Size context: print A4 or digital]
```

**Example:**
> "Event flyer for tech conference 'AI Summit 2026'. Main visual: futuristic cityscape with AI elements. Headline: 'AI Summit 2026' prominent. Key info: 'March 15-17, Tech Hub Convention Center'. Details: '50+ speakers, workshops, networking'. Modern tech aesthetic, blue and purple gradient, clean typography, print-ready A4 size, high detail, professional quality."

---

## Brand Asset Generation

### Recommended Models

| Asset Type | Best Model | Why |
|------------|------------|-----|
| **Logos** | Recraft V4 Pro / Ideogram V3 | Vector output, text accuracy |
| **Icons** | Recraft V4 Pro SVG | Native SVG, scalable |
| **Wordmarks** | Ideogram V3 | Best text rendering |
| **Illustrations** | FLUX.2 [pro] | High detail, artistic quality |
| **Patterns** | FLUX.1 [dev] + LoRA | Style consistency |

### Specialized Models on Other Platforms

| Platform | Model | Best For |
|----------|-------|----------|
| **Ideogram** | Ideogram V3 | Logos, wordmarks, text-heavy graphics |
| **Recraft** | Recraft V4 Pro SVG | Vector logos, icons, scalable brand assets |
| **Midjourney** | V6.1 | Artistic brand illustrations |

### Logo Generation Prompt Structure

```
[Brand name] logo, [logo type: wordmark/lettermark/pictorial/abstract]
[Industry/context], [style keywords]
[Color specification with HEX], [aesthetic direction]
[Technical: vector style, clean lines, scalable, simple]
```

**Example:**
> "GreenTech Solutions logo, pictorial mark with wordmark. Sustainable technology company. Minimalist leaf integrated with circuit pattern. Forest green #2C5F2D and teal #0D9488. Modern, clean, tech-meets-nature aesthetic. Vector style, simple shapes, scalable, works at small sizes."

---

## Asset Resizing & Adaptation

### Recommended Models

| Task | Model | Why |
|------|-------|-----|
| **Extend background** | FLUX Kontext [pro] | Seamless outpainting |
| **Fill added space** | FLUX Kontext [pro] | Context-aware generation |
| **Style transfer** | FLUX Kontext [pro] | Maintain aesthetic across variants |
| **Upscaling** | SeedVR Upscale | High-quality resolution increase |

### Workflow

1. **Identify focal content** that must be preserved
2. **Generate extension** using Kontext with reference image
3. **Apply brand consistency** through style prompts
4. **Export at all required sizes**

---

## Image Editing & Enhancement

### Recommended Models

| Task | Model | Why |
|------|-------|-----|
| **Background removal** | Bria RMBG 2.0 | Professional quality, licensed data |
| **Background replacement** | FLUX Kontext [pro] | Context-aware filling |
| **Object removal** | Nano Banana Pro Edit | Precise editing |
| **Color adjustment** | FLUX Kontext [pro] | Style transfer capability |
| **Upscaling** | Topaz Upscale / SeedVR | High-quality enhancement |

---

## Quality vs Speed Trade-offs

| Scenario | Model | Generation Time | Cost |
|----------|-------|-----------------|------|
| **Prototype/Test** | FLUX.1 [schnell] | ~2 seconds | Low |
| **Production Ready** | FLUX.2 [flex] | ~5 seconds | Medium |
| **Premium Quality** | FLUX.2 [pro] | ~10 seconds | Higher |
| **Print Quality** | FLUX.2 [pro] @ 2K | ~15 seconds | Higher |
| **With Text** | Nano Banana Pro | ~5 seconds | Medium |

---

## Pricing Reference (fal.ai, 2026)

| Model | Approximate Cost per Image |
|-------|---------------------------|
| FLUX.1 [schnell] | $0.003 - $0.01 |
| FLUX.1 [dev] | $0.02 - $0.04 |
| FLUX.2 [pro] | $0.04 - $0.08 |
| FLUX.2 [flex] | $0.02 - $0.05 |
| Nano Banana Pro | $0.02 - $0.05 |
| FLUX Kontext [pro] | $0.05 - $0.10 |

*Note: Pricing varies by resolution and provider. Check fal.ai for current rates.*

---

## API Usage Tips

### fal.ai Client Setup

```javascript
import { fal } from "@fal-ai/client";

// Configure once
fal.config({
  credentials: process.env.FAL_KEY
});

// Generate image
const result = await fal.subscribe("fal-ai/flux-pro/v1.1", {
  input: {
    prompt: "Your prompt here",
    image_size: "landscape_16_9",
    num_inference_steps: 28,
  }
});
```

### Best Practices

1. **Batch similar requests** - Use same model/session for consistency
2. **Cache frequently used styles** - Store prompts that work
3. **Use appropriate steps** - Lower steps for schnell, higher for pro
4. **Specify exact dimensions** - Use custom width/height for platform specs
5. **Enable safety filters** - For brand-safe content

---

## Hybrid Workflow: AI + HTML Templates

For maximum control and brand consistency:

1. **Generate background/artistic elements** with AI (FLUX, Nano Banana)
2. **Create HTML/CSS template** for text and layout
3. **Render combined image** using Puppeteer/Playwright
4. **Export at exact dimensions**

See `./template-system.md` for template architecture.