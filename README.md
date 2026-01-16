# YOLOKAN-11 : Détection Intelligente des Parasites du Paludisme

## 📌 Présentation du Projet

Le diagnostic manuel du paludisme par examen microscopique est un processus lent et sujet à l'erreur humaine. **YOLOKAN-11** est une solution d'IA hybride conçue pour automatiser ce diagnostic avec une précision accrue.

En fusionnant la puissance de détection de **YOLO11** et la capacité d'approximation non linéaire des **Réseaux de Kolmogorov-Arnold (KAN)**, ce modèle identifie les parasites sur des frottis sanguins minces et estime la charge parasitaire (parasitémie).

---

## 🚀 Innovations Majeures

### 1. Hybridation YOLOKAN

Contrairement aux réseaux classiques utilisant des poids fixes et des fonctions d'activation (ReLU), YOLOKAN intègre des **fonctions d'activation apprenantes** basées sur les **polynômes de Tchebychev**. Cela permet :

* Une meilleure capture des textures fines des parasites.
* Une réduction du nombre de paramètres tout en conservant la performance.

### 2. Prétraitement Médical (CLAHE)

Application de l'algorithme **CLAHE** (*Contrast Limited Adaptive Histogram Equalization*) pour normaliser l'éclairage et renforcer les contrastes entre les parasites et le cytoplasme des globules rouges.

### 3. Gestion du Déséquilibre (Focal Loss)

Utilisation de la **Focal Loss** pour concentrer l'apprentissage sur les exemples "difficiles" (parasites) et ignorer le bruit de fond (cellules saines majoritaires).

---

## 📊 Résultats Cliniques

| Métrique | YOLO11 (Baseline) | **YOLOKAN-11 (Proposé)** |
| --- | --- | --- |
| **mAP@0.5** | 89.9% | **92.4%** |
| **F1-Score** | 0.86 | **0.89** |
| **MAE (Parasitémie)** | 2.5% | **1.2%** |

> **Conclusion :** YOLOKAN-11 réduit l'erreur de comptage de moitié par rapport au modèle standard.

---

## 🛠️ Structure du Projet

```text
├── data/               # Jeu de données (NIH-NLM)
├── models/             # Définitions des couches KAN & Tchebychev
├── weights/            # Modèles pré-entraînés (.pt)
├── utils/              # Scripts CLAHE et calcul de parasitémie
├── train.py            # Pipeline d'entraînement
└── detect.py           # Script d'inférence et visualisation

```

---

## 📥 Installation

```bash
# Cloner le projet
git clone https://github.com/votre-nom/YOLOKAN-11.git
cd YOLOKAN-11

# Installer les dépendances
pip install -r requirements.txt

```

---

## 🔍 Visualisation Qualitative

| **Annotation Expert** | **Prédiction YOLOKAN-11** |
| --- | --- |
|  |  |
| *Vérité terrain : Parasites annotés* | *Détection précise des trophozoïtes* |

---

## 📖 Méthodologie & Travaux Connexes

Ce projet s'appuie sur le jeu de données **NIH-NLM** comprenant des milliers d'images de frottis infectés. L'architecture suit un protocole rigoureux en 4 phases :

1. **Baseline** : Étalonnage avec YOLO11.
2. **Hybridation** : Intégration du noyau KAN.
3. **Ablation** : Test des fonctions de perte (BCE vs Focal Loss).
4. **Validation** : Test en aveugle sur des données patients.

---

## 🎓 Auteur

Projet réalisé dans le cadre d'un mémoire de recherche sur l'intelligence artificielle appliquée à l'imagerie médicale.

---
