# Prédiction de l’Efficacité Énergétique des Bâtiments

> Projet de Master MLAIM - Université Sidi Mohamed Ben Abdellah (FSDM, Fès)  
> Réalisé par : Ayat Bouhrir & Wijdane El Karami  
> Encadré par : Pr. Dounia El Bourakadi  
> Année universitaire : 2024–2025

---

## Objectif

Ce projet vise à prédire la **charge de chauffage (Heating Load - Y1)** et de **refroidissement (Cooling Load - Y2)** des bâtiments résidentiels à partir de leurs caractéristiques de construction, en utilisant deux approches de réseaux de neurones :
- 🧠 **Extreme Learning Machine (ELM)**
- 🔁 **Backpropagation manuel (ManualBP)**

---

## Contenu du projet

- `ENB2012_data.xlsx` : Dataset utilisé (Energy Efficiency Data Set)
- `ELM.py` : Implémentation de la classe ELM
- `ManualBP.py` : Implémentation du réseau BP avec descente de gradient manuelle
- `main.py` : Prétraitement, entraînement, évaluation, visualisation
- `utils.py` : Fonctions auxiliaires (normalisation, métriques, graphiques)
- `README.md` : Ce fichier

---

## Description du dataset

- 📦 768 échantillons
- 🔢 8 variables d’entrée (surface, orientation, vitrage, etc.)
- 🎯 2 cibles à prédire :
  - `Y1` : Heating Load (charge de chauffage)
  - `Y2` : Cooling Load (charge de refroidissement)

---

## Méthodologie

1. **Chargement & prétraitement** :
   - Normalisation des données [0,1]
   - Séparation en jeu d’entraînement (80%) et de test (20%)

2. **Entraînement des modèles** :
   - ELM : Initialisation aléatoire, activation sigmoïde, pseudo-inverse
   - ManualBP : Architecture personnalisée, activation ReLU, rétropropagation manuelle

3. **Évaluation** :
   - Métriques : RMSE, MAE, R²
   - Visualisation : courbes de prédiction, barplots de comparaison

---

## Résultats

| Modèle            | Target | RMSE   | MAE   | R²    |
|-------------------|--------|--------|-------|-------|
| **ELM (200)**     | Y1     | 0.64   | 0.50  | 1.00  |
| **ELM (200)**     | Y2     | 1.76   | 1.29  | 0.97  |
| ManualBP (256-64) | Y1     | ~3.06  | >1.5  | <0.9  |
| ManualBP (256-64) | Y2     | ~3.06  | >1.5  | <0.9  |

✅ L’**ELM avec 200 neurones** surpasse tous les modèles BP en précision et rapidité.

---

## Visualisations

- Prédictions vs Réalité pour Y1 et Y2
- Graphiques comparatifs des RMSE, MAE, R² entre modèles
- Analyse qualitative des performances

---

## Comment exécuter

```bash
# Installer les dépendances
pip install numpy pandas matplotlib scikit-learn
```

---

## Conclusion

Le modèle **ELM** s'est montré plus performant que les réseaux BP :
- Moins de temps d’entraînement
- Meilleure généralisation
- Simplicité d’implémentation

Ce modèle est donc bien adapté aux **projets d'optimisation énergétique** en bâtiment.
