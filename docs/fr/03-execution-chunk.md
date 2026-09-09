# Exécuter et prouver un chunk

`ChunkWitness` apporte les blocs, le fork actif et l’état nécessaire à leur exécution.
`execute` construit la spécification de chaîne correspondant au fork Scroll demandé.
Le vérifieur SBV rejoue les blocs et retourne les racines d’état avant et après exécution.
Il calcule aussi la racine de retraits qui sera propagée jusqu’au bundle final.
Les octets des transactions L2 sont condensés dans `tx_data_digest`.
Depuis EuclidV2, une empreinte roulante relie également la file des messages L1.
Les contextes de blocs publient timestamp, base fee, limite de gas et nombres de transactions.
Pour le domaine Validium, le témoin produit en plus une clé publique de chiffrement.
Le circuit refuse un témoin dont la version ne correspond pas au fork annoncé.

Suite : [entrées publiques et continuité](04-entrees-publiques-continuite.md).
