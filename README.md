# mnemon-dev/assets

Public media storage for Pull Request and Issue visual evidence across Mnemon repositories.

## Directory Layout

- `<repo>/pr/<slug>/<file>`: redacted screenshots and short recordings referenced from Pull Request descriptions by full 40-character commit SHA:
  `https://raw.githubusercontent.com/mnemon-dev/assets/<sha>/<repo>/pr/<slug>/<file>`

## Rules

- Upload only synthetic or redacted evidence. Never upload API keys, tokens, personal data, or private memory.
- Reference uploaded files by full 40-character commit SHA so links stay stable across future commits.
