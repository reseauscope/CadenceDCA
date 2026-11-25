# CadenceDCA 0.3.0

- **Date :** 2026-11-25
- **Type :** version de fonctionnalités.
- **Fichier livré :** `CadenceDCA.html`, page unique, 100 % hors ligne.
- **SHA-256 de la page :** `a94fbc4e55f9fc0fc0932bbb142e28a49aad495aada9665af3c81300c99e731a` (195 186 octets)
- **Auteurs :** Jean Augeraud et AgoraMesh-MD. **Licence :** PolyForm Noncommercial 1.0.0 (voir `LICENSE`).

## Nouveautés
- **Inflation Insee et profils préremplis :** un bouton remplit l'inflation à partir de la série Insee intégrée (1999 à 2025) ; trois profils de rendement sourcés (Livret A, fonds en euros, actions).
- **Export Excel :** en plus du CSV, un fichier `.xlsx` avec les feuilles « Simulation » et « Paramètres », aux montants utilisables dans des formules.
- **Frais et fiscalité :** frais d'entrée et de gestion ; enveloppes PEA, compte-titres, assurance-vie et livrets exonérés, avec les taux vérifiés le 25/11/2026 et modifiables. C'est une estimation simplifiée.
- **Comparaison de deux scénarios (A/B) :** un scénario B, des raccourcis (DCA ou versement unique, frais, rendement), une carte des écarts, B sur le graphique et dans les exports.
- **Fourchette de résultats (Monte-Carlo) :** 1 000 tirages à graine fixe, trois profils de volatilité sourcés, 10e centile, médiane et 90e centile, bande sur le graphique et dans les exports. Simulation, pas un conseil ; les performances passées ne préjugent pas des performances futures.
- **Bas de page :** les sections « À quoi sert CadenceDCA ? » et « Sources des données » sont repliées par défaut, avec un bouton « Déployer » / « Replier » ; elles s'impriment en entier.
- **Note :** « export CSV et Excel » et « frais et fiscalité simplifiés ».

## Moteur de calcul
Sans frais ni fiscalité, les résultats sont inchangés. Les cas de référence restent les mêmes : 17 128,10 € de valeur finale et 2 155,49 € de gain réel.

## Revues
Chaque lot a été écrit par Dev puis relu par trois relecteurs indépendants, avec contre-vérification de chaque correction : Audit (Codex), Graphiste (Gemini) et Revue-Fable (Claude Fable 5.2). Chaque lot n'a été validé qu'avec un GO sans réserve des trois.

## Tests
- 130 tests unitaires Node, dont des références de calcul indépendantes en Python.
- `verifier.mjs` : code 0 sous Chromium, avec 130/130 tests Node, 6/6 mentions et 104/104 contrôles navigateur (calculs, exports CSV et Excel relus, contrastes en clair et en sombre, absence de défilement horizontal à 320 px, accessibilité au clavier, performance).

## Limites connues
- Vérifié sous Chromium uniquement.
- Fiscalité simplifiée : la situation personnelle (autres contrats, retraits passés, option pour le barème) n'est pas prise en compte.
- Import d'une série d'indice en CSV : abandonné pour cette version (non simple, et risque d'importer des données sous licence).
- La recherche du navigateur peut ne pas trouver le texte d'une section repliée : déployez-la d'abord.
