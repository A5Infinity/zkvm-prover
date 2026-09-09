# Vérifier les preuves et leurs engagements

`UniversalVerifier` charge la clé STARK d’agrégation et le bytecode du vérifieur EVM.
Pour une preuve STARK, il décode la baseline et les valeurs publiques authentifiées.
Il compare l’engagement EXE attendu à celui contenu dans la baseline.
Le SDK OpenVM contrôle ensuite la preuve complète avec la clé d’agrégation.
Pour une preuve EVM, les engagements EXE et VM sont tous deux comparés explicitement.
Le bytecode de vérification exécute enfin le contrôle cryptographique du SNARK.
Une preuve produite par un autre programme ou une autre VM est donc rejetée.
Les tests d’intégration conservent des exemples chunk, batch et bundle par fork.
Ils montrent où vérifier le chemin complet jusqu’au contrat Solidity.

Suite : [limites et vérification](10-limites-et-verification.md).
