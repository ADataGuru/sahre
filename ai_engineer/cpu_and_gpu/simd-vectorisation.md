# SIMD et vectorisation


---
title: "SIMD et vectorisation"
tags: [cpu, simd, vectorisation]
niveau: intermédiaire
source: "Notes utilisateur — CPU, cache, SIMD, multithreading"
last_review: 2026-07-04
---



## Idée en 1 phrase
SIMD permet d’appliquer une seule instruction à plusieurs données en même temps.

## Prérequis
- Instruction CPU
- Tableau de données
- Unité d’exécution

## À quoi ça sert ?
- Accélérer les calculs numériques.
- Exploiter plusieurs lanes de calcul dans un même cœur CPU.

## Explication simple
Au lieu de faire une addition nombre par nombre, le CPU additionne plusieurs nombres d’un coup.

## Explication technique
SIMD signifie Single Instruction, Multiple Data.  
Une instruction vectorielle opère sur un registre contenant plusieurs valeurs.  
Avec du SIMD explicite, on peut voir dans le binaire des instructions comme `vmulps`, `vaddps` ou `vstoreps`.  
C’est important pour l’inférence CPU, les kernels numériques et certaines opérations de serving LLM.

## Mini exemple

```python
import numpy as np

a = np.array([1, 2, 3, 4], dtype=np.float32)
b = np.array([10, 20, 30, 40], dtype=np.float32)

c = a + b  # Peut utiliser SIMD via NumPy / BLAS
````

## Questions pour me tester

1. Que signifie SIMD ?
2. Pourquoi SIMD est-il plus rapide qu’une boucle scalaire ?
3. Quel type de données profite le plus de SIMD ?

## Erreurs fréquentes

* Croire que SIMD = multithreading.
* Croire que toute boucle est automatiquement vectorisée.
* Oublier que les données doivent être bien organisées en mémoire.

## Liens liés

* [[execution-superscalaire-out-of-order]]
* [[predication-divergence-simd]]