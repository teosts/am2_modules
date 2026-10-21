# Module 2 : Validation, PCR et PLS

Cours interactif en notebooks Jupyter (noyau **R (AM2)**), construit à partir de **tous** les documents du module :
- le syllabus `module2.pdf` (ce module n'a pas de slides) ;
- l'exercice dirigé officiel `PLS_PCR_fatty_acids_20201007.Rmd` (et ses rendus .html/.docx) ;
- l'énoncé `homework2.pdf` et sa correction officielle `Soil_Rmarkdown_20201015.Rmd` ;
- l'article *Chimiométrie 2006* (concours dont proviennent les données de sols) ;
- les scripts `pca_fatty_acids.R`, `pcr_fatty_acids.R`, `pls_fatty_acids.R` et `homework2.R`.

Voir `../../README_environnement.md` pour configurer VS Code (noyau « R (AM2) »).

## Parcours

| # | Notebook | Contenu |
|---|---|---|
| 0 | `00_Introduction_et_donnees.ipynb` | Place du module, jeux de données (lait MIR, sols NIR, octane), concours Chimiométrie 2006, packages FactoMineR et pls |
| 1 | `01_Validation.ipynb` | Validation interne ou externe, taille du jeu de calibration, leave-one-out, k-fold, indicateurs (RMSEC, RMSECV, RMSEP, biais, SEP, RPD) |
| 2 | `02_ACP_et_detection_des_outliers_spectraux.ipynb` | ACP, vecteurs et valeurs propres, distance de Mahalanobis, GH, potentiel de prédiction |
| 3 | `03_Regression_sur_composantes_principales_PCR.ipynb` | PCR en 3 phases (à la main et avec pls), exemple octane, choix du nombre de composantes |
| 4 | `04_Regression_PLS.ipynb` | PLS, algorithme NIPALS pas à pas (Tables 3 à 12 du syllabus), Q², T² de Hotelling, interprétation |
| 5 | `05_Comparaison_des_modeles_et_validation_externe.ipynb` | PCR, PLS, Ridge, Lasso et Elastic Net (`cv.glmnet`), validation externe, régions bruitées |
| 6 | `06_TP_Homework2_sols.ipynb` | **TP guidé** sur l'azote total des sols : A) démarche de `homework2.R`, B) correction officielle, C) comparaison avec le concours, D) choix final |
| 7 | `07_Synthese_et_aide_memoire.ipynb` | Formulaire, pipeline généralisé en fonctions (appliqué au lait et aux sols), aide-mémoire R, pièges, quiz, préparation à l'examen |

## Conventions

- **Exercice** : une cellule « À toi de jouer ! », puis un bloc **Voir la solution** à déplier.
- Encadrés : **Définition**, **Attention**, **Complément** (pédagogie ajoutée au-delà des documents du cours), **Fonction R** (signature générale et arguments).
- Les notebooks sont livrés **déjà exécutés** pour que tu puisses comparer tes résultats. Pour repartir de zéro : *Clear All Outputs* puis *Run All*.
- Les données sont lues depuis le dossier parent (`../fatty_acids.csv`, `../Xcal.txt`…). Les fichiers d'origine du module ne sont jamais modifiés.
- Le TP enregistre son équation finale dans `Cours/best_model_Nt.RData`. Ton `Module2/best_model.RData` n'est pas touché.
