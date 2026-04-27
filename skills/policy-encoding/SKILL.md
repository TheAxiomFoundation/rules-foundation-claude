---
name: Policy Encoding
description: Use this skill when encoding tax/benefit statutes into Axiom RuleSpec, creating tests, or validating implementations against authoritative calculators
version: 2.0.0
---

# Policy Encoding Skill

This skill provides patterns and guidance for encoding tax and benefit law into Axiom RuleSpec YAML.

## Where Encodings Go

RuleSpec artifacts live in the jurisdiction rules repositories. Source registries and manifests also live there. Raw source payloads are external storage or official web sources, not committed generated XML payloads.

## Filepath And Scope

- The filepath identifies the legal source unit being encoded.
- Encode only that source unit. Do not mix sibling or parent provisions into a leaf file.
- Use one RuleSpec YAML artifact for one source unit.
- Use a `.test.yaml` companion for executable examples when the source is assertable.

## Minimal RuleSpec Shape

```yaml
format: rulespec/v1
module:
  summary: |-
    <exact source text>
rules:
  - name: example_amount
    kind: parameter
    dtype: Money
    unit: USD
    versions:
      - effective_from: '2024-01-01'
        formula: |-
          451
```

## Validation

```bash
cd ~/TheAxiomFoundation/axiom-encode
uv run axiom-encode validate path/to/file.yaml
```

Before marking an encoding complete:

- [ ] RuleSpec compile passes.
- [ ] Companion tests pass or the artifact is explicitly nonassertable.
- [ ] Every legal amount, rate, threshold, cap, or limit is grounded in source text.
- [ ] Imports resolve to existing RuleSpec definitions.
- [ ] External calculator differences are documented with concrete inputs and expected outputs.
