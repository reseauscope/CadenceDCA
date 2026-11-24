# CadenceDCA 0.2.1

- **Date :** 2026-11-24
- **Type :** version corrective de la 0.2.0, sans nouvelle fonctionnalité de calcul.
- **Fichier livré :** `CadenceDCA.html`, page unique, 100 % hors ligne.
- **SHA-256 de la page :** `05d7ce98181f459aad503b677d90691d1725f118aed7c72ee34189518c0080f1` (58 696 octets)
- **Auteurs :** Jean Augeraud et AgoraMesh-MD. **Licence :** PolyForm Noncommercial 1.0.0 (voir `LICENSE`).

## Corrections
- **Bouton de thème :** il indique l'action, « Mode clair » en sombre et « Mode sombre » en clair, et son nom accessible suit ce libellé (décision 008, avenant 1).
- **Note « À quoi sert CadenceDCA ? » :** remplacée par la version courte de Jean.
- **Typographie :** espaces insécables entre les nombres et « € » ou « % », pour que l'unité ne se retrouve plus seule en début de ligne.
- **Panneau Paramètres :** il défile normalement avec la page, il n'est plus collant.
- **Tableau annuel :**
  - plus de défilement horizontal inutile sur ordinateur ;
  - sur téléphone, une mention indique qu'on peut le faire glisser.
  - avec les valeurs par défaut, les dix lignes et l'en-tête sont entièrement visibles.
- **Formulaire :** « Versement régulier » et « Fréquence » sont alignés.
- **Export :** le fichier s'appelle `CadenceDCA-simulation-AAAAMMJJ.csv`.

## Moteur de calcul
Inchangé, identique octet pour octet à la 0.2.0. Les cas de référence restent les mêmes : 17 128,10 € de valeur finale et 2 155,49 € de gain réel.

## Revues
- Correctif écrit par Dev.
- Relecture par Revue-Fable (Claude Fable 5.2, relecteur indépendant, décision 009) : GO après correction de C1 (dernière ligne du tableau masquée), puis GO final après contre-vérification.

## Tests
- 25 tests unitaires Node, inchangés.
- `verifier.mjs` : code 0 sous Chromium, avec 25/25 tests Node, 6/6 mentions et 31/31 contrôles navigateur. Contrôles ajoutés : libellé du bouton, espaces dans la note, alignement des champs, tableau sans défilement, panneau non collant, nom du fichier exporté, dernière ligne du tableau entièrement visible.

## Limites connues
- Mêmes limites que la 0.2.0 (voir `CadenceDCA-0.2.0.md`).
- Vérifié sous Chromium uniquement. L'alignement des champs repose sur la sous-grille CSS (navigateurs récents) ; ailleurs, un léger décalage peut subsister.
- Si l'on saisit un rendement de -100 % ou moins, les messages d'erreur gardent une espace ordinaire avant « % ».

## Prochaine version (0.3.0)
- L6.1 : inflation INSEE et profils préremplis.
- L6.1b : export Excel (.xlsx).
- Puis frais et fiscalité, comparaison A/B, Monte-Carlo.
