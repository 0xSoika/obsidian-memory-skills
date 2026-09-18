---
name: maj-analyse
description: Audite la mémoire Obsidian d'un projet et produit un bilan actionnable pour /maj. Utiliser avec /maj-analyse pour vérifier cohérence, structure, liens, doublons et informations périmées sans modifier les notes du projet.
---

# Analyse de la mémoire projet

Avec `/maj-analyse`, réalise un audit approfondi de la mémoire Obsidian du projet courant. Le but est d'identifier ce qui aiderait la mémoire à rester fiable, navigable et adaptée à l'état réel du projet ; ce n'est ni un résumé gratuit ni une réorganisation automatique.

## Périmètre

Résous le vault et la zone projet exactement comme `/maj` : instructions du projet, conversation, chemin déjà utilisé ou unique vault accessible. Si aucun emplacement fiable ne peut être résolu, demande le chemin avant toute lecture ou écriture.

Analyse d'abord la zone du projet, ses index et les notes qui la référencent. Pour répondre à une incohérence potentielle avec le reste du vault, examine l'inventaire global (noms, chemins, liens et métadonnées), puis ouvre le contenu seulement des notes pertinentes. Par défaut, les autres projets ne sont jamais des anomalies. Analyse le vault entier seulement si l'utilisateur le demande explicitement.

## Ce qu'il faut vérifier

- La mémoire représente-t-elle encore le projet et son état actuel ?
- Les notes fondatrices et les liens permettent-ils de retrouver les informations importantes ?
- Y a-t-il des doublons, liens cassés, notes orphelines, contradictions, informations périmées ou contenu manifestement hors périmètre ?
- Une note est-elle devenue trop chargée au point de justifier une note spécialisée ?
- Les décisions, livrables, recherches et actions confirmées sont-ils placés à un endroit compréhensible ?

Ne signale pas des préférences esthétiques comme des problèmes. Ne prétends pas qu'une information est erronée si tu ne disposes pas d'un élément concret qui la contredit.

## Bilan durable

Ne modifie aucune note métier, de projet ou personnelle pendant l'analyse. Crée ou actualise le bilan le plus récent dans la zone du projet sous le nom `Analyse de mémoire` (ou respecte un nom déjà employé pour ce bilan). Ne remplace jamais aveuglément les commentaires et décisions humaines déjà présents.

Le bilan doit être court, daté et organisé ainsi :

1. `Couverture` — zone analysée, contenu réellement ouvert et limites ;
2. `État général` — une appréciation factuelle en quelques lignes ;
3. `Recommandations` — chaque recommandation contient un identifiant stable, les notes concernées, le constat justifié, le changement proposé, l'impact (`local` ou `structurel`), le statut (`proposée`, `approuvée`, `refusée`, `appliquée`, `obsolète`) et un champ `Commentaire utilisateur` ;
4. `Observations` — risques ou incohérences constatés, avec liens vers les notes concernées.

Ne crée aucune rubrique vide. Chaque recommandation doit indiquer la raison et les notes concernées. Conserve identifiants, statuts, refus et commentaires lors d'une analyse suivante ; ne recrée pas une recommandation refusée et inchangée. Signale clairement lorsqu'aucun problème significatif n'a été trouvé.

## Relation avec `/maj`

Le prochain `/maj` lit ce bilan. Il applique uniquement les recommandations locales, non destructives, encore justifiées et au statut `proposée` ou `approuvée`. Il vérifie les notes avant l'application et marque ensuite le résultat réel dans le bilan.

Les éléments de `Décisions à valider` restent des propositions. Ils ne sont appliqués que si l'utilisateur les confirme explicitement dans un prochain `/maj`. Le rapport final de l'analyse indique toujours les décisions qui attendent cette confirmation.

Termine par un compte rendu bref : couverture de l'analyse, bilan créé ou actualisé et nombre de recommandations à appliquer ou à valider.
