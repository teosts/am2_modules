# AM2 : Analyse multivariée 2, cours en notebooks Jupyter (R)

Cours interactif du cours AM2 (Data Mining & Machine Learning, Gembloux Agro-Bio Tech, ULiège) sous forme de notebooks Jupyter en **R**.

| Dossier | Contenu |
|---|---|
| `Module1/` | Régression linéaire, Ridge, Lasso, Elastic Net |
| `Module2/` | Validation, ACP, PCR, PLS |

Chaque module contient un dossier `Cours/` avec les notebooks numérotés (à suivre dans l'ordre) et un `README.md` qui décrit le parcours. Les données sont dans le dossier du module et sont lues depuis le notebook via `../`.

Les notebooks utilisent un noyau Jupyter nommé **« R (AM2) »** (identifiant `ir-am2`). La procédure ci-dessous installe R, Jupyter et tous les packages nécessaires dans un environnement conda isolé, puis enregistre ce noyau. Elle est identique sous Linux et Windows ; seules l'installation de Miniforge et la manière d'ouvrir un terminal changent.

## 1. Récupérer le dépôt

Avec git :

```bash
git clone https://github.com/teosts/am2_modules.git
cd am2_modules
```

Sans git : sur la page GitHub, **Code → Download ZIP**, puis décompresse l'archive.

## 2. Installer Miniforge (conda)

Miniforge fournit `conda`, qui installe R et Python avec toutes leurs dépendances, sans droits administrateur.

**Linux**

```bash
wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-x86_64.sh
bash Miniforge3-Linux-x86_64.sh
```

Accepte la licence, garde le dossier proposé et réponds `yes` à la question sur l'initialisation du shell. Ferme puis rouvre le terminal.

**Windows**

1. Télécharge `Miniforge3-Windows-x86_64.exe` depuis https://github.com/conda-forge/miniforge/releases/latest.
2. Lance l'installateur avec les options par défaut (installation « Just Me »).
3. Ouvre **Miniforge Prompt** depuis le menu Démarrer. Toutes les commandes suivantes se tapent dans cette fenêtre.

## 3. Créer l'environnement `am2`

Depuis le terminal (Linux) ou Miniforge Prompt (Windows) :

```bash
conda create -n am2 -c conda-forge -y python=3.12 jupyterlab r-base r-irkernel r-glmnet r-pls r-mass r-car r-leaps r-olsrr r-relaimpo r-factominer r-corrplot r-summarytools r-pander r-knitr r-reshape2 r-ggplot2
```

L'installation prend quelques minutes.

## 4. Enregistrer le noyau « R (AM2) »

```bash
conda activate am2
R -e "IRkernel::installspec(name = 'ir-am2', displayname = 'R (AM2)')"
```

Pour vérifier, `jupyter kernelspec list` doit afficher une ligne `ir-am2`.

## 5. Ouvrir les notebooks

### Avec JupyterLab (navigateur)

```bash
conda activate am2
cd chemin/vers/am2_modules
jupyter lab
```

JupyterLab s'ouvre dans le navigateur. Ouvre `Module1/Cours/00_Introduction_et_prise_en_main.ipynb` ; le noyau « R (AM2) » est sélectionné automatiquement. Pour arrêter Jupyter, fais `Ctrl+C` dans le terminal.

Sous Windows, `cd` vers un autre disque demande l'option `/d`, par exemple `cd /d D:\cours\am2_modules`.

### Avec VS Code

1. Installe les extensions **Jupyter** et **Python** (Microsoft).
2. Ouvre le dossier `am2_modules` (**File → Open Folder**), puis un fichier `.ipynb`.
3. En haut à droite : **Select Kernel → Jupyter Kernel… → R (AM2)**.
   Si « R (AM2) » n'apparaît pas : `Ctrl+Shift+P` → **Python: Select Interpreter** → choisis l'environnement `am2`, puis recommence l'étape 3.

### Utilisation

- `Shift+Entrée` exécute la cellule courante et passe à la suivante.
- Les notebooks sont livrés déjà exécutés pour que tu puisses comparer tes résultats. Pour repartir de zéro : **Clear All Outputs**, puis **Run All**.
- Les solutions des exercices sont dans les blocs **Voir la solution**, à déplier.

## Dépannage

| Problème | Solution |
|---|---|
| `conda` n'est pas reconnu | Linux : rouvre le terminal ou lance `~/miniforge3/bin/conda init`. Windows : utilise **Miniforge Prompt**, pas l'invite de commandes classique. |
| Jupyter demande de choisir un noyau à l'ouverture | Le noyau `ir-am2` n'est pas enregistré : refais l'étape 4 avec l'environnement `am2` activé. |
| `there is no package called '...'` | Installe le package dans l'environnement : `conda install -n am2 -c conda-forge r-<nom>` (nom en minuscules), puis redémarre le noyau (**Restart Kernel**). |
| Fichier de données introuvable | Ouvre le notebook depuis son dossier `Cours/` sans le déplacer : les chemins `../` en dépendent. |

## Désinstaller

```bash
jupyter kernelspec remove ir-am2
conda deactivate
conda env remove -n am2
```
