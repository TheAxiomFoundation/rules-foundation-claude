---
description: "Validate encoded policy against multiple tax/benefit systems"
argument-hint: "<RuleSpec YAML path>"
---

# Validate Policy Command

Validate an Axiom RuleSpec YAML artifact.

## Arguments
- `$ARGUMENTS` - Path to a RuleSpec YAML file

## Workflow

### 1. Run validation

```bash
cd ~/TheAxiomFoundation/axiom-encode
uv run axiom-encode validate "$ARGUMENTS"
```

### 2. Interpret results

**Consensus Levels:**
- Compile pass means the YAML shape and imports are accepted by Axiom Rules.
- CI pass means local RuleSpec tests and grounding checks pass.
- Oracle pass means an external model, when configured, agrees on comparable cases.

### 3. Report findings

Summarize:
- Total tests run
- Pass/fail rate
- Potential upstream bugs detected
- Recommended actions
