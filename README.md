# CadenceDCA

CadenceDCA simule l'évolution d'une épargne entre deux dates : un versement de départ, des versements réguliers (DCA, « investissement programmé »), un rendement annuel et des intérêts composés. Il calcule les gains nominaux, puis les gains réels après l'inflation que vous saisissez.

## Ouvrir la page

1. Téléchargez puis ouvrez le fichier `CadenceDCA.html` dans votre navigateur (double-clic, ou glisser-déposer dans une fenêtre du navigateur).
2. Saisissez les dates, les montants, la fréquence des versements, le rendement et l'inflation. Les résultats, le graphique et le tableau année par année se mettent à jour.
3. Deux boutons, au-dessus du tableau, enregistrent la simulation : « Exporter en CSV » et « Exporter en Excel » (voir « Exporter la simulation » ci-dessous).
4. La page s'ouvre en mode sombre. Le bouton en haut de la page indique le mode vers lequel il bascule : « Mode clair » en mode sombre, « Mode sombre » en mode clair. Ce choix n'est pas mémorisé : chaque ouverture repart en sombre. L'impression se fait toujours en couleurs claires.

Aucune installation n'est nécessaire.

## Profils préremplis et inflation Insee

- **Profils préremplis.** Sous le rendement, trois boutons remplissent un taux de départ sourcé :
  - Prudent, 1,7 % : le taux du Livret A depuis le 1er août 2026 ;
  - Modéré, 2,63 % : le rendement moyen des fonds en euros en 2025 (ACPR) ;
  - Dynamique, 5 % : une hypothèse prudente pour des actions, sous leur rendement historique (AMF).

  Ce sont des hypothèses constantes, pas des prévisions : c'est une simulation, pas un conseil.
- **Bouton « Inflation INSEE ».**
  - Si la période est passée et couverte par la série intégrée (de 1999 à 2025, en moyennes annuelles), il remplit une approximation de l'inflation cumulée, en mode « Cumul sur la période » : elle va de la moyenne annuelle de l'année de départ à celle de l'année de fin, sans tenir compte des mois.
  - Sinon, il propose la moyenne annuelle des 10 ou des 20 dernières années. C'est l'inflation passée, pas une prévision.
  - La série est intégrée à la page : aucune connexion n'est nécessaire.
- **Sources.** La section « Sources des données », en bas de la page, cite chaque source avec sa date. Elle est repliée par défaut, comme « À quoi sert CadenceDCA ? » : le bouton « Déployer » (souris, ou touche Entrée ou Espace) l'ouvre, « Replier » la referme. À l'impression, les deux sections sont imprimées en entier.

## Fourchette de résultats (Monte-Carlo)

- **Pourquoi.** Le rendement saisi est une moyenne : en réalité, les marchés montent plus certaines années et baissent d'autres. La fourchette montre l'éventail des valeurs finales probables.
- **Interrupteur.** Sous le rendement, cochez « Afficher une fourchette (Monte-Carlo) » (souris, ou touche Espace). CadenceDCA tire alors 1 000 suites de rendements annuels autour du rendement saisi ; les tirages sont toujours les mêmes pour les mêmes paramètres.
- **Profils de la fourchette.** Trois boutons remplissent le rendement moyen et la volatilité (l'écart habituel du rendement d'une année autour de sa moyenne). Attention : ils remplacent aussi le rendement annuel saisi plus haut ; le changement est indiqué sous les boutons.
  - Obligataire : 2,5 % par an, volatilité 4 % ;
  - Équilibré : 4 % par an, volatilité 9 % ;
  - Actions monde : 5 % par an, volatilité 16 %.

  Ce sont des hypothèses de CadenceDCA, situées dans les classes de risque officielles des fonds (sources et dates dans « Sources des données ») ; vous pouvez aussi saisir la volatilité. À 0 %, la fourchette se confond avec la courbe.
- **Résultats.** La carte « Fourchette de résultats » donne une valeur pessimiste (10e centile : 1 tirage sur 10 fait moins bien), la médiane (la moitié des tirages fait mieux) et une valeur optimiste (90e centile), en euros courants et en euros de la date de départ, après frais et nets d'impôt si vous en avez saisi ; elle indique aussi la part des tirages qui finissent sous le total versé. Sur le graphique, la zone grisée bornée de pointillés va, à chaque date, du 10e au 90e centile des valeurs simulées à cette date ; la médiane est en trait mixte. Ce ne sont pas des bornes : une même trajectoire peut sortir de la zone puis y revenir, et les marchés réels peuvent faire mieux ou pire. Avec 1 000 tirages, les centiles sont des estimations : leurs derniers chiffres ne sont pas significatifs. En comparaison A/B, la fourchette porte sur le scénario A seulement.
- **Exports.** Fourchette affichée, le CSV ajoute une section « Fourchette Monte-Carlo » (paramètres, centiles à la date de fin et année par année) et le fichier Excel une feuille « Fourchette ». Décochez l'interrupteur : la page et les exports redeviennent exactement ceux d'avant.
- Simulation, pas un conseil ; les performances passées ne préjugent pas des performances futures.

## Frais et fiscalité

- **Frais.** Dans « Frais & fiscalité », saisissez les frais d'entrée (pourcentage retenu sur chaque versement) et les frais de gestion annuels (pourcentage de l'encours, prélevé chaque mois au douzième). Par défaut, ils valent 0 %.
- **Enveloppe.** Choisissez « Aucune fiscalité (brut) » (par défaut), PEA, compte-titres (PFU), assurance-vie ou « Exonéré » (Livret A, LDDS). L'impôt est calculé sur la plus-value (valeur après frais moins vos versements), comme si vous retiriez tout à la date de fin :
  - compte-titres : 12,8 % d'impôt et 18,6 % de prélèvements sociaux ;
  - PEA : avant 5 ans, 12,8 % et 18,6 % ; après 5 ans, 18,6 % de prélèvements sociaux seulement ; un message signale des versements au-delà du plafond de 150 000 € ;
  - assurance-vie : avant 8 ans, 12,8 % ; après 8 ans, abattement de 4 600 € (personne seule) ou 9 200 € (couple, à choisir), puis 7,5 % jusqu'à 150 000 € de versements et 12,8 % au-delà ; ce seuil se compare aux primes versées au 31 décembre de l'année qui précède la date de fin : cette date d'arrêté et le montant des primes à cette date sont affichés dans la carte « Frais et fiscalité » et repris dans les exports CSV et Excel (« Primes arrêtées au (assurance-vie) », « Primes à cette date (€) ») ; 17,2 % de prélèvements sociaux ;
  - exonéré : aucun impôt ; un message rappelle les plafonds (Livret A 22 950 €, LDDS 12 000 €).
- **Taux.** Les taux ont été vérifiés le 25/11/2026 sur les sites officiels (Service-Public.fr, impots.gouv.fr, BOFiP) ; chacun est cité avec sa date dans « Sources des données ». Vous pouvez les modifier dans « Taux fiscaux utilisés », et revenir aux taux vérifiés par un bouton.
- **Résultats.** La carte « Frais et fiscalité » donne, en euros courants et en euros de la date de départ : la valeur brute, le coût des frais (intérêts perdus compris), la valeur après frais, l'impôt, les prélèvements sociaux, la valeur nette et le gain net. Le tableau année par année ajoute « Frais cumulés » et « Valeur après frais » dès que des frais sont saisis.
- C'est une **estimation simplifiée** : votre situation personnelle (autres contrats, retraits passés, option pour le barème, exonérations) n'est pas prise en compte. Simulation, pas un conseil.

## Comparer deux scénarios (A/B)

- **Interrupteur.** En bas des paramètres, cochez « Comparer avec un scénario B » (souris, ou touche Espace au clavier). Le scénario A, ce sont vos paramètres ; le scénario B en est d'abord une copie : changez-y un ou plusieurs paramètres (versements, fréquence, rendement, frais, enveloppe). Les dates, l'inflation, l'abattement de l'assurance-vie et les taux fiscaux sont communs aux deux. « Recopier A dans B » refait la copie.
- **Raccourcis.**
  - « DCA ou versement unique » : B place en une fois, au départ, le même total que celui versé par A ;
  - « Frais 0,2 % ou 1,5 % » : frais de gestion annuels de 0,2 % pour A et 1,5 % pour B ;
  - « Rendement 5 % ou 7 % » : 5 % pour A, 7 % pour B.

  Les deux derniers modifient aussi A ; un message le rappelle, effacé dès que vous changez ensuite un paramètre.
- **Assurance-vie.** Si A ou B est en assurance-vie, le choix de l'abattement (personne seule ou couple) s'affiche ; il vaut pour les deux scénarios.
- **Avertissements de B.** Si les versements de B dépassent le plafond de son enveloppe (PEA, Livret A, LDDS), ou si B n'a pas de plus-value, l'avertissement s'affiche dans la carte « Comparaison A/B », précédé de « Scénario B : », et figure dans les exports.
- **Résultats.** La carte « Comparaison A/B » donne, pour A, pour B et pour l'écart B − A (toujours signé, « + » quand B est plus élevé) : total versé, valeur finale nominale et réelle, valeur après frais, valeur nette d'impôt, frais cumulés et gain net. L'écart est la différence des deux montants affichés, au centime près. Sur le graphique, B est tracé en orange, en tirets longs (valeur nominale) et en pointillés (valeur réelle), avec des marqueurs carrés ; en comparaison, A et B y sont montrés après frais, avant impôt. Le tableau année par année reste celui de A.
- **Exports.** En comparaison, le CSV ajoute une section « Comparaison A/B » et le tableau année par année de B ; le fichier Excel ajoute les feuilles « Scénario B » et « Comparaison A-B ». Décochez l'interrupteur : la page et les exports redeviennent exactement ceux du seul scénario A.

## Exporter la simulation

Les deux exports reprennent la saisie en cours, même si vous cliquez juste après avoir changé un paramètre. Si une saisie est invalide, les boutons sont désactivés et aucun fichier n'est créé.

- **CSV** : fichier `CadenceDCA-simulation-AAAAMMJJ.csv` (séparateur point-virgule), avec les paramètres, le tableau année par année et les totaux, y compris les frais, l'enveloppe, les taux fiscaux utilisés et les résultats nets d'impôt.
- **Excel** : fichier `CadenceDCA-simulation-AAAAMMJJ.xlsx`, qui s'ouvre dans Excel, LibreOffice Calc et Google Sheets. Il contient deux feuilles :
  - « Simulation » : le tableau année par année, avec les mêmes colonnes que le CSV ; les montants sont de vrais nombres, au format euros, utilisables dans des formules ;
  - « Paramètres » : les paramètres saisis, l'inflation utilisée (taux annuel moyen et cumul, en pourcentages) et sa source (série Insee si elle vient du bouton « Inflation INSEE », sinon votre saisie), les résultats, les frais et la fiscalité (taux, sources, résultats nets), la version de CadenceDCA et l'avertissement « Simulation, pas un conseil ».

Le fichier Excel est fabriqué dans votre navigateur : rien n'est envoyé sur Internet.

## Hors ligne

La page fonctionne entièrement hors ligne. Elle n'appelle aucun service, ne charge aucune ressource externe et n'envoie aucune donnée : tout le calcul se fait dans votre navigateur.

## Auteurs

Créé par Jean Augeraud et AgoraMesh-MD.

## Licence

Copyright (c) 2026 Jean Augeraud et AgoraMesh-MD.

Licence : PolyForm Noncommercial 1.0.0 (voir `LICENSE`, à la racine du dépôt). Usage commercial sur autorisation écrite de Jean Augeraud.

Les composants tiers (palette Sanzo Wada n° 340 et ses données de couleurs, sous licence MIT) et leurs avis sont indiqués dans `NOTICE-TIERS.md`, à la racine du dépôt.

## En savoir plus

Ce que permet l'outil, comment lire ses résultats et ses limites : voir `note-explicative.md`. Le même texte figure en bas de la page.

## Version

Version actuelle : 0.3.0. Détail : `CadenceDCA-0.3.0.md` ; versions précédentes : `CadenceDCA-0.2.1.md`, `CadenceDCA-0.2.0.md`.
