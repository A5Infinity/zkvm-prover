# Bundle et finalisation sur Ethereum

Le bundle est la dernière couche d’agrégation du pipeline Scroll zkVM.
Son témoin contient plusieurs `BatchInfo` accompagnés de leurs preuves.
Le circuit contrôle les engagements du programme batch avant toute agrégation.
Il impose la continuité des racines d’état, des batch hashes et des messages L1.
`BundleInfo` résume l’état précédemment finalisé et l’état final proposé.
Il publie aussi le nombre de batches, la racine de retraits et le dernier batch hash.
Contrairement aux niveaux inférieurs, le bundle n’a aucun parent qui l’agrège encore.
Sa preuve peut donc être enveloppée pour une vérification économique dans l’EVM.
Une acceptation on-chain finalise les valeurs publiques liées par cette preuve.

Suite : [engagements des programmes](07-engagements-et-versions.md).
