# Entrées publiques et continuité

Une preuve n’est utile que si son résultat public est relié au bon état de chaîne.
`ChunkInfo` publie notamment chain ID, racines d’état, retraits et empreintes de données.
Son encodage change selon EuclidV1, EuclidV2, Feynman, Galileo ou Validium.
Entre deux chunks, le code exige le même chain ID.
La racine initiale du nouveau chunk doit égaler la racine finale du précédent.
La file de messages L1 est chaînée de la même manière à partir d’EuclidV2.
En Validium, les blockhashes et la clé de chiffrement doivent aussi rester cohérents.
Ces assertions empêchent d’agréger des segments valides mais sans lien entre eux.
Le hash des entrées publiques devient l’interface cryptographique entre les niveaux.

Suite : [agrégation des batches](05-batch-kzg-donnees.md).
