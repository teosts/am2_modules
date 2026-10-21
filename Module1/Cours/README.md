# Module 1 : Linear regression, Ridge, Lasso & Elastic Net

Cours interactif en notebooks Jupyter (noyau **R (AM2)**), construit à partir de **tous** les documents du module : slides 2026-2027, syllabus `module1.pdf`, résolution *lactoferrin 24-25*, cheatsheet, scripts `ex1.r`, `ex1_v2.R`, `training.R`, `Homework1/homework1.R`, ainsi que la correction officielle du homework (`Homework1/fatty_acids_20201006.Rmd`) et le script de la séance TP (`Homework1/2026_AMV2_module1.R`).

Voir `../../README_environnement.md` pour configurer VS Code.

## Parcours

| # | Notebook | Contenu |
|---|---|---|
| 0 | `00_Introduction_et_prise_en_main.ipynb` | Organisation du cours, Data Mining & ML, KDD, supervisé ou non supervisé, jeux de données, rappels R |
| 1 | `01_Exploration_et_controle_des_donnees.ipynb` | Types de données, statistiques descriptives, boxplot, valeurs aberrantes ou manquantes, colinéarité, *scaling*, transformations |
| 2 | `02_Regression_lineaire_univariee.ipynb` | Moindres carrés, *r*, R², MSE ; lactoférrine ; analyse des résidus ; log10 |
| 3 | `03_Regression_lineaire_multivariee.ipynb` | $y = X\beta + e$, $(X'X)^{-1}X'y$, surapprentissage, colinéarité, précautions, nouvelles variables |
| 4 | `04_Selection_de_variables.ipynb` | Toutes les combinaisons (olsrr), AIC, backward, forward, stepwise (stepAIC), importance relative (relaimpo) |
| 5 | `05_Estimation_numerique_descente_de_gradient.ipynb` | Fonction de coût, descente de gradient, taux d'apprentissage, *feature scaling* |
| 6 | `06_Regressions_penalisees.ipynb` | Ridge, Lasso, Elastic Net, glmnet, choix de λ |
| 7 | `07_TP_Homework1_acides_gras.ipynb` | **TP guidé** sur les acides gras saturés : A) démarche de `homework1.R`, B) correction officielle (filtre CV, régions spectrales, Lasso), C) script de la séance TP 2026, D) comparaison des démarches |
| 8 | `08_Synthese_et_aide_memoire.ipynb` | Formulaire, pipeline généralisé en fonctions, aide-mémoire R, pièges, quiz, préparation à l'examen |

## Conventions

- **Exercice** : une cellule vide « À toi de jouer ! », puis un bloc **Voir la solution** à déplier.
- Définition · Attention · Complément (pédagogie ajoutée au-delà des documents du cours) · Fonction R (signature générale et arguments).
- Les notebooks sont livrés **déjà exécutés** pour que tu puisses comparer tes résultats. Pour repartir de zéro : *Clear All Outputs* puis *Run All*.
- Les données sont lues depuis le dossier parent (`../lactoferrin.csv`, `../Homework1/fatty_acids.csv`).
