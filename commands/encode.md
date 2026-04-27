---
description: "Encode a source citation or source slice into Axiom RuleSpec YAML"
argument-hint: "<citation> (e.g., '26 USC 1', '26 USC 32(c)(2)(A)')"
---

# Encode Source

Runs the Axiom Encode pipeline and emits RuleSpec YAML.

## Usage

```
/encode 26 USC 1
/encode 26 USC 32
/encode 7 USC 2017(a)
```

## What Happens

The command should:

1. Resolve the cited source text from the source registry or an official source.
2. Generate a `format: rulespec/v1` YAML artifact.
3. Validate with `axiom-encode validate`.
4. Report the output path and validation result.

## Invoke

```bash
cd ~/TheAxiomFoundation/axiom-encode
uv run axiom-encode encode "$ARGUMENTS" --output /tmp/axiom-encode-encodings
```
