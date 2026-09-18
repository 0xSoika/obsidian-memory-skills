---
name: maj
description: Met à jour progressivement la mémoire Obsidian d'un projet à partir du travail de la session. Utiliser avec /maj pour sauvegarder les faits, décisions, livrables et prochaines étapes sans réécrire le vault.
---

# Mémoire projet incrémentale

Avec `/maj`, transforme uniquement les nouveaux faits établis pendant cette session en mémoire durable dans le vault Obsidian du projet. Une note donnée avec la commande apporte du contexte, mais n'est enregistrée comme fait que si elle est formulée comme telle.

Le résultat doit devenir plus utile au fil des sessions : d'abord un socle très simple, puis des notes spécialisées seulement lorsque l'évolution réelle du projet les justifie. L'organisation reste reconnaissable d'une session à l'autre ; ne la reconstruis jamais pour la rendre plus "parfaite".

Cette compétence s'adapte à tout sujet : logiciel, recherche, création, entreprise, étude, association ou projet personnel. Elle ne suppose ni code, ni Git, ni format précis de vault.

## Résoudre automatiquement le bon emplacement

1. Utilise le vault et la zone de projet indiqués dans les instructions du projet, dans la conversation ou déjà utilisés durant la session.
2. Si un seul vault accessible est clairement lié à la session, utilise-le. Si le projet n'a pas encore de zone dans ce vault, utilise le nom clair du dossier de travail ou du projet pour l'initialiser.
3. S'il existe plusieurs vaults possibles ou qu'aucun chemin de vault n'est accessible, demande le chemin une seule fois et n'écris pas avant la réponse. Sans chemin, il est impossible de savoir quel dossier l'utilisateur veut réellement modifier.

Ne modifie jamais un autre projet, même si son nom paraît similaire. Ne consigne que les faits connus pendant la session et ne modifie pas les fichiers de production du projet.

Après la première résolution, réutilise l'index du projet. S'il n'expose pas clairement les chemins du journal, des décisions et du bilan, crée ou complète une section technique compacte marquée `<!-- obsidian-project-memory -->`. Elle contient seulement ces chemins, la langue du vault et le lien du bilan actif. Ne crée pas une seconde base de connaissances.

## Contrat de coût : travailler en delta

- Ne fais jamais d'audit complet et ne relis jamais le vault pour reconstruire le contexte de la session.
- Commence par un résumé mental des résultats, modifications, décisions, blocages, prochaines actions confirmées et apprentissages de la session.
- Lis seulement la carte du projet (`Vue d'ensemble` ou index), le journal au point d'insertion, puis les une à trois notes directement impactées. Si une note a été lue ou modifiée plus tôt dans cette session, ne la relis pas sans raison.
- Écris des deltas concis : une entrée de journal, un ajout ou une correction localisée, une décision courte. Ne reformule pas une page entière si un paragraphe ou une ligne suffit.
- Ne mets à jour les champs de date, résumés ou index que lorsqu'une information nouvelle les rend réellement obsolètes.
- Avant toute écriture, compare les faits nouveaux à la dernière entrée ou section pertinente. S'ils sont déjà consignés, n'écris rien, ne crée pas de doublon et ne change aucune date.
- Traite toutes les notes réellement concernées, en lisant uniquement les sections utiles. Ne fixe pas de nombre maximal de notes.
- Distingue faits, hypothèses, décisions, questions ouvertes et actions explicitement validées. Ne copie jamais de secrets, clés, mots de passe ou identifiants.

## Première utilisation : initialiser sans imposer

Si le vault est identifié mais qu'il ne possède aucune zone consacrée au projet courant :

1. Utilise le nom clair du dossier de travail ou du projet. Ne pose une question que si aucun nom utilisable n'est disponible.
2. Crée un dossier léger pour ce projet, à un emplacement cohérent avec les conventions du vault. Si aucune convention n'est visible, crée-le à la racine du vault.
3. Crée uniquement les notes rendues utiles par la session :
   - `Vue d'ensemble` : objectif, périmètre connu, état actuel et liens vers les notes créées ;
   - `Journal` : première entrée datée qui résume cette session ;
   - `Décisions` : uniquement si la session comporte une décision durable.
4. Ajoute un lien depuis l'index du vault seulement si un index existe et sert déjà à référencer les projets. Ne fabrique pas de page d'accueil ou de taxonomie vide.

Cette structure est un point de départ stable, pas une norme. Même si le projet n'est qu'à 1 %, elle donne une adresse durable à la mémoire sans promettre de futurs dossiers.

## Faire évoluer la structure sans perdre l'utilisateur

À chaque `/maj`, utilise d'abord les notes fondatrices comme repères. Ajoute une note spécialisée uniquement lorsqu'elle contient déjà un contenu concret et récurrent ou qu'elle évite de surcharger durablement une note existante. Exemples possibles selon le projet : `Recherche`, `Livrables`, `Documentation`, `Clients`, `Réunions`, `Architecture`, `Sources`.

Quand une note spécialisée est créée, ajoute son lien à `Vue d'ensemble` et explique son rôle en une ligne. Ne déplace ni ne renomme les notes existantes ; ne change pas la taxonomie de base au gré des sessions. Une amélioration future se fait par ajout progressif et conservation des liens, jamais par surprise.

## Prendre en compte `/maj-analyse`

Avant la mise à jour normale, cherche uniquement le bilan le plus récent `Analyse de mémoire` de cette zone projet, s'il existe. Lis ses recommandations sans relancer d'audit.

- Applique les éléments de `À appliquer par /maj` qui sont encore justifiés, locaux et non destructifs : compléter un lien manquant, actualiser une vue d'ensemble, créer une note déjà nécessaire ou préciser une information établie.
- Applique uniquement les recommandations au statut `approuvée` ou `proposée` lorsque leur niveau d'impact est local et non destructif. Vérifie d'abord que les notes concernées correspondent encore au constat ; sinon marque la recommandation `obsolète`.
- Marque ces éléments comme `appliquée`, avec la date, seulement après vérification effective du résultat, afin qu'ils ne soient pas rejoués.
- N'applique jamais automatiquement une fusion, un déplacement, un renommage, une suppression ou une refonte de structure. Ces éléments doivent rester dans `Décisions à valider` jusqu'à ce que l'utilisateur les confirme explicitement dans la commande `/maj`.
- Si l'utilisateur confirme une recommandation, réalise seulement le changement explicitement approuvé et conserve une trace de la décision.

## Mises à jour suivantes

1. Ajoute une entrée datée, concise et factuelle au journal ou changelog existant.
2. Mets à jour les seules notes touchées par les nouveaux faits : vue d'ensemble, documentation, recherche, livrable, état, tâches ou décisions.
3. Lorsqu'une décision durable est prise, indique le choix, son motif et ses conséquences connues. Utilise le registre de décisions existant ; crée-le seulement si nécessaire.
4. Si un fait nouveau remplace une décision ou un état, actualise la synthèse et conserve une trace concise de l'évolution. N'efface pas silencieusement l'information antérieure.
5. Actualise les liens internes qui deviennent nécessaires entre les notes créées ou mises à jour, sans créer un réseau de liens décoratif.

## Efficacité et rapport

Cette commande est une mise à jour incrémentale, jamais un audit du vault. N'explore pas l'ensemble du vault et ne réanalyse pas largement le projet pour reconstruire ce que la session a déjà établi. Lis seulement le minimum nécessaire pour choisir et modifier les bonnes notes.

Termine par un rapport court, en liste : emplacement mis à jour, notes créées ou modifiées, et éventuels éléments à confirmer. Si aucun fait utile ne justifie une mise à jour, indique-le au lieu de créer du contenu vide.
