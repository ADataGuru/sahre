# Mémoire et caches CPU

---
title: "Mémoire et caches CPU"
tags: [cpu, memoire, cache]
niveau: base
source: "Notes utilisateur — CPU, cache, SIMD, multithreading"
last_review: 2026-07-04
---


## Idée en 1 phrase
La mémoire est lente par rapport au CPU, donc le processeur utilise des caches pour garder les données proches.

## Prérequis
- Adresse mémoire
- Latence
- Registre

## À quoi ça sert ?
- Réduire les attentes liées aux accès RAM.
- Accélérer les boucles qui réutilisent les mêmes données.

## Explication simple
La RAM est comme un entrepôt lointain.  
Le cache est comme une petite table près du CPU avec les données récentes.

## Explication technique
La mémoire peut être vue comme un tableau de bytes indexés par adresse.  
Quand le CPU charge une donnée, il charge souvent une ligne de cache complète, pas un seul byte.  
Une ligne de cache fait souvent 64 bytes, mais cela dépend du processeur.  
Les caches typiques sont L1, L2 et L3 : plus ils sont grands, plus ils sont généralement lents.

## Mini exemple

```python
# Accès contigus : souvent plus favorable au cache
arr = list(range(1000))
s = 0
for x in arr:
    s += x
````

## Questions pour me tester

1. Pourquoi accéder à la RAM coûte cher ?
2. Qu’est-ce qu’une ligne de cache ?
3. Pourquoi L1 est-il plus rapide que L3 ?

## Erreurs fréquentes

* Croire que le cache charge un seul byte.
* Croire que les tailles L1/L2/L3 sont universelles.
* Croire que le remplacement est toujours du vrai LRU exact.

## Liens liés

* [[cpu-instructions-registres]]
* [[multithreading-cpu-latence-memoire]]

