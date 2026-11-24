# À quoi sert ce simulateur

**Ce que fait l'outil.** Il calcule ce que devient une épargne placée entre deux dates : un versement de départ, puis des versements réguliers (c'est le DCA, « investissement programmé »), qui rapportent chaque mois des intérêts eux-mêmes réinvestis (intérêts composés). Il retire ensuite l'effet de l'inflation pour montrer ce que vaut réellement cette épargne.

**Comment lire les résultats.**
- Le **gain nominal** est la différence entre la valeur finale et ce que vous avez versé, en euros courants.
- Le **gain réel** fait la même différence en pouvoir d'achat, exprimé en euros de la date de départ. Exemple : 1 000 € au départ puis 100 € par mois pendant 10 ans à 5 % par an donnent 17 128,10 €, soit 4 128,10 € de gain nominal. Avec 2 % d'inflation par an, le gain réel n'est plus que de 2 155,49 €.
- Si l'inflation dépasse le rendement, le gain réel devient négatif : la page vous prévient.

**Ce que vous pouvez faire avec.**
- Comparer des durées, des montants mensuels ou des fréquences de versement.
- Mesurer l'effet d'un point de rendement en plus ou en moins sur 10, 20 ou 30 ans.
- Saisir l'inflation en taux annuel moyen, ou en cumul sur la période si vous le connaissez (par exemple l'inflation publiée entre deux dates).
- Exporter le tableau année par année en CSV pour le retravailler dans Excel.

**Limites.** Le rendement est supposé constant, alors que les marchés varient. Les frais, la fiscalité (flat tax, PEA, assurance-vie) et les prélèvements sociaux ne sont pas déduits. La durée compte en mois entiers, et les versements hebdomadaires sont lissés à 52/12 par mois. C'est une simulation, pas un conseil en investissement. Aucune donnée ne quitte votre ordinateur.
