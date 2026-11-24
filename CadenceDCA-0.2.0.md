# CadenceDCA 0.2.0

- **Date :** 2026-11-24
- **Fichier livré :** `CadenceDCA.html`, une seule page, 100 % hors ligne, sans bibliothèque ni requête réseau.
- **SHA-256 de la page :** `7751a48fae1978fcb43bb9d5f886f9c210658b0dc4b95c063f7cf0c565f096c8` (58 026 octets)
- **Auteurs :** Jean Augeraud et AgoraMesh-MD.
- **Licence :** PolyForm Noncommercial 1.0.0 (voir `LICENSE`). L'usage commercial demande l'autorisation écrite de Jean Augeraud. Avis de tiers : `NOTICE-TIERS.md`.

## Contenu
- Simulation d'une épargne entre deux dates : un versement initial, puis des versements réguliers (DCA), mensuels, trimestriels, annuels ou hebdomadaires.
- Intérêts composés calculés au mois, à un rendement annuel constant.
- Inflation, saisie en taux annuel moyen ou en cumul sur la période. Le gain réel est exprimé en euros constants de la date de départ.
- Indicateurs : total versé, valeur finale, gain nominal, inflation cumulée, gain réel. Un avertissement s'affiche quand l'inflation dépasse le rendement.
- Graphique de l'évolution (versé, nominal, réel), utilisable au clavier.
- Tableau année par année et export CSV.
- Note explicative en bas de page.
- Interface « Terminal Cyber-Émeraude » (palette Sanzo Wada n° 340) :
  - mode sombre par défaut, avec un bouton pour passer en mode clair ;
  - mise en page adaptée du téléphone (360 px) au grand écran (1920 px) ;
  - impression propre.
- Logo « Onde composée » (n° 05-B) et favicon intégrés dans la page.

## Décisions marquantes
| N° | Objet |
|---|---|
| 003 | Palette Sanzo Wada n° 340 « Terminal Cyber-Émeraude », contraste AA (4,5:1) pour le texte |
| 005 | Licence PolyForm Noncommercial 1.0.0 |
| 006 | Nom CadenceDCA, page renommée `CadenceDCA.html` |
| 007 | Dépôt public reseauscope/CadenceDCA, livrables seuls |
| 008 | Mode sombre par défaut |
| 009 | Auditeurs de remplacement (Gemini, Fable) pendant l'indisponibilité de Codex |
| 010 | Logo n° 05-B |

## Revues passées
- **Codex (auditeur, autre fournisseur) :**
  - GO sur L1 à L4 (moteur, interface, graphique, export) ;
  - GO sur L5 v3 (refonte graphique, contrastes sur fonds composés) ;
  - GO sur L6.0 (script de vérification).
- **DeepSeek (second auditeur ponctuel) :** revue L1 à L5, constats repris par Codex.
- **Gemini (auditeur de remplacement) :** GO sur L5.1 (nom, licence, auteurs, renommage, mode sombre par défaut).
- **Claude Fable 5.2 (relecteur indépendant) :**
  - L5.1 : GO après corrections, avec la réserve R1 (3 couleurs hors palette), levée dans L5.2 ;
  - L5.2 (couleurs, alignement dark-first, dégradé sous la courbe réelle, logo) : GO sans réserve bloquante ; courbes ≥ 4,78:1 sur fonds composés, texte ≥ 4,98:1.

## Tests
- 25 tests unitaires Node : moteur de calcul, cas de référence et export. Par exemple, 1 000 € puis 100 €/mois sur 10 ans à 5 % donnent 17 128,10 €, soit un gain réel de 2 155,49 € avec 2 % d'inflation.
- Script unique `verifier.mjs`, dans Chromium hors ligne, à 360, 768, 1280 et 1920 px, en clair et en sombre. Il vérifie :
  - qu'aucune requête ne sort de la page, et que la console reste vide ;
  - l'absence de défilement horizontal ;
  - le contraste AA ;
  - l'export ;
  - les mentions d'auteur et de licence ;
  - le thème.
- Résultat sur la version livrée : code 0, 25/25 tests Node, 6/6 mentions, 24/24 contrôles navigateur (Chromium).

## Limites connues
- Le rendement est supposé constant. Ni les frais, ni la fiscalité (flat tax, PEA, assurance-vie), ni les prélèvements sociaux ne sont déduits.
- La durée se compte en mois entiers. Les versements hebdomadaires sont lissés à 52/12 par mois.
- Le choix du thème n'est pas mémorisé d'une ouverture à l'autre.
- Testé sous Chromium ; Firefox et Safari non vérifiés (le dégradé du graphique utilise des variables CSS dans le SVG).
- C'est une simulation, pas un conseil en investissement.

## Prochaines versions
- **0.3.0 et suivantes :**
  - L6.1 : inflation INSEE et préréglages ;
  - L6.2 : frais et fiscalité ;
  - L6.3 : comparaison A/B ;
  - L6.4 : fourchette de résultats Monte-Carlo, par profils.
- **V2 :** objectif inversé, sauvegarde locale, phase de rente.
