# Rayden UI Design Skill

A Claude Code skill for building with [Rayden UI](https://www.raynaui.com/) — in code and in Figma. Two skills in one package:

- **`/rayden-code`** — Generate production-quality React code using Rayden UI components with correct props, design tokens, and premium layout patterns
- **`/rayden-use`** — Build and maintain Rayden UI components and screens directly in Figma via the Figma MCP

Both skills enforce the Rayna UI design system: documented components only, token-only colors, spacing on the 4px grid, and visual craft rules that prevent generic AI output.

## Install

### Claude Code Plugin Marketplace

```bash
claude plugin add rayden-ui-design-skill
```

### skills.sh

```bash
claude skill add leslieisah/rayden-ui-design-skill
```

### Manual

```bash
git clone https://github.com/leslieisah/rayden-ui-design-skill.git
claude --plugin-dir ./rayden-ui-design-skill
```

## Skills

### `/rayden-code` — Vibe Code with Rayden UI

Generate React + Tailwind CSS code using all 34 Rayden UI components with correct props and design tokens. Prevents hallucinated components and props.

```
/rayden-code a dashboard with KPI cards and a recent orders table
/rayden-code auth page with login form
/rayden-code settings page with profile and notification preferences
```

**Prerequisites:**
- `@raydenui/ui` installed in your project (`npm install @raydenui/ui`)

**What it enforces:**
- Only documented components and props (34 components, full API reference)
- Tailwind token classes (`bg-primary-500` not `#EB5017`)
- Premium layout patterns (generous whitespace, clear hierarchy, color restraint)
- Anti-pattern detection (no gradient text, no colored containers, no 3-col icon grids)
- Responsive design with proper breakpoints
- Accessibility (aria-labels on icon-only buttons, keyboard navigation)

### `/rayden-use` — Design in Figma

Build Rayden UI components and screens directly in Figma using the Figma MCP. Every output uses auto layout, resolved token values, and passes a visual validation checklist.

```
/rayden-use Button https://figma.com/file/...
/rayden-use dashboard-screen balanced https://figma.com/file/...
/rayden-compose landing expressive https://figma.com/file/...
```

**Prerequisites:**
- [Figma MCP](https://github.com/anthropics/claude-code) connected in Claude Code
- Figma Dev or Full seat (write access)
- Rayden AI MCP server (`npx @raydenui/ai`) or `@raydenui/ui` installed

**Style modes:**

| Mode | Description |
|------|-------------|
| `conservative` | Tight whitespace, flat cards, maximum restraint |
| `balanced` | Default — generous whitespace, clean hierarchy, premium neutral |
| `expressive` | Bolder scale, stronger contrast, more visual weight |

## What's included

```
skills/
├── rayden-code/
│   ├── SKILL.md              # Vibe coding skill
│   └── RAYDEN_RULES.md       # Full component API, design patterns, tokens, anti-patterns
└── rayden-use/
    ├── SKILL.md              # Figma design skill
    ├── rayden-compose/
    │   └── SKILL.md          # Subagent for full-page Figma screen builds
    └── supporting/
        ├── tokens.md         # Resolved token values (colors, spacing, radius, shadows)
        ├── craft-rules.md    # Typography, radius, spacing, color rules + QA checklist
        ├── anti-patterns.md  # Banned AI-generated patterns with alternatives
        └── screen-patterns.md # Pre-built layout shells for 5 screen types
```

## Design System

Built on the [Rayna UI](https://www.raynaui.com/) design system (34 components). The skills enforce:

- Only documented components and props — no hallucination
- Token-only colors and spacing (4px grid)
- Concentric border radius
- One primary action per section
- No gradient text, colored containers, or centered hero stacks
- Consistent elevation strategy (shadow OR border, not both heavy)
- Content width always constrained

## License

MIT
