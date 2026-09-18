# Obsidian Project Memory

**[Read in English](README.md)**

> Deux commandes Claude Code pour transformer le travail d'une session en une mémoire projet claire, vivante et durable dans Obsidian.

**Statut : bêta.** Le projet est publié pour être testé sur des vaults et des sujets variés. Les retours sur la structure créée, les cas limites et la consommation de contexte sont les bienvenus.

## Pourquoi ?

Le contexte utile d'un projet disparaît souvent entre les sessions : décisions, pistes abandonnées, état réel, apprentissages et prochaines étapes. Ce projet apporte une mémoire dans Obsidian sans transformer chaque fin de session en audit coûteux ni réécrire tout le vault.

Il fonctionne aussi bien pour du logiciel que pour une recherche, une activité, une création, une formation ou un projet personnel.

## Les deux commandes

| Commande | Rôle | Quand l'utiliser |
| --- | --- | --- |
| `/maj` | Sauvegarde les nouveautés de la session, de façon incrémentale. | À la fin d'une session de travail. |
| `/maj-analyse` | Vérifie la santé et la cohérence de la mémoire du projet. | De temps en temps, ou avant une phase importante. |

Le duo suit ce cycle :

```text
Travail dans Claude Code
        ↓
      /maj
        ↓
Mémoire du projet actualisée dans Obsidian
        ↓
  /maj-analyse  (ponctuellement)
        ↓
Bilan « Analyse de mémoire » et recommandations
        ↓
      /maj
        ↓
Application des améliorations sûres + sauvegarde de la session
```

## Installation

Copiez les deux dossiers de ce dépôt dans votre dossier de skills Claude Code :

```text
~/.claude/skills/maj/SKILL.md
~/.claude/skills/maj-analyse/SKILL.md
```

Redémarrez Claude Code. Les commandes `/maj` et `/maj-analyse` seront alors disponibles dans tous vos projets.

Pour les rendre disponibles dans un seul projet, placez-les plutôt ici :

```text
votre-projet/.claude/skills/maj/SKILL.md
votre-projet/.claude/skills/maj-analyse/SKILL.md
```

## Configuration du vault — une fois par projet

Pour que Claude sache immédiatement où écrire, indiquez une fois votre vault et la zone du projet dans le `CLAUDE.md` de ce projet :

```md
## Mémoire Obsidian
- Vault : `/chemin/absolu/vers/mon-vault`
- Zone de ce projet : `Projets/Mon projet`
```

S'il n'existe qu'un seul vault accessible et clairement associé à la session, le skill peut l'utiliser directement. S'il y a plusieurs vaults possibles ou aucun chemin accessible, il demande le bon chemin au lieu de risquer d'écrire au mauvais endroit.

## Utilisation

À la fin d'une session :

```text
/maj
```

Vous pouvez joindre une précision :

```text
/maj Décision : le lancement est reporté à octobre.
```

Pour un audit complet de la mémoire du projet :

```text
/maj-analyse
```

## Ce qui se passe au premier `/maj`

Le skill respecte d'abord l'organisation existante du vault. S'il ne trouve aucune zone pour le projet, il crée une base minimale et stable :

- une `Vue d'ensemble` avec l'objectif, le périmètre et l'état actuel ;
- un `Journal` contenant la première entrée de session ;
- un registre `Décisions` uniquement lorsqu'une vraie décision durable existe.

Le projet peut démarrer très petit. La structure grandit uniquement lorsque le contenu le justifie : une recherche récurrente peut obtenir une note `Recherche`, un projet de création une note `Livrables`, un logiciel une note `Architecture`, etc. Les notes existantes ne sont pas déplacées ou renommées au fil des sessions.

## Une mémoire utile sans gaspiller le contexte

`/maj` travaille en **delta** : il utilise ce que Claude connaît déjà de la session, lit la carte du projet, le journal au point d'insertion et seulement les notes concernées. Il ne relit pas le vault entier, ne reformule pas toutes les pages et ne recrée pas l'architecture à chaque utilisation.

`/maj-analyse` est volontairement plus approfondi, mais ponctuel. Il inspecte la structure complète du vault puis ouvre seulement les notes pertinentes pour vérifier les liens, doublons, incohérences, notes orphelines et informations devenues obsolètes.

## Sécurité et contrôle humain

L'analyse crée une note `Analyse de mémoire` avec deux catégories :

- **À appliquer par `/maj`** : améliorations locales et non destructives, que la prochaine mise à jour peut appliquer ;
- **Décisions à valider** : fusion, déplacement, renommage, suppression ou changement majeur de structure.

Les décisions de la seconde catégorie ne sont jamais appliquées sans confirmation explicite. Le skill ne fabrique pas de faits, d'échéances ou de tâches, et ne modifie pas les fichiers de production du projet.

## Contribuer et faire un retour

Ce projet est en phase de test. Si vous l'essayez, un retour utile contient : le type de projet, la forme initiale du vault, ce qui a bien fonctionné et ce qui vous a surpris. Ne partagez pas de notes confidentielles.
