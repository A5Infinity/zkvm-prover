# Une architecture en trois niveaux

Le workspace Rust distingue les circuits chunk, batch et bundle dans des crates séparées.
Le chunk exécute les blocs à partir d’un témoin et calcule un [1mrésumé d’état[0m public.
Le batch vérifie récursivement les preuves de chunks et reconstruit leur résultat global.
Le bundle fait la même opération au-dessus des preuves de batches.
Chaque niveau implémente le trait `Circuit` avec son type de témoin et ses entrées publiques.
Batch et bundle implémentent aussi `AggCircuit` pour vérifier des preuves enfants.
Les types communs vivent dans `crates/types`, séparés du moteur de preuve.
Le prover générique charge un exécutable OpenVM et sa configuration sans connaître le métier.
Le vérifieur sait ensuite contrôler une preuve STARK ou son enveloppe EVM.

Suite : [exécution d’un chunk](03-execution-chunk.md).
