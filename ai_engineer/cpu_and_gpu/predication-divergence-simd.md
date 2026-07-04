# Prédication et divergence SIMD

---
title: "Prédication et divergence SIMD"
tags: [cpu, simd, divergence]
niveau: intermédiaire
source: "Notes utilisateur — CPU, cache, SIMD, multithreading"
last_review: 2026-07-04
---


## Idée en 1 phrase
Les conditions peuvent réduire l’efficacité SIMD si toutes les lanes ne font pas le même travail.

## Prérequis
- SIMD
- Condition
- Vectorisation

## À quoi ça sert ?
- Comprendre pourquoi certaines boucles vectorisées restent lentes.
- Écrire du code plus cohérent pour les calculs parallèles.

## Explication simple
SIMD fonctionne bien quand tous les éléments font la même opération.  
Si certains éléments doivent faire autre chose, une partie du matériel reste inactive.

## Explication technique
Avec la prédication, un masque indique quelles lanes SIMD sont actives.  
Les lanes qui ne satisfont pas le prédicat sont désactivées pour cette instruction.  
Cela garde le résultat correct, mais peut gaspiller du calcul.  
Cette idée est aussi importante sur GPU avec la divergence de branches.

## Mini exemple

```python
import numpy as np

x = np.array([-2, -1, 0, 1, 2])
mask = x > 0

y = np.where(mask, x * 2, x)  # Certaines lanes suivent un prédicat
````

## Questions pour me tester

1. Pourquoi les conditions peuvent-elles ralentir SIMD ?
2. À quoi sert un masque de prédication ?
3. Quel lien existe entre SIMD CPU et divergence GPU ?

## Erreurs fréquentes

* Croire qu’une condition coûte toujours zéro en vectorisation.
* Confondre résultat correct et exécution efficace.
* Oublier que les lanes inactives consomment du débit potentiel.

## Liens liés

* [[simd-vectorisation]]
* [[memoire-cache-cpu]]