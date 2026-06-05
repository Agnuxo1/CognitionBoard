# New Cognitive Skills Contribution Guide

This guide supports https://github.com/Agnuxo1/CognitionBoard/issues/1.

The issue proposes three new skills:

- Neuroscientist,
- Anthropologist,
- Roboticist.

The current public README describes the board as 6x4. Adding three skills means contributors must either expand the board or replace/merge existing cells. To avoid accidental collisions, this guide defines a conservative path.

## Recommended Approach

Use an extension row instead of changing the stable 6x4 board immediately.

| Proposed code | Skill | Domain | Why |
|---|---|---|---|
| `E1` | Neuroscientist | Science | Brain-computer interfaces, neural systems, cognitive neuroscience. |
| `E2` | Anthropologist | Humanities | Cultural evolution, ethnography, human variation, social systems. |
| `E3` | Roboticist | Applied science / engineering | Embodied autonomy, controls, perception, planning, human-robot interaction. |

This keeps the original board stable while allowing a future v2 board to become 6x5 or 7x4 after tests and docs are updated.

## Skill Metadata Template

Each new skill should include:

```json
{
  "code": "E1",
  "name": "Neuroscientist Mind",
  "domain": "science",
  "summary": "Neuroscience, neural systems, brain-computer interfaces, cognition, and neurotechnology.",
  "routes_after": ["D5", "A1"],
  "routes_before": ["D3", "D6"],
  "keywords": ["neuroscience", "BCI", "neural", "cognition", "brain"]
}
```

Adjust field names to match the repository's actual `skills.json` structure if it differs.

## Skill Scope

### Neuroscientist

Use for:

- brain-computer interface research,
- neural encoding/decoding,
- cognitive neuroscience,
- neuroimaging interpretation,
- synaptic plasticity and learning,
- neural safety constraints.

Expected routes:

```text
D5.A1.E1.D6
D5.A1.E1.A6.D3.D6
D5.A1.E1.C3.D3.D6
```

### Anthropologist

Use for:

- cultural evolution,
- ethnographic analysis,
- kinship and social organization,
- symbolic systems,
- human adaptation,
- cross-cultural comparison.

Expected routes:

```text
D5.A1.E2.D6
D5.A1.E2.B1.D4.D6
D5.A1.E2.D2.D4.D6
```

### Roboticist

Use for:

- autonomous robotics,
- embodied agents,
- perception-action loops,
- SLAM and navigation,
- control systems,
- human-robot interaction.

Expected routes:

```text
D5.A1.E3.C5.A6.D3.D6
D5.A1.E3.A3.C5.D3.D6
D5.A1.E3.D6
```

## Files To Update

The original issue names these files:

- `src/cognitionboard/skills.json`,
- `src/cognitionboard/board.py`,
- `tests/test_skills.py`.

If those paths are not present in the current branch, add the equivalent metadata and tests in the actual package path and update this guide.

## Acceptance Criteria

- [ ] New skill codes do not collide with existing board cells.
- [ ] Each skill has metadata, keywords, route hints, and a short usage description.
- [ ] Board routing can select the new skill from representative prompts.
- [ ] Tests cover all three new skills.
- [ ] README and skill index mention the extension row or new board version.
- [ ] Existing paths such as `D5.A1.A2.D6` still work.

## Suggested Tests

```python
def test_new_skill_codes_are_unique():
    codes = [skill["code"] for skill in load_skills()]
    assert len(codes) == len(set(codes))


def test_neuroscience_prompt_routes_to_e1():
    path = route("Design a brain-computer interface experiment")
    assert "E1" in path


def test_anthropology_prompt_routes_to_e2():
    path = route("Analyze cultural evolution in small communities")
    assert "E2" in path


def test_robotics_prompt_routes_to_e3():
    path = route("Plan an autonomous robot navigation stack")
    assert "E3" in path
```

## Documentation Update

When implemented, update the README board section with either:

- an `Extension Row E` table, or
- a new full v2 board layout.

Do not silently add the skills to the 6x4 layout without explaining the board-size change.
