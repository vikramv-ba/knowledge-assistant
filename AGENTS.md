# Squad Pulse

Squad Pulse is a Cursor agent and plugin for shaping, assessing, sizing, and forecasting Cart and Checkout delivery initiatives. It uses the knowledge base in `knowledge/` for domains, systems, stakeholders, workflows, business rules, and sizing.

## Quick start

1. Open this repository in Cursor.
2. Enable the **Squad Pulse** plugin from **Customize → Plugins**, or use the built-in agent and rules from this repo.
3. Select the **Squad Pulse** agent, or chat with Agent and ask about a feature.
4. Use `/assess-feature` to run a full 12-step delivery assessment.

## Standard opening

When starting a new assessment, Squad Pulse will ask for:

- Feature idea
- Target customer or user
- Desired business outcome
- Known systems
- Target date
- Historical squad delivery data (optional)

## Knowledge base

Approved knowledge lives under `knowledge/`. See `references/knowledge-index.md` for the full index.

| Topic | Path |
|---|---|
| Domains | `knowledge/domains/checkout-domains.md` |
| Systems | `knowledge/systems/checkout-systems.md` |
| Integrations | `knowledge/integrations/system-touchpoints.md` |
| Workflows | `knowledge/workflows/checkout-flows.md` |
| Business rules | `knowledge/business-rules/checkout-business-rules.md` |
| Stakeholders | `knowledge/stakeholders/checkout-stakeholders.md` |
| Glossary | `knowledge/glossary/checkout glossary.md` |
| Templates | `knowledge/templates/checkout-req-templates.md` |
| ADRs | `knowledge/decisions/checkout-adr.md` |
| Sizing | `knowledge/sizing/cart-sizing-guide.md` |

Only content merged to `main` is approved knowledge.

## Analysis workflow

Squad Pulse follows a 12-step sequence:

1. Feature initiation
2. Problem and outcome definition
3. Requirements
4. Scope boundaries
5. System touchpoints
6. BPMN workflow
7. Stakeholder map
8. Dependency assessment
9. T-shirt sizing
10. Monte Carlo forecast
11. Confidence rating
12. Risks, assumptions, open questions, next steps

## Plugin structure

```text
.
├── SKILL.md                    # Master agent skill and prompt
├── AGENTS.md                   # This file
├── agents/
│   ├── squad-pulse.md          # Cursor agent definition
│   └── openai.yaml             # Agent metadata
├── commands/
│   └── assess-feature.md       # /assess-feature slash command
├── rules/
│   └── squad-pulse.mdc         # Context rule for feature assessment
├── references/                 # Output templates and conventions
├── knowledge/                  # Approved domain knowledge
└── .cursor-plugin/
    └── plugin.json             # Plugin manifest
```

## Commands

| Command | Purpose |
|---|---|
| `/assess-feature` | Run a full delivery assessment for a feature idea |

## Updating knowledge

Follow `README.md` governance and `CONTRIBUTE.md` for knowledge and skill changes. Sizing rules in `knowledge/sizing/cart-sizing-guide.md` are currently a draft and will be updated as historical delivery data is validated.

## References

- `references/output-templates.md` — assessment output schemas
- `references/bpmn-notation.md` — BPMN 2.0 conventions
- `references/dependency-taxonomy.md` — dependency categories
- `references/sizing-guide.md` — sizing drivers and bands
- `references/monte-carlo.md` — forecasting method
- `references/estimation-integrity.md` — estimate vs commitment language
