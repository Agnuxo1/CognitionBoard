# Output Skill (D6)

## Role
Final formatting, token compression, and delivery.

## Protocol

```
1. Apply token compression rules (A1)
2. Format output according to task type
3. Add PATH footer
4. Log session
```

## Token Compression Rules

| Verbose | Compressed |
|---------|-----------|
| "for all x in S, P holds" | `∀x∈S: P(x)` |
| "there exists x such that" | `∃x:` |
| "if and only if" | `↔` |
| "implies" | `→` |
| "therefore" | `∴` |
| "because" | `∵` |
| "approximately" | `≈` |
| "proportional to" | `∝` |
| "is defined as" | `≝` |
| "contradiction" | `⊥` |

## Path Footer

Always end with:
```
---
PATH: {full path}
```

Example:
```
---
PATH: D5.A1.A2.B6.D6
```
