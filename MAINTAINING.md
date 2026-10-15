# Matcha maintenance branch

This fork preserves the deployed plugin version with a small maintenance patch set.

- Maintenance branch: `matcha-stable` (the fork's default branch).
- Upstream base commit: `2b97b4d498f618847f257eb54159fe532bb02eb9`.
- AstrBot repository source: `https://github.com/mydosu/astrbot_plugin_qzone_tools/tree/matcha-stable`.
- Original author attribution and upstream license are retained.

Keep QZone tool guidance scoped to its own tools, retain current browser compatibility, and avoid rewriting unrelated memory-tool rules.

## Updating AstrBot

Bind this installed plugin to the **Repository** source using the URL above. AstrBot stores this binding separately from `metadata.yaml`; both must point to the fork. The explicit branch avoids falling back to the unpatched upstream tracking branch if GitHub's default-branch API is unavailable.

Plugin settings, provider credentials, persona definitions and conversation databases live outside this repository. Keep the existing AstrBot data directory when updating. In particular, the installed OutputPro configuration uses at most two reply segments and does not split on the Chinese comma; these settings are not replaced by this source tree.

## Maintaining the fork

Keep upstream work on the upstream tracking branch. Review and merge or cherry-pick upstream changes into `matcha-stable`, run the applicable context, memory and reply-splitting regressions, and publish that branch. Do not replace the maintenance branch wholesale with the upstream default branch. Preserve the repository URL in `metadata.yaml` so a later update retains the fork binding.

The plugin version is retained from the deployed release. Bump `metadata.yaml` when intentionally publishing a new maintenance release; Git commits identify this initial patch set.

The MIT license file is retained from upstream commit `768792b9d43801466d7d00d798011fce2b85cef3`; the deployed 5.0.6 source tree did not include a license file.
