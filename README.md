# Renovate Config

[![MIT](https://img.shields.io/badge/MIT-gray?logo=github&logoColor=white)](LICENSE)

Custom configuration for Renovate.

- `base.json` - core Renovate settings including semantic commits, dependency dashboard, and Go module tidying.
- `groups.json` - groups monorepo packages and explicitly linked modules (e.g. purpleclay/x) into single PRs.
- `labels.json` - applies labels to PRs based on update type (major, minor, patch, digest).
- `automerge.json` - enables auto-merge for minor and patch updates when all status checks pass.
- `nix.json` - enables the (beta) nix manager to update flake inputs and maintain `flake.lock`.
- `regexmatch.json` - custom regex managers for versioned variables in Dockerfiles, GitHub workflows and composite GitHub actions.

## Enabling Auto-merge

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>purpleclay/renovate-config",
    "github>purpleclay/renovate-config//automerge"
  ]
}
```

## Enabling Nix

Renovate's nix manager is in beta and disabled by default. Opting in will raise PRs to update each input within `flake.lock`, along with a scheduled lock file maintenance PR that refreshes the entire file. Lock file maintenance only applies to Nix and does not affect other managers.

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>purpleclay/renovate-config",
    "github>purpleclay/renovate-config//nix"
  ]
}
```
