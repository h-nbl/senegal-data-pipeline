# senegal-data-pipeline

Pipeline de données (ETL) et tableau de bord sur l'éducation au Sénégal, à partir de données ouvertes.

Un programme récupère des données publiques sur le secondaire général, les vérifie, les nettoie
et les charge dans une base PostgreSQL. Un tableau de bord interactif permet ensuite de les
explorer par région, par année et par sexe.

> **Statut :** en cours de développement (phase 0 : cadrage).

## Questions

**Question principale :** entre 2016 et 2025, l'accès au secondaire général et la réussite au BAC
progressent-ils au Sénégal, et de façon égale entre les régions et entre filles et garçons ?

1. **Régions :** quelles régions ont le taux brut de scolarisation au secondaire général le plus bas
   en 2025, et lesquelles ont le plus progressé depuis 2016 ?
2. **Sexe :** comment évolue l'écart entre filles et garçons, pour le taux brut de scolarisation au
   secondaire général (2016–2025) et pour la réussite au BAC (2018–2022) ?
3. **Facteurs associés :** les académies dont les lycées sont mieux équipés (électricité, point d'eau,
   cantine) et dont les enseignants sont plus qualifiés ont-elles de meilleurs taux de réussite au BAC ?

## Sources

Portail : [Open Data for Senegal – Éducation](https://senegal.opendataforafrica.org/data/#topic=Education)

| # | Jeu de données | Fichier | Années |
|---|---|---|---|
| 1 | [Effectifs des enseignants par inspection d'académie, cycle et sexe](https://senegal.opendataforafrica.org/owakqrf/2-2-effectifs-des-enseignants-par-inspection-acad%C3%A9mique-cyle-et-sexe) | `ObservationData_wccbqne.csv` | 2016–2025 |
| 2 | [Scolarisation par inspection d'académie, cycle et sexe](https://senegal.opendataforafrica.org/ervtjfc/3-1-scolarisation-par-inspection-acad%C3%A9mique-cyle-et-sexe) | `ObservationData_ahetued.csv` | 2016–2025 |
| 3 | [Résultats aux examens scolaires et professionnels par cycle, académie et sexe](https://senegal.opendataforafrica.org/bagghce/r%C3%A9sultats-aux-examens-scolaires-et-professionnels-par-cycle-d-enseignement-par-acad%C3%A9mie-et-par-sexe) | `ObservationData_hqtyss.csv` | 1991–2022 |
| 4 | [Nombre et infrastructures scolaires par inspection d'académie, cycle et statut](https://senegal.opendataforafrica.org/joelgdb/2-1-nombre-et-infrastructures-scolaires-par-inspection-acad%C3%A9mique-cyle-et-statut) | `ObservationData_kzpcpje.csv` | 2016–2025 |

**Licence :** à confirmer (aucune licence n'est indiquée sur le portail).

Les fichiers de données ne sont pas versionnés dans ce dépôt : un script de téléchargement sera
ajouté plus tard.

## Limites connues des données

- Le taux de réussite au BAC par académie manque pour 2020 (seul le chiffre national existe).
- Le taux brut de scolarisation est donné pour les 14 régions ; les autres indicateurs sont
  découpés en 16 inspections d'académie (Dakar, Pikine-Guédiawaye et Rufisque sont séparées).

## Stack prévue

Python, pandas, PostgreSQL, SQLAlchemy, Streamlit, Docker, GitHub Actions.