# Fiches de Synthèse — Master Informatique & Mathématiques Appliquées

Recueil de synthèses et fiches de révision de niveau Master (M1 - M2). Ce dépôt regroupe les cours théoriques et appliqués axés sur l'apprentissage automatique, l'optimisation, la modélisation probabiliste et l'algorithmique avancée.

Le document complet est compilé dans `main.pdf` via $\LaTeX$, et chaque matière dispose de son propre point d'entrée modulaire.

---

## 📚 Matières couvertes

| Thématique | Modules & Notions abordées | Répertoire source |
| :--- | :--- | :--- |
| **Apprentissage Automatique** | Fondations Deep Learning, CNN, RNN, HMM, apprentissage supervisé, Ridge, méthodes à noyaux. | `subjects/DeepLearning/`<br>`subjects/Mathematiques_ML/` |
| **Probabilités & Simulation** | Chaînes de Markov (discret/continu), espérances conditionnelles, martingales, Metropolis-Hastings, Robbins-Monro. | `subjects/Probabilites/`<br>`subjects/Simulation_Aleatoire/` |
| **Optimisation** | Optimisation différentiable sans contraintes et sous contraintes (KKT, multiplicateurs de Lagrange). | `subjects/Optimisation/` |
| **Statistiques** | Modèles statistiques, information de Fisher, théorie de l'estimation et analyse du risque. | `subjects/Statistiques/` |
| **Algorithmique Avancée** | Théorie de la complexité, flots maximaux, programmation linéaire, métaheuristiques, CSP et SAT. | `subjects/Algorithmique/` |
| **Représentation des Connaissances** | Formalismes pour données incertaines et gestion des connaissances incomplètes. | `subjects/RCHI/` |
| **Systèmes & Modélisation** | Grammaires LL(k) (Compilation), modélisation géométrique 3D, opérations en temps discret (Signal). | `subjects/Compilation/`<br>`subjects/Informatique_Graphique/`<br>`subjects/Traitement_Signal/` |

---

## 🛠️ Compilation

Le projet s'appuie sur `latexmk` et un `Makefile` pour gérer les passes de compilation et les inclusions graphiques TikZ.

### Prérequis

* Distribution TeX complète (`texlive-full` ou `MacTeX`).
* `latexmk` et `make`.

### Commandes usuelles

* **Générer le recueil complet (`main.pdf`) :**
```bash
make
# ou directement avec latexmk
latexmk -pdf main.tex
```

* **Nettoyer les fichiers auxiliaires (.aux, .log, .fls, .synctex.gz) :**
```bash 
make clean 
make clean # Supprime le main.pdf en plus 
```
---

## 🌿 Workflow Git & Branches

Le développement des chapitres s'effectue sur des branches thématiques dédiées avant intégration dans main :
```
main : Version stable et publiable (PDF compilable sans erreur).

subjects/* : Branches de travail par discipline
    subjects/deep-learning
    subjects/mathematiques-ml
    subjects/signal
    etc...
```
### Intégration recommandée (Rebase & Fast-Forward)

Pour maintenir un historique linéaire et propre avant publication :

```bash
# 1. Mettre à jour la branche de travail par rapport à main
git checkout subjects/deep-learning
git rebase main

# 2. Revenir sur main et fusionner
git checkout main
git merge --ff-only subjects/deep-learning

# 3. Compiler et vérifier avant de pousser
make clean && make
git push origin main
```

---

## 📁 Architecture du dépôt

```
.
├── Makefile              # Cibles de compilation globales et clean
├── main.tex              # Document maître intégrant toutes les UE
├── main.pdf              # Document de sortie compilé
├── titlepage.tex         # Page de garde
├── images/               # Schémas vectoriels, séparateurs et figures
└── subjects/             # Modules indépendants par matière
    ├── Algorithmique/
    ├── Compilation/
    ├── DeepLearning/
    ├── Informatique_Graphique/
    ├── Mathematiques_ML/
    ├── Optimisation/
    ├── Probabilites/
    ├── RCHI/
    ├── Simulation_Aleatoire/
    ├── Statistiques/
    └── Traitement_Signal/
```

---

## 📝 Licence & Précisions

Notes rédigées à des fins d'étude et de synthèse personnelle. Les retours sur les démonstrations ou les corrections de coquilles sont les bienvenus via Issues ou Pull Requests.