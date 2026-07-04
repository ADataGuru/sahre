# Instructions CPU et registres

---
* title: "Instructions CPU et registres"
* tags: [cpu, architecture, registres]
* niveau: base
* source: "Notes utilisateur — CPU, cache, SIMD, multithreading"
* last_review: 2026-07-04
---


## Idée en 1 phrase
Un programme compilé devient des instructions que le CPU exécute en modifiant l’état de ses registres et de la mémoire.

## Prérequis
- Programme compilé
- Mémoire
- Registre

## À quoi ça sert ?
- Comprendre ce qu’un CPU exécute réellement.
- Comprendre pourquoi le code source ne reflète pas toujours l’exécution matérielle.

## Explication simple
Le code source est une recette lisible par l’humain.  
Après compilation, il devient une suite d’ordres simples pour le CPU.

## Explication technique
Une instruction peut lire des registres, faire une opération dans une unité d’exécution, puis écrire un résultat dans un registre ou en mémoire.  
Le CPU ne manipule pas directement des variables Python ou C : il manipule des registres, des adresses et des valeurs.

## Mini exemple

```python
# Conceptuellement :
a = b + c
# Peut devenir :
# load b -> registre R1
# load c -> registre R2
# add R1, R2 -> registre R3
# store R3 -> a
````

## Questions pour me tester

1. Que devient un programme après compilation ?
2. Pourquoi les registres sont-ils importants pour le CPU ?
3. Une variable de haut niveau correspond-elle toujours à un registre ?

## Erreurs fréquentes

* Croire que le CPU exécute directement le code source.
* Croire qu’une variable = toujours une case mémoire.
* Oublier que le compilateur transforme fortement le programme.

## Liens liés

* [[execution-superscalaire-out-of-order]]
* [[memoire-cache-cpu]]