# Contributing to Squad Sense — Cart

Thank you for contributing to the Squad Sense — Cart skill.

This repository contains workflow instructions, reusable templates, Cart domain references, estimation guidance, and agent configuration used to assess, size, and forecast digital delivery initiatives.

## Repository Structure

```text
.
├── SKILL.md
├── AGENTS.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── output-templates.md
│   ├── bpmn-notation.md
│   ├── dependency-taxonomy.md
│   ├── sizing-guide.md
│   ├── systems-catalog.md
│   ├── monte-carlo.md
│   └── estimation-integrity.md
└── .cursor-plugin/
    └── plugin.json
```

## Ways to Contribute

Contributions may include:

- Improving the 12-step assessment workflow
- Adding or refining Cart system information
- Updating sizing guidance using validated historical data
- Improving BPMN conventions and examples
- Adding dependency categories or delivery risks
- Improving output templates
- Correcting terminology, links, or formatting
- Updating agent or plugin metadata
- Adding validated delivery forecasting guidance

## Before You Start

Before making a change:

1. Check whether an existing issue or pull request already covers the change.
2. Confirm the proposed change is relevant to Cart delivery assessment.
3. Use source material that can be verified.
4. Do not add confidential, personal, security-sensitive, or production-secret information.
5. Do not invent system behaviour, ownership, sizing data, or Confluence links.

When information is uncertain, label it as an assumption or open question.

## Branching

Create a branch from the default branch.

Recommended naming:

```text
feature/<short-description>
fix/<short-description>
docs/<short-description>
chore/<short-description>
```

Examples:

```text
docs/update-bpmn-notation
feature/add-cart-refund-dependencies
fix/correct-paydock-description
```

## Editing `SKILL.md`

`SKILL.md` should remain focused on workflow and agent behaviour. Keep detailed reference material in the `references/` directory.

Changes to `SKILL.md` must preserve:

- Valid YAML front matter
- The mandatory 12-step sequence
- The standard Squad Sense opening line
- A maximum of five clarifying questions at a time
- Explicit separation of facts, assumptions, risks, recommendations, and open questions
- Provisional sizing when historical data is unavailable
- Estimate, forecast, target, constraint, and commitment distinctions
- Handoffs to downstream backlog and knowledge-publishing workflows

Do not turn `SKILL.md` into a large reference manual.

## YAML Front Matter

The YAML front matter must remain at the top of `SKILL.md`.

```yaml
---
name: squad-sense-cart
description: Assess, shape, size, and forecast Cart delivery initiatives. Trigger for requests such as "size this feature", "Squad Sense", "delivery forecast", "BPMN for...", and "initiate epic".
---
```

Requirements:

- Use spaces, not tabs.
- Keep field names lowercase unless the schema requires otherwise.
- Quote values containing special characters when needed.
- Do not add unsupported metadata without checking compatibility.

## Editing Reference Files

### `output-templates.md`

Maintain reusable schemas for the assessment sections. Keep headings, field names, and tables consistent with `SKILL.md`.

### `bpmn-notation.md`

Use BPMN 2.0 terminology. Distinguish events, tasks, gateways, sub-processes, pools, lanes, message flows, and sequence flows.

### `dependency-taxonomy.md`

Define dependency categories, criticality, lead-time risk, ownership, and delivery impact consistently.

### `sizing-guide.md`

Only update sizing bands or asset complexity values when supported by approved source material or historical delivery evidence. Do not present estimates as commitments.

### `systems-catalog.md`

For each system, include:

- System or platform name
- Purpose
- Owner or vendor, where known
- Integration role
- Complexity or impact
- Relevant domain scenarios
- Source or Confluence link

Use `TBC` for unknown ownership or links. Do not invent URLs.

### `monte-carlo.md`

Keep simulation rules aligned with the minimum data thresholds:

- 10–20 comparable completed items for a rough forecast
- 30 or more comparable items for a stronger forecast
- 6–10 sprints or weeks of throughput for squad-level forecasting

Forecasts should report P50, P75, P85, and P95 where the data supports them.

### `estimation-integrity.md`

Preserve clear distinctions between:

- Estimate
- Forecast
- Target date
- Constraint date
- Commitment

## Writing Style

Use concise, professional Australian English.

Prefer plain language, descriptive headings, evidence-based statements, explicit assumptions, and canonical Cart terminology.

Avoid unexplained acronyms, unsupported certainty, duplicate guidance, generic step lists presented as BPMN, and overly precise forecasts from weak data.

## Cart Terminology

| Preferred term | Avoid where possible |
|---|---|
| Cart | Bag, Checkout |
| Fulfilment method | Delivery type, Shipment type |
| Shipping rule | Shipping calculation, Delivery rule |
| Stock on hand | Inventory available |
| Marketplace item | Third-party item, where ambiguity may arise |

Terms may be clarified in context when a source system uses a different name.

## Source and Evidence Requirements

Changes based on Cart documentation should include a traceable source.

Acceptable sources include:

- Approved Confluence pages
- Architecture documentation
- Validated system-owner input
- Historical squad delivery data
- Approved operational process documentation
- Vendor documentation

When evidence conflicts:

1. Record the conflict.
2. Prefer the most authoritative and recent source.
3. Add an open question where resolution is required.
4. Do not silently merge incompatible information.

## Historical Delivery Data

Treat historical delivery data as primary evidence for sizing and forecasting.

When adding or analysing data:

- Identify or separate outliers.
- Segment by squad, work type, size, and dependency profile where possible.
- Avoid averaging unrelated work.
- State the sample size and period covered.
- Describe exclusions.
- Avoid overstating precision.

Do not commit raw data containing personal, confidential, or commercially sensitive information.

## Validation

Before submitting a pull request, check:

- Markdown renders correctly.
- Internal links work.
- YAML front matter is valid.
- JSON files are valid.
- Tables have consistent columns.
- The 12-step sequence remains intact.
- Sizing guidance matches the approved Cart model.
- Confluence links are real or marked `TBC`.
- No confidential information has been introduced.
- No estimate is described as a commitment.
- New terminology is defined where necessary.

Suggested checks:

```bash
git diff --check
python -m json.tool .cursor-plugin/plugin.json
```

Validate YAML with a YAML-aware validator, for example:

```bash
python -c "import yaml; yaml.safe_load(open('agents/openai.yaml')); print('YAML valid')"
```

## Commit Messages

Use clear, focused commit messages.

```text
<type>: <summary>
```

Examples:

```text
docs: add refund workflow conventions
fix: correct Order Master system role
feature: add dependency assessment template
chore: update plugin metadata
```

Keep each commit focused on one logical change.

## Pull Requests

A pull request should include:

- A concise description of the change
- The reason for the change
- Files affected
- Source or evidence used
- Risks or assumptions
- Rendered examples where formatting changed
- Validation completed
- Follow-up work required

Suggested checklist:

```markdown
- [ ] The change is relevant to Squad Sense — Cart.
- [ ] YAML and JSON files validate.
- [ ] Markdown renders correctly.
- [ ] Sources are documented.
- [ ] Assumptions are labelled.
- [ ] Sizing and forecasting guidance remains evidence-based.
- [ ] No confidential information is included.
- [ ] The mandatory 12-step sequence is preserved.
```

## Review Expectations

Reviewers should check accuracy, evidence quality, consistency with Cart terminology, workflow integrity, estimation integrity, security, readability, and compatibility with existing templates and agent behaviour.

Changes to sizing bands, system ownership, forecasting rules, or the mandatory workflow should receive review from the relevant Delivery, Business Analysis, Product, Engineering, or Architecture owner.

## Reporting Issues

When raising an issue, include:

- The affected file or section
- Current behaviour
- Expected behaviour
- Evidence or source
- Delivery impact
- Suggested resolution, when known

For incorrect system details, also include the system owner or SME who can validate the change.

## Security and Confidentiality

Do not commit:

- Credentials, API keys, or tokens
- Customer or team-member personal data
- Production secrets
- Restricted architecture details
- Vendor-confidential information
- Unapproved internal URLs or attachments

Report suspected security issues through the organisation's approved security process rather than a public issue.

## Code of Conduct

Contributors are expected to communicate respectfully, review constructively, and focus feedback on the change rather than the contributor.

## Questions

Use a repository issue or the approved team collaboration channel for contribution questions. Include enough context for reviewers to understand the proposed change without requiring access to private conversations.
