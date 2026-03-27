# Publishing Checklist

Use this checklist before publishing the repository publicly.

## Required before public release

- Choose the final public contact email and replace the email placeholder in `.codex-plugin/plugin.json`.
- Review `README.md`, `PRIVACY.md`, and `TERMS.md` for final wording.
- Confirm no local absolute paths, private endpoints, tokens, or personal provider names remain anywhere in the repo.

## Recommended before public release

- Add plugin icon and screenshots if you want a more polished plugin card.
- Add example prompts or sample outputs to the README.
- Tag the first release as `v0.1.0` after the final review.

## Local release check

From the repository root:

```bash
python3 - <<'PY'
from pathlib import Path
import json, re

root = Path('.')
plugin = json.loads((root / '.codex-plugin' / 'plugin.json').read_text())
assert plugin['name'] == 'finlens-catalyst-mapper'
assert (root / 'skills' / 'finlens-catalyst-mapper-cn' / 'SKILL.md').exists()
assert (root / 'skills' / 'finlens-catalyst-mapper-global' / 'SKILL.md').exists()
assert re.fullmatch(r'[a-z0-9-]+', plugin['name'])
print('basic-package-check: ok')
PY
```
