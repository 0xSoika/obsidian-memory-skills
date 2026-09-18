# Obsidian Project Memory

> 🇬🇧 Turn your Obsidian vault into a durable second brain for any project — without rewriting everything after every session.
>
> 🇫🇷 Transformez votre vault Obsidian en second cerveau durable pour n’importe quel projet — sans tout réécrire après chaque session.

<p align="center">
  <strong>Claude Code</strong> · <strong>Codex</strong> · <strong>Obsidian</strong><br>
  <em>Beta — built for real projects, improved through feedback.</em>
</p>

## What it does / Ce que ça fait

🇬🇧 Project context usually gets lost between sessions: what was decided, what was tried, where the project stands, and what matters next. This repository gives your AI agent a lightweight routine to keep that context clear in Obsidian.

🇫🇷 Entre deux sessions, on perd souvent le contexte : ce qui a été décidé, testé, appris, l’état réel du projet et la suite. Ce dépôt donne à votre agent IA une routine légère pour garder tout ça clair dans Obsidian.

🇬🇧 It works for AI and e-commerce projects, code, business operations, deep research, and more — any project where decisions and progress should not disappear with the chat history.

🇫🇷 Ça fonctionne pour les projets IA et e-commerce, le code, la gestion business, les recherches approfondies, etc. — bref, tout projet dont les décisions et l’avancée ne doivent pas disparaître avec l’historique du chat.

## The two skills / Les deux skills

| | Main job | Use it when… |
| --- | --- | --- |
| **`maj`** | 🇬🇧 Saves only what is new and useful from the session.<br>🇫🇷 Sauvegarde uniquement les nouveautés utiles de la session. | 🇬🇧 You finish working, or your context window is nearly full.<br>🇫🇷 Vous terminez une session, ou votre fenêtre de contexte approche de la limite. |
| **`maj-analyse`** | 🇬🇧 Audits the project memory and surfaces improvements.<br>🇫🇷 Audite la mémoire du projet et fait remonter les améliorations utiles. | 🇬🇧 Occasionally, before an important phase, or when the vault feels messy.<br>🇫🇷 Ponctuellement, avant une phase importante ou quand le vault commence à devenir confus. |

```text
🇬🇧 Work → maj → Obsidian memory stays current → maj-analyse (occasionally) → better next maj
🇫🇷 Travail → maj → mémoire Obsidian à jour → maj-analyse (ponctuellement) → prochain maj amélioré
```

## Why it stays lightweight / Pourquoi ça reste léger

🇬🇧 `maj` works in **delta mode**. It uses the current session, then reads only the few notes needed to update the right place. It does not rescan the entire vault, rebuild the structure, or rewrite unchanged notes every time.

🇫🇷 `maj` travaille en **mode delta**. Il part de la session en cours, puis lit seulement les quelques notes nécessaires pour écrire au bon endroit. Il ne rescane pas tout le vault, ne reconstruit pas la structure et ne réécrit pas les notes inchangées à chaque fois.

🇬🇧 `maj-analyse` is intentionally deeper, but occasional. Its recommendations are recorded so the next `maj` can use the safe ones, while structural changes stay under your control.

🇫🇷 `maj-analyse` est volontairement plus poussé, mais ponctuel. Ses recommandations sont enregistrées afin que le prochain `maj` puisse appliquer les améliorations sûres, tandis que les changements structurels restent sous votre contrôle.

## Start here / Commencez ici

### 1. Install the skills / Installez les skills

#### Claude Code

🇬🇧 Copy both folders from this repository into your personal Claude Code skills directory, then restart Claude Code.

🇫🇷 Copiez les deux dossiers de ce dépôt dans le dossier de skills personnel de Claude Code, puis redémarrez Claude Code.

```text
~/.claude/skills/maj/SKILL.md
~/.claude/skills/maj-analyse/SKILL.md
```

🇬🇧 To install them for one project only, use `your-project/.claude/skills/` instead.

🇫🇷 Pour les installer dans un seul projet, utilisez plutôt `votre-projet/.claude/skills/`.

#### Codex

🇬🇧 Open this repository in Codex and paste the ready-to-use [Codex setup prompt](CODEX_SETUP_PROMPT.md). It installs the skills in `~/.agents/skills/` while leaving this repository unchanged.

🇫🇷 Ouvrez ce dépôt dans Codex et collez le [prompt d’installation Codex](CODEX_SETUP_PROMPT.md). Il installe les skills dans `~/.agents/skills/`, sans modifier ce dépôt.

### 2. Point the agent to your vault / Indiquez votre vault à l’agent

🇬🇧 Once per project, add this to that project’s `CLAUDE.md` (or give Codex the same information in its project instructions):

🇫🇷 Une seule fois par projet, ajoutez ceci au `CLAUDE.md` du projet (ou donnez la même information à Codex dans les instructions du projet) :

```md
## Obsidian memory / Mémoire Obsidian
- Vault: `/absolute/path/to/my-vault`
- Project area / Zone du projet: `Projects/My project`
```

🇬🇧 If the path is missing or several vaults are possible, the skill asks before writing. It never guesses a location that could be wrong.

🇫🇷 Si le chemin manque ou que plusieurs vaults sont possibles, le skill demande avant d’écrire. Il ne devine jamais un emplacement qui pourrait être mauvais.

### 3. Use it / Utilisez-les

| Tool | Update session memory | Audit the memory |
| --- | --- | --- |
| **Claude Code** | `/maj` | `/maj-analyse` |
| **Codex** | `$maj` | `$maj-analyse` |

🇬🇧 You can add a short instruction: `/maj Decision: launch postponed to October.`

🇫🇷 Vous pouvez ajouter une précision : `/maj Décision : lancement reporté à octobre.`

## What happens on the first update? / Que se passe-t-il au premier update ?

🇬🇧 The skill first respects your existing vault. If the project has no dedicated area yet, it creates only a stable minimum: a project overview, a dated session journal, and a decision log only when a lasting decision exists.

🇫🇷 Le skill respecte d’abord votre vault existant. Si le projet n’a pas encore d’espace dédié, il crée seulement un minimum stable : une vue d’ensemble, un journal de sessions daté et un registre de décisions uniquement lorsqu’une décision durable existe.

🇬🇧 The structure then grows with the project, without moving or renaming your existing notes: an architecture note for software, research notes for a research project, deliverables for a creative project, and so on.

🇫🇷 La structure évolue ensuite avec le projet, sans déplacer ni renommer vos notes existantes : une note d’architecture pour le logiciel, des notes de recherche pour une recherche, des livrables pour un projet créatif, etc.

## What `maj-analyse` can change / Ce que `maj-analyse` peut changer

🇬🇧 Its report separates safe, local improvements from changes that need your approval. It can flag duplicate information, weak links, stale notes, inconsistencies, or orphaned notes. It does not silently merge, move, rename, or delete your content.

🇫🇷 Son bilan sépare les améliorations locales et sûres des changements qui demandent votre validation. Il peut signaler les doublons, liens faibles, notes obsolètes, incohérences ou notes orphelines. Il ne fusionne, ne déplace, ne renomme et ne supprime jamais votre contenu en silence.

## Beta, privacy & feedback / Bêta, vie privée et retours

🇬🇧 This is a beta meant for real workflows. If you try it, feedback about your project type, vault structure, what worked, and what surprised you is especially useful. Do not share confidential notes.

🇫🇷 C’est une bêta pensée pour de vrais workflows. Si vous l’essayez, les retours sur votre type de projet, la structure initiale du vault, ce qui a fonctionné ou surpris sont particulièrement utiles. Ne partagez pas de notes confidentielles.

🇬🇧 Your notes stay in your Obsidian vault, but text read by Claude Code or Codex may be sent to the AI service you use, according to its own configuration. This is not an offline-only tool.

🇫🇷 Vos notes restent dans votre vault Obsidian, mais le texte lu par Claude Code ou Codex peut être transmis au service IA utilisé, selon sa propre configuration. Ce n’est pas un outil entièrement hors ligne.

🇬🇧 Already using a `maj` command? Do not overwrite it. Install this skill under a different folder and give it a unique command name in its frontmatter.

🇫🇷 Vous utilisez déjà une commande `maj` ? Ne l’écrasez pas. Installez ce skill dans un autre dossier et donnez-lui un nom de commande unique dans son frontmatter.
