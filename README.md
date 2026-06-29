# i18n demo — BlueWallet (React Native) English→Arabic

Forge demo output from the **Supergrow translation skill**: an agent enters an OSS app's codebase, machine-translates a slice of its English base catalog into a target locale, and opens a reviewable PR.

- **Gold app:** [BlueWallet](https://github.com/BlueWallet/BlueWallet) (React Native)
- **Engine:** `react-localization` — single-brace `{var}` placeholders, no plural API
- **Target locale:** Arabic (`ar`), right-to-left (RTL)
- **Slice:** 198 keys (representative slice, not a full app translation)

## The PR

`main` holds the English base catalog (`locales/en.json`). The branch `add-arabic-ar` adds the generated Arabic catalog (`locales/ar.json`), so the PR diff is exactly the new locale file.

## Forge result

- **Gate score:** 91/100 (worker → optimizer loop, reached plateau)
- **Mechanics verified:** `scripts/check_locale_parity.mjs --all` → exit 0 (key parity + `{var}` placeholder parity between `en` and `ar`)

## What the worker learned

- Followed BlueWallet's `loc/vocabulary/ar.md` glossary — e.g. Seed → عبارة الاسترداد, watch-only → للقراءة فقط
- Kept brand / protocol nouns in Latin script: Bitcoin, Lightning, RBF, CPFP
