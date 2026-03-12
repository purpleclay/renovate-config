# Renovate Config

[![MIT](https://img.shields.io/badge/MIT-gray?logo=github&logoColor=white)](LICENSE)

Custom configuration for Renovate.

- `base.json` - core Renovate settings including semantic commits, dependency dashboard, and Go module tidying.
- `groups.json` - groups monorepo packages and explicitly linked modules (e.g. purpleclay/x) into single PRs.
- `labels.json` - applies labels to PRs based on update type (major, minor, patch, digest).
- `automerge.json` - enables auto-merge for minor and patch updates when all status checks pass.
- `regexmatch.json` - custom regex managers for versioned variables in Dockerfiles and GitHub workflows.

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
