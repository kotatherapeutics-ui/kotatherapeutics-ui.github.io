# Project Context

## Repository
https://github.com/kotatherapeutics-ui/kotatherapeutics-ui.github.io

## Deployment
Vercel, from the default branch. Routing is defined in vercel.json.
Live URL: TBD

## Pages
- landing.html — landing page, served at /
- index.html — peptide mixing and compatibility tool. Filename is fixed. Do not modify.
- ghk-cu-test.html — GHK-Cu home test guide. Filename is fixed. Do not modify.

## Product
Free peptide tools and resources, published online.

## Audience
Peptide researchers at any experience level, from first compound to years of logs.
The site must be usable by a beginner without talking down to an expert.

## Goal
Two goals, in this order:
1. Give away genuinely useful peptide tools and resources for free.
2. Funnel users into The BioChem Society Discord.
The tools come first. The Discord invite is secondary and should not interrupt the resource experience.

## Brand
The BioChem Society. Publishing identity is DØSΞ.
design.md is authoritative for color, type, spacing, motifs, and copy voice. Read it before any visual or copy work.

## Visual Direction
Black-field luxury per design.md: near-black ground, cream serif display, one azure gradient accent per view, letterspaced caps.
Modern halo and liquid-glass interaction language, interpreted through the BCS design rules rather than generic SaaS patterns.
Dark only. Never a light theme, never pure white.
Fonts are Google Fonts stand-ins (Playfair Display, Montserrat, IBM Plex Mono) pending real brand faces.
The azure gradient is reserved for the hero bcs-monogram-accent.png. Other interface accents use cream or flat azure.

## Page Structure
Hero → Tools → Guides → Discord → Footer.
Tools use structured, functional cards with a clear action.
Guides use quieter editorial rows or cards with more emphasis on title and description.
Both sections must support at least 6–8 entries without restructuring the page.

## Copy Direction
Per design.md section 8. Peer register, signal over hype, plain spoken English, no advice, no em dashes.
Landing-page caveats stay short. Detailed caveats remain inside the individual tool or guide.

## Functionality
Clean and dynamic. Fully responsive for mobile and desktop.
Tools and guides are distinct content types and must stay visually distinct.
Motion per design.md: fades and single-step color shifts only. No bounces, springs, or scale-in.
Liquid-glass behavior should come from edge response, restrained halos, specular highlights, and interaction, not decorative blur everywhere.
Legacy hash links on / must forward to /index.html while preserving the hash.

## Discord
Invite: https://discord.gg/sR7ty2Z6h9
Place one restrained Discord section after tools and guides with one clear CTA. No repeated banners or persistent prompts.

## Avoid
Everything in design.md section 10, plus: no vendor references, no marketplace framing, no generic SaaS visual language, no common template-style cards or interactions.

## Current Decisions
- Tools and guides will expand beyond the two current resources.
- Design for at least 6–8 tools and 6–8 guides without changing page structure.
- Hero monogram is the single gradient-accent element.
- Free resources are primary. Discord is secondary.
- Mixing-tool landing copy gets one short context line; detailed caveats remain inside the tool.
- When visual judgment is required, choose the option that best fits BCS branding and the modern halo/liquid-glass direction rather than a common web pattern.
