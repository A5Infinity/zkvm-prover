# Batch, blobs et preuve KZG

Le circuit batch reçoit les résumés publics des chunks et leurs preuves agrégées.
Il compare leurs engagements VM et EXE aux constantes du programme enfant attendu.
Les entrées publiques des chunks sont hachées puis rapprochées des preuves fournies.
Le builder V7 vérifie aussi que les données du batch correspondent au blob déclaré.
Il évalue le polynôme du blob au défi dérivé de son enveloppe.
La preuve KZG confirme cette évaluation sans révéler ni retraiter tout le polynôme.
L’engagement KZG compressé doit produire le même versioned hash que l’en-tête on-chain.
Le payload contrôle ensuite l’ordre et la continuité des chunks du batch.
Le résultat retient les racines extrêmes, le batch hash et la file de messages finale.

Suite : [bundle et finalisation](06-bundle-finalisation.md).
