# Comprendre Scroll zkVM

Scroll regroupe des blocs L2 et prouve leur exécution sans la refaire sur Ethereum.
Ce dépôt contient les programmes invités OpenVM qui matérialisent ce pipeline de preuve.
La première couche traite un chunk de blocs et produit un résumé public vérifiable.
La deuxième agrège plusieurs chunks dans un batch en contrôlant leur continuité.
La troisième agrège plusieurs batches dans un bundle destiné à la finalisation L1.
Les preuves intermédiaires sont des STARK ; la sortie finale peut être enveloppée en SNARK.
Le code sépare les témoins privés, les entrées publiques et les engagements de programme.
Cette séparation empêche une preuve valide pour un autre circuit d’être acceptée par erreur.
Le parcours suit les structures et validations réellement présentes dans le dépôt.

Suite : [architecture en trois niveaux](02-architecture-trois-niveaux.md).
