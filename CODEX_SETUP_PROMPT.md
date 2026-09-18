# Codex setup prompt / Prompt d'installation Codex

Open Codex from the cloned `obsidian-memory-skills` repository, then paste the prompt below.

Ouvrez Codex depuis le dépôt `obsidian-memory-skills` cloné, puis collez le prompt ci-dessous.

```text
Install the two Obsidian Project Memory skills from this repository for my personal Codex use.

Source folders:
- ./maj
- ./maj-analyse

Target folders:
- ~/.agents/skills/maj/
- ~/.agents/skills/maj-analyse/

First inspect whether either target skill already exists. If it does not exist, copy the complete source folder into the target folder without changing the repository source.

If a target skill already exists, do not overwrite it. Show me the existing SKILL.md path and ask whether I want to replace it, keep it, or install this skill under a different unique name.

After installation, verify that each target folder contains a SKILL.md with valid name and description frontmatter. Explain that I can invoke the skills in Codex with `$maj` and `$maj-analyse`. Do not edit any Obsidian vault and do not run either skill during setup.
```

Codex uses the same `SKILL.md` format, but discovers personal skills from `~/.agents/skills/` and invokes them with `$skill-name`.

Codex utilise le même format `SKILL.md`, mais découvre les skills personnels dans `~/.agents/skills/` et les invoque avec `$nom-du-skill`.
