# Scénarios de validation bêta

Ces scénarios sont à exécuter dans un faux vault isolé ; ils ne constituent pas des tests automatiques du comportement d'un modèle.

1. Projet vide : le premier `/maj` crée uniquement l'index, le journal et une décision si nécessaire.
2. Vault existant dans une autre langue : les noms, chemins et métadonnées existants sont conservés.
3. Deux `/maj` identiques : le second ne modifie aucun fichier.
4. Une session touchant plus de trois notes : toutes les notes concernées sont mises à jour de façon ciblée.
5. Une recommandation refusée et commentée : une nouvelle analyse la conserve sans la recréer.
6. Une recommandation dont les notes ont changé : `/maj` la marque obsolète et ne l'applique pas.
7. Une fusion ou un déplacement : aucune action sans approbation explicite.
8. Plusieurs projets dans un vault : aucune note d'un autre projet n'est modifiée ou signalée comme anomalie.
