# Limites et pistes de vérification

Ce parcours décrit le pipeline Scroll zkVM présent dans ce dépôt au moment de l’analyse.
Il ne constitue ni une preuve de sécurité indépendante ni un audit cryptographique.
Les détails internes d’OpenVM, de SBV, de Halo2 et des courbes restent hors périmètre.
Les paramètres de sécurité dépendent aussi des versions exactes de ces dépendances.
Les engagements générés doivent être régénérés lorsque les programmes invités changent.
Les chemins de release et le fichier `release-fork` participent à cette traçabilité.
Aucune installation, compilation ou exécution n’a été effectuée pour ce parcours.
Pour vérifier le comportement, consulter les tests de `crates/integration/tests`.
Les cibles `test-single-chunk`, `test-e2e-batch` et `test-e2e-bundle` documentent les chemins prévus.

Retour au [sommaire](README.md).
