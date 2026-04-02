# Ghidra Skill Package

This repository is an exact-mirror export of the tracked ghidra skill family
from the source repository. Use it to browse the published skill directories,
review the release history, and confirm how the package maps back to its source
version.

## Start Here

1. Read the top-level inventory below to understand the published package.
2. Start with `ghidra-headless/` when you need the family entrypoint and
   routing guide, then move to a phase-specific skill from the stable
   identifier and display-title mapping table.
3. Review `.release-manifest.json` when you need source and release
   traceability details.

## Top-Level Inventory

| Entry | Type | Purpose |
| --- | --- | --- |
| `README.md` | Package guide | Explains the published package, entrypoints, and traceability surfaces. |
| `CHANGELOG.md` | Release history | Mirrors the published release notes for the ghidra skill family. |
| `ghidra-headless/` | Skill directory | Route headless Ghidra workflow planning |
| `ghidra-headless-auto-evolution/` | Skill directory | Promote reusable workflow improvements |
| `ghidra-headless-evidence/` | Skill directory | Plan evidence extraction and audit |
| `ghidra-headless-frida-evidence/` | Skill directory | Import Frida evidence for review |
| `ghidra-headless-frida-runtime-injection/` | Skill directory | Plan reproducible Frida runtime capture |
| `ghidra-headless-intake/` | Skill directory | Plan target intake and project setup |
| `ghidra-headless-progressive-decompilation/` | Skill directory | Plan selected decompilation and compare |
| `ghidra-headless-script-review/` | Skill directory | Author and audit reusable scripts |
| `.release-manifest.json` | Release metadata | Records source, version, destination, and publish timing traceability. |

## Published Skills

| Stable ID | Display Title | Short Description | UI Surface | Fallback Label |
| --- | --- | --- | --- | --- |
| `ghidra-headless` | Ghidra Headless | Route headless Ghidra workflow planning | `agents/openai.yaml` `interface.display_name` | `ghidra-headless` |
| `ghidra-headless-auto-evolution` | Ghidra Auto Evolution | Promote reusable workflow improvements | `agents/openai.yaml` `interface.display_name` | `ghidra-headless-auto-evolution` |
| `ghidra-headless-evidence` | Ghidra Evidence Review | Plan evidence extraction and audit | `agents/openai.yaml` `interface.display_name` | `ghidra-headless-evidence` |
| `ghidra-headless-frida-evidence` | Ghidra Frida Evidence | Import Frida evidence for review | `agents/openai.yaml` `interface.display_name` | `ghidra-headless-frida-evidence` |
| `ghidra-headless-frida-runtime-injection` | Ghidra Frida Runtime Capture | Plan reproducible Frida runtime capture | `agents/openai.yaml` `interface.display_name` | `ghidra-headless-frida-runtime-injection` |
| `ghidra-headless-intake` | Ghidra Headless Intake | Plan target intake and project setup | `agents/openai.yaml` `interface.display_name` | `ghidra-headless-intake` |
| `ghidra-headless-progressive-decompilation` | Progressive Decompilation | Plan selected decompilation and compare | `agents/openai.yaml` `interface.display_name` | `ghidra-headless-progressive-decompilation` |
| `ghidra-headless-script-review` | Ghidra Script Review | Author and audit reusable scripts | `agents/openai.yaml` `interface.display_name` | `ghidra-headless-script-review` |

## Title Display In Codex

- Codex-compatible hosts can show the human-friendly title from
  `agents/openai.yaml` `interface.display_name`.
- Stable directory identifiers remain the compatibility anchor for routing,
  release automation, and repository links.
- If Codex or another host does not surface the display title, use the stable
  identifiers listed above.

## Traceability

- Source repository: `byteland-app/ghidra-headless-skill`
- Source version: `1.4.0`
- Source tag: `v1.4.0`
- Source commit: `c352780ebc79f509d4bfef47b1e8b8fb5e36a393`
- Destination repository: `ByteLandTechnology/ghidra-headless`
- Destination branch: `main`
- Destination directory: `repository root`
- Metadata file: `.release-manifest.json`
