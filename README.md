# Projet SQL – Analyse de données football

Évaluation SQL du **DU Sorbonne Data Analytics** (Université Paris 1 Panthéon-Sorbonne, promotion 2026-2027) – enseignant : M. Orfandis.
Travail en binôme, rendu = **une vidéo de 5 à 6 minutes** (lien à transmettre via l'ENT de l'Université Paris 1).

---

## 1. Informations générales

| Élément | Valeur |
|---|---|
| Membres du binôme | Soufiane / *(nom du binôme à compléter)* |
| SGBD | SQLite |
| Base de données | European Soccer Database |
| Source | Kaggle – https://www.kaggle.com/datasets/hugomathien/soccer |
| Version / taille | Version 10 – `database.sqlite` (313 Mo) |
| Date de téléchargement | 12/10/2026 |
| Période couverte | Saisons 2008/2009 à 2015/2016 |
| Date limite de rendu | *25/10/2026* |
| Lien de la vidéo | *(à compléter après enregistrement)* |

> Règle de travail : un **seul fichier `database.sqlite` de référence** (même copie pour les deux), et tous les scripts SQL sont versionnés dans ce dépôt.

---

## 2. La base en un coup d'œil

7 tables, 199 colonnes au total :

| Table | Lignes | Colonnes |
|---|---|---|
| Country | 11 | 2 |
| League | 11 | 3 |
| Team | 299 | 5 |
| Team_Attributes | 1 458 | 25 |
| Player | 11 060 | 7 |
| Player_Attributes | 183 978 | 42 |
| Match | 25 979 | 115 |

*(Chiffres relevés sur la page Kaggle ; à revérifier avec `01_exploration.sql`.)*

---

## 3. Exigences du professeur (rappel)

- Présenter brièvement la base (provenance, objet).
- Expliquer la méthode d'accès aux données (ici : ouverture du fichier `.db`).
- Explorer : tables principales, NULL, anomalies, difficultés, avec quelques requêtes.
- Exploiter : faits saillants, enseignements, KPI. **C'est le cœur du sujet.**
- Syntaxes à montrer : `CASE WHEN`, `GROUP BY`, `HAVING`, `ORDER BY`, `LIMIT`, `JOIN`, sous-requêtes, `CREATE VIEW` et/ou `CREATE TABLE`.
- Ne pas lire un texte mécaniquement. Slides facultatives : montrer le code qui tourne.
- Seule la vidéo est notée (README, scripts et slides n'influencent pas la note).
- Facultatif : dashboard Grafana (non nécessaire pour la note maximale).

---

## 4. Répartition des tâches

| # | Tâche | Responsable | Échéance | Statut |
|---|---|---|---|---|
| 1 | Télécharger la base et vérifier qu'elle s'ouvre | | | ☐ |
| 2 | Exécuter `01_exploration.sql` et noter les résultats | | | ☐ |
| 3 | Analyse de la qualité des données (NULL, doublons, anomalies) et traitement | | | ☐ |
| 4 | Définir les KPI et les questions d'analyse | Les deux | | ☐ |
| 5 | Écrire et tester les requêtes (JOIN, GROUP BY / HAVING, CASE WHEN, sous-requête) | | | ☐ |
| 6 | Créer une vue (`CREATE VIEW`) pour un KPI réutilisable | | | ☐ |
| 7 | Rédiger le plan de la vidéo (pas un texte à lire) | Les deux | | ☐ |
| 8 | Répétition à deux, chronométrée | Les deux | | ☐ |
| 9 | Enregistrement de la vidéo (Loom ou autre) | | | ☐ |
| 10 | Dépôt du lien sur l'ENT de l'Université Paris 1 | Un seul | | ☐ |

---

## 5. Plan de la vidéo (≈ 6 minutes)

| Partie | Durée | Contenu | Qui parle |
|---|---|---|---|
| 1. Présentation de la base | 40 s | Sujet, source Kaggle, période, pourquoi ce choix | |
| 2. Méthode d'accès | 40 s | Ouverture du fichier `.db`, preuve que la base fonctionne (liste des tables) | |
| 3. Exploration et qualité | 1 min 30 | Tables principales, NULL, doublons, anomalies, traitement, 2 ou 3 requêtes | |
| 4. Exploitation et KPI | 2 min 30 | Requêtes avec jointures, regroupements, `CASE WHEN`, sous-requête, vue ; lecture des résultats | |
| 5. Conclusion | 30 s | Ce que les chiffres permettent de comprendre, limites | Les deux |

**Conseils d'enregistrement**
- Avoir tous les scripts prêts dans des onglets, pour ne pas chercher à l'écran.
- Exécuter les requêtes en direct et commenter le résultat avec ses propres mots.
- Viser 5 min 30 : sur le chrono, la limite à ne pas dépasser significativement est 6 minutes.
- Répéter une fois en entier avant l'enregistrement final.

---

## 6. Qualité des données (à remplir)

| Table | Colonne | Problème constaté | Nb de lignes concernées | Traitement choisi |
|---|---|---|---|---|
| | | | | |

Pistes à vérifier : NULL dans `Match` (cotes de paris, buts) et `Player_Attributes` (notes), doublons sur les identifiants, valeurs hors plage, incohérences de dates.

---

## 7. KPI et requêtes (à remplir)

| KPI / question | Tables utilisées | Syntaxes mises en œuvre | Résultat clé | Fichier |
|---|---|---|---|---|
| | | | | |

Idées de départ (à valider selon la structure réelle des tables) :
- Taux de victoire par équipe et par saison.
- Avantage à domicile par championnat.
- Moyenne de buts par match, par championnat et par saison.
- Équipes les plus offensives / les plus solides défensivement.
- Évolution des notes des joueurs dans le temps.

---

## 8. Structure conseillée du dépôt

```
.
├── README.md                # ce fichier
├── sql/
│   ├── 01_exploration.sql   # structure, volumes, premiers contrôles
│   ├── 02_qualite.sql       # NULL, doublons, anomalies, traitement
│   ├── 03_kpi.sql           # requêtes d'exploitation et KPI
│   └── 04_vues.sql          # CREATE VIEW
└── notes/
    └── plan_video.md        # points-clés à dire (pas un texte à lire)
```

Le fichier `database.sqlite` (313 Mo) ne doit pas être poussé sur GitHub tel quel : indiquer simplement le lien Kaggle, ou le partager via Drive.

---

## 9. Checklist finale avant l'envoi

- [ ] La vidéo dure entre 5 et 6 minutes.
- [ ] La source et la version de la base sont citées.
- [ ] La méthode d'accès est expliquée et la base fonctionne à l'écran.
- [ ] Les NULL et anomalies sont présentés, avec le traitement.
- [ ] Au moins un `JOIN`, un `GROUP BY` avec `HAVING`, un `CASE WHEN`, une sous-requête et une vue sont montrés.
- [ ] Les KPI sont expliqués : ce que les résultats permettent de comprendre.
- [ ] Les deux membres ont pris la parole (idéalement).
- [ ] Le texte n'est pas lu mot à mot.
- [ ] Le lien de la vidéo est accessible et déposé sur l'ENT.
