# Environnement Jupyter + R pour le cours AM2

Cet environnement sert à **tous les modules** du cours (Module1, Module2, …).

## Ce qui a été installé

| Élément | Emplacement | Rôle |
|---|---|---|
| Env conda `.am2-env` | `AM2/.am2-env/` | Python 3.12 + Jupyter (jupyterlab, ipykernel, nbconvert) |
| Bibliothèque R dédiée | `AM2/.am2-Rlib/` | `IRkernel`, `IRdisplay`, `pbdZMQ`, `repr` (noyau R pour Jupyter) |
| Kernelspec `ir-am2` | `~/.local/share/jupyter/kernels/ir-am2/` (+ copie dans `.am2-env/share/jupyter/kernels/`) | Noyau « **R (AM2)** » |

Le noyau utilise le **R du système** (`/usr/bin/R`, 4.6) et donc **tous les packages déjà installés** (glmnet, MASS, olsrr, summarytools…). Il ajoute seulement `.am2-Rlib` en tête de `.libPaths()`. Rien n'a été installé dans la bibliothèque R personnelle.

## Utilisation dans VS Code

1. Installer les extensions **Jupyter** et **Python** (Microsoft) si ce n'est pas déjà fait.
2. Ouvrir le dossier `AM2` (ou un module) dans VS Code, puis un fichier `.ipynb`.
3. En haut à droite : **Select Kernel** → **Jupyter Kernel…** → **R (AM2)**.
   - Si « R (AM2) » n'apparaît pas : `Ctrl+Shift+P` → *Python: Select Interpreter* → choisir `AM2/.am2-env/bin/python`, puis recommencer l'étape 3.
4. Exécuter une cellule : `Shift+Entrée`.

## Utilisation hors VS Code (optionnel)

```bash
~/Documents/GBX/MA2/AM2/.am2-env/bin/jupyter lab
```

## Installer un package R supplémentaire

Dans un notebook : `install.packages("nom")`. Le package va dans ta bibliothèque R habituelle et reste disponible partout.

## Tout désinstaller

```bash
rm -rf ~/Documents/GBX/MA2/AM2/.am2-env ~/Documents/GBX/MA2/AM2/.am2-Rlib ~/.local/share/jupyter/kernels/ir-am2
```
