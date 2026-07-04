# Multithreading CPU et latence mémoire

---
title: "Multithreading CPU et latence mémoire"
tags: [cpu, multithreading, latence]
niveau: intermédiaire
source: "Notes utilisateur — CPU, cache, SIMD, multithreading"
last_review: 2026-07-04
---


## Idée en 1 phrase
Le multithreading permet de mieux utiliser le CPU quand certains threads attendent la mémoire.

## Prérequis
- Thread
- Cache CPU
- Latence mémoire

## À quoi ça sert ?
- Masquer la latence mémoire.
- Garder les unités d’exécution occupées.

## Explication simple
Quand un thread attend une donnée depuis la RAM, le CPU peut avancer sur un autre thread.

## Explication technique
Un processeur peut avoir plusieurs cœurs.  
Chaque cœur possède des unités d’exécution, des registres et souvent plusieurs contextes matériels.  
Avec SMT ou Hyper-Threading, plusieurs threads matériels partagent un même cœur.  
L’OS planifie les threads sur des cœurs logiques, mais ne les mappe pas directement sur une ALU.

## Mini exemple

```python
# Concept :
# Thread 1 attend la mémoire
# Thread 2 utilise le cœur pendant ce temps
# Cela améliore l'occupation du CPU
````

## Questions pour me tester

1. Pourquoi plus de threads peut aider si le programme attend la mémoire ?
2. Pourquoi un programme très compute-bound a-t-il besoin de moins de threads ?
3. Que planifie l’OS : une ALU ou un cœur logique ?

## Erreurs fréquentes

* Dire que l’OS mappe un thread directement sur une ALU.
* Croire que plus de threads accélère toujours.
* Oublier que les threads partagent le cache et les unités d’exécution.

## Liens liés

* [[memoire-cache-cpu]]
* [[simd-vectorisation]]