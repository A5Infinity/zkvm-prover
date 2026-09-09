# Du STARK récursif au SNARK EVM

Le prover exécute toujours le programme invité avant de générer sa preuve.
Cette pré-exécution mesure les cycles et détecte une entrée invalide avant le calcul coûteux.
`gen_proof_stark` produit une preuve OpenVM et ses preuves de valeurs publiques.
Il sérialise aussi la baseline et les éventuelles preuves Merkle de calcul différé.
Les circuits d’agrégation utilisent ce mécanisme différé pour vérifier leurs enfants.
Un arbre d’agrégation combine les feuilles par groupes configurés dans le prover.
La preuve racine reste efficace à composer dans les niveaux batch puis bundle.
`gen_proof_snark` enveloppe finalement l’exécution pour une vérification dans l’EVM.
Le choix combine la récursion STARK hors chaîne et un coût on-chain maîtrisé.

Suite : [vérification finale](09-verification-evm.md).
