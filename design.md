# BCS Design Guide (design.md)

The working reference for designing anything as **The BioChem Society**. `readme.md` covers project context and the file manifest; this file is the rulebook. Every value below is a live token in `styles.css`.

---

## 1. Brand in one paragraph

BCS is a Discord community for peptide research: real-people data, official study breakdowns, peptide news, and regulatory coverage. It positions itself as the most organised research community in the peptide space. The publishing identity is **DØSΞ**. The look is black-field luxury: near-black ground, cream serif monogram, a single azure gradient accent, letterspaced caps. Professional and science-driven, and community is the glue, so nothing in the design should look like a vendor talking down to a customer.

**Three rules that hold everywhere**
1. Dark is the only mode. Cream on ink, never ink on white.
2. One accented element per composition. The azure gradient is a spotlight, not a paint bucket.
3. No em dashes in any BCS copy. Ever.

---

## 2. Color

### Ink (the field)
| Token | Value | Use |
|---|---|---|
| `--ink-950` | `#050506` | Page ground, full bleed |
| `--ink-900` | `#0A0B0D` | Cards |
| `--ink-800` | `#101216` | Raised panels, dialogs, embeds |
| `--ink-700` | `#171A20` | Inputs, inset wells |
| `--ink-600` | `#232830` | Tooltips, scrollbars |
| `--ink-500` | `#39404C` | Highest lift, rarely needed |

### Bone (type and marks)
`--cream-50 #FDFBF5` display type · `--cream-100 #F7F1E5` the monogram cream, primary buttons · `--cream-200 #EAE1CF` body text · `--cream-400 #C9BEA6` · `--cream-600 #8F8672`. **Never `#FFFFFF`.**

### Azure (the one accent)
`--azure-200 #8AD5F5` · `300 #5BC0EE` · `400 #3A9FDB` · `500 #2578BE` · `600 #175A9A` · `700 #123F73`
`--grad-azure: linear-gradient(165deg,#7FD0F4 0%,#3A9FDB 45%,#175A9A 100%)` — the gradient of the monogram's S. Reserve it for the single accent: one button, one rail, one underline.

### Signal ratings (reserved)
`--signal-strong #4CAF78` 🟢 · `--signal-emerging #D9A13B` 🟡 · `--signal-preliminary #C4554D` 🔴. These three colors carry meaning: **evidence quality, nothing else.** Never use them as decoration, and never as generic success/warning/error branding outside of a Toast tone.

### Semantic aliases (prefer these)
`--surface-page/card/raised/inset` · `--text-display/body/muted/faint` · `--border-subtle` (9% cream) `--border-strong` (18%) `--border-accent` (azure 45%) · `--accent`, `--accent-strong`, `--accent-deep` · `--focus-ring`.

---

## 3. Type

| Role | Stack | Notes |
|---|---|---|
| Display | `--font-display` Playfair Display | High-contrast didone. Headlines, compound names, big numbers-as-statement. |
| UI / caps | `--font-sans` Montserrat | All chrome, labels, buttons, body copy. |
| Data | `--font-mono` IBM Plex Mono | Doses, N values, dates, IDs, percentages. |

**Substitution flag:** no brand font binaries were provided. These are Google Fonts stand-ins. If BCS owns real faces, drop the files in and swap `tokens/fonts.css`.

**Scale** `--text-xs 12 · sm 13 · base 15 · lg 18 · xl 22 · 2xl 28 · 3xl 36 · 4xl 48 · 5xl 64`
**Leading** `tight 1.15` (display) · `snug 1.35` · `body 1.6`
**Tracking** `--tracking-caps .22em` (the signature eyebrow) · `--tracking-wide .08em` (buttons, badges) · `normal 0`
**Weights** 300 / 400 / 500 / 600 / 700

### The three type moves
1. **Big serif display, tight leading.** `--font-display` at 36–64px, `--leading-tight`, weight 400–500. Never bold-and-cramped.
2. **Letterspaced caps eyebrow.** Montserrat 11px, weight 600, `--tracking-caps`, uppercase, `--text-muted` or `--accent-strong`. Optional ◉ eye substituted for an O (`S◉CIETY`).
3. **Mono for anything measurable.** If it has a unit, a count, or a date, it is mono.

Measure: cap body text at `--measure` (64ch).

---

## 4. Spacing, radii, layout

4px base: `--space-1 4` → `--space-16 64` (4, 8, 12, 16, 20, 24, 32, 40, 48, 64).
Radii are deliberately sharp: `--radius-sm 4` (buttons, inputs, badges) · `--radius-md 8` (toasts, wells) · `--radius-lg 14` (cards, dialogs) · `--radius-pill` (tags only). Nothing bubblier than 14px.

Layout: generous negative space. Marks float in large black fields. Rails sit at 232px (left) and 268px (right); a content column reads best at 560–720px. Fixed elements: channel header (56px), composer pinned to the bottom, toasts bottom-right at 24px inset.

---

## 5. Depth, motion, states

**Shadows** — deep, soft, plus a 1px inner top highlight:
- `--shadow-card` `inset 0 1px 0 rgba(255,255,255,.04), 0 8px 28px rgba(0,0,0,.55)`
- `--shadow-raised` `inset 0 1px 0 rgba(255,255,255,.05), 0 16px 48px rgba(0,0,0,.65)`
- `--glow-azure` `0 0 28px rgba(58,159,219,.28)` — the accent element only.

**Motion** `--dur-fast 120ms` (hover, toggles) · `--dur-base 200ms` (surfaces, dialogs) · `--ease-out cubic-bezier(.22,1,.36,1)`. Fades and 1-step color shifts. **No bounces, no springs, no scale-in.**

**Hover** brighten: cream goes to `--cream-50`, azure `filter: brightness(1.12)`, backgrounds lift one ink step, borders go from `--border-subtle` to `--border-strong` or `--border-accent`.
**Press** darken one step (`--cream-200`, `brightness(.92)`, `--surface-inset`). Never shrink.
**Focus** `--focus-ring` — 2px ink gap then 2px azure. Visible, always.
**Disabled** `opacity: .4`, `cursor: not-allowed`. No color change.

**Transparency and blur** — dialog backdrops only: `rgba(5,5,6,.72)` + `blur(4px)`. Cards stay opaque.

---

## 6. Brand motifs

- **The monogram** — cream serif BCS lockup. Accent variant has the azure-gradient S; ouroboros variant terminates the C in a snake head. `assets/bcs-monogram-accent.png`, `assets/bcs-monogram-ouroboros.png`.
- **The DØSΞ wordmark** — cream curly braces, `assets/dose-wordmark.png`. Use for announcements and publishing.
- **The Eye of Horus** — 𓂀 as a divider centerpiece, ◉ substituted for an O in caps lockups.
- **The ▬ divider** — `▬▬▬▬▬▬▬▬▬▬▬▬▬▬▬` at `--text-faint`, letter-spacing 2px. Inherited from the embed format and a genuine signature. Hairline-plus-eye is the quieter alternative.
- **Never redraw the marks.** Place the PNGs. No reconstructions, no traced SVGs.

**Backgrounds** are flat ink, optionally with a very subtle radial azure glow behind a hero mark. No photography, textures, or patterns exist in the brand. If imagery is ever added: cool, desaturated, near-black.

---

## 7. Iconography

No icon library was provided, and the brand genuinely uses unicode and emoji as functional glyphs. Prefer those:

- Category emoji, one per title or field name: ⚗️ 🔬 📊 📡 ⚠️ 📌 🔑 📅 🎉
- Signal ratings: 🟢 🟡 🔴
- Structure: ▬ dividers, ・ separators, U+2800 braille blanks for embed spacing
- Chrome glyphs in use: `#` channel, `✕` close, `⌕` search, `◈` gated, `⌗` read-only, `ⓘ` info, `✓` check

Emoji are **functional labels, never decoration.** One leads a title or a field name; never a row of them for flavor. For richer UI chrome, Lucide at 1.5px stroke via CDN is the sanctioned substitute, and it is a substitute, flagged as such.

---

## 8. Copy rules (the short version)

- **Peer register.** Members are experienced researchers. Density over hand-holding. Never define common terms.
- **Signal over hype.** Banned: groundbreaking, shocking, game-changing, exclamation stacking.
- **Plain spoken English**, even for regulatory material. If it would sound strange said aloud, rewrite it plainer.
- **No advice, no editorializing.** State facts, name gaps, stop.
- **Field names label, never instruct.** `📋 What's Verifiable`, `⚠️ What We Still Don't Know` — never `What You Should Do`.
- **Honest absence.** "Our search returned no trials," never "no trials exist."
- **Headlines** Title Case, 4–8 words, journalist-specific: "FDA Opposes Peptide Access," not "Peptide News Update."
- **Credit the members**, not the brand.
- **No em dashes.** Commas, periods, or the ▬ divider.

---

## 9. Component inventory

Import from the bundle namespace (`check_design_system` prints the exact name).

**forms/** `Button` (primary cream / accent gradient / ghost; sm-md-lg) · `IconButton` · `Input` (caps label, optional mono) · `Select` · `Checkbox` · `Radio` · `Switch`
**display/** `Card` (default / raised / accent) · `Badge` (neutral, azure, three signal tones) · `Tag` (pill, removable) · `Tooltip`
**navigation/** `Tabs` (caps, azure gradient underline)
**feedback/** `Dialog` (blurred ink backdrop, caps eyebrow, serif title) · `Toast` (tone glyph, no colored left border)
**brand/** `Eyebrow` · `SectionDivider` (bars / eye) · `SignalBadge` (glowing dot + caps rating) · `EmbedCard` — the Sapphire embed, BCS's core publishing unit and the one place a colored left rail is sanctioned (4px azure).

Each directory has a `.prompt.md` per component with usage, and one `@dsCard` HTML showing states.

---

## 10. Anti-patterns

Do not: use pure white or a light theme · apply the azure gradient to more than one element per view · use signal colors decoratively · add a colored left border to anything other than `EmbedCard` · draw the monogram, the eye, or the ouroboros by hand · use bluish-purple gradients · scale or bounce on press · round corners past 14px · write em dashes · stack decorative emoji · say "groundbreaking."
