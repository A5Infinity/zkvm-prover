# Engagements de programme et versions

Une preuve correcte ne suffit pas : elle doit provenir du circuit précisément attendu.
Le dépôt représente cette identité par deux engagements, `exe` et `vm`.
`exe` engage l’exécutable invité tandis que `vm` engage sa configuration OpenVM.
Batch compare ces valeurs aux engagements générés du circuit chunk.
Bundle les compare à ceux du circuit batch.
Le vérifieur final reçoit également la clé sérialisée correspondant à ces engagements.
Les versions encodent le domaine, le fork et la version de transition d’état.
Galileo ajoute explicitement l’octet de version à plusieurs entrées publiques.
Cette discipline rend les changements de circuit visibles dans les valeurs vérifiées.

Suite : [du STARK au SNARK](08-stark-snark-recursion.md).
