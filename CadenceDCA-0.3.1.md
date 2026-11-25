# CadenceDCA 0.3.1

- **Date :** 2026-11-25
- **Type :** version corrective de la 0.3.0, sans changement de calcul.
- **Fichier livré :** `CadenceDCA.html`, page unique, 100 % hors ligne.
- **SHA-256 de la page :** `14a4771fc8123fc01d88855ae0052d72c395ad09fcd82eee3089f58168d8709f` (196 059 octets)
- **Auteurs :** Jean Augeraud et AgoraMesh-MD. **Licence :** PolyForm Noncommercial 1.0.0 (voir `LICENSE`).

## Corrections
- **Recherche dans les sections repliées :** la recherche du navigateur (Ctrl+F) trouve le texte de « À quoi sert CadenceDCA ? » et de « Sources des données » même repliées, et ouvre la section concernée ; le bouton passe alors à « Replier ». Dans les navigateurs qui ne le permettent pas, la page se comporte comme en 0.3.0.
- **Liens vers une section :** un lien vers un passage d'une section repliée l'ouvre ; ce comportement est désormais contrôlé automatiquement.

## Moteur de calcul et exports
Inchangés. L'affichage est identique à la 0.3.0, et le CSV identique à l'octet. Le fichier Excel ne change que par le numéro de version (« CadenceDCA 0.3.1 »). Cas de référence : 17 128,10 € de valeur finale et 2 155,49 € de gain réel.

## Revues
Correctif écrit par Dev, relu par Audit (Codex), Graphiste (Gemini) et Revue-Fable (Claude Fable 5.2) : GO sans réserve des trois.

## Tests
`verifier.mjs` : code 0 sous Chromium, avec 130/130 tests Node, 6/6 mentions et 106/106 contrôles navigateur (dont la recherche dans une section repliée et l'ouverture par un lien).

## Limites connues
- Mêmes limites que la 0.3.0 (voir `CadenceDCA-0.3.0.md`).
- Ouverture par la recherche vérifiée sous Chromium ; Firefox et Safari non essayés.
