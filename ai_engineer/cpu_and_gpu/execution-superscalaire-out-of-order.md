
# Exécution superscalaire et out-of-order

---
* title: "Exécution superscalaire et out-of-order"
* tags: [cpu, superscalar, out-of-order]
* niveau: intermédiaire
* source: "Notes utilisateur — CPU, cache, SIMD, multithreading"
* last_review: 2026-07-04
---

## Idée en 1 phrase
Un CPU moderne peut exécuter plusieurs instructions par cycle si leurs dépendances le permettent.

## Prérequis
- Instructions CPU
- Registres
- Dépendances de données

## À quoi ça sert ?
- Augmenter le débit d’instructions.
- Exploiter les unités d’exécution qui seraient sinon inutilisées.

## Explication simple
Même si le code semble séquentiel, certaines instructions sont indépendantes.  
Le CPU peut donc les lancer en parallèle.

## Explication technique
Le CPU décode les instructions en micro-opérations.  
Il analyse leurs dépendances et construit une forme de graphe de dépendances.  
L’exécution superscalaire lance plusieurs micro-opérations dans le même cycle.  
L’out-of-order permet de changer l’ordre d’exécution sans changer le résultat visible du programme.

## Mini exemple

```python
# b + c et d + e sont indépendants
x = b + c
y = d + e
z = x + y  # dépend de x et y
````

## Questions pour me tester

1. Pourquoi deux instructions peuvent-elles être exécutées en parallèle ?
2. Quelle est la différence entre superscalaire et out-of-order ?
3. Pourquoi le résultat final reste-t-il correct ?

## Erreurs fréquentes

* Croire que le CPU construit un DAG visible au niveau du code source.
* Confondre parallélisme matériel et threads logiciels.
* Croire que tout peut être réordonné librement.

## Liens liés

* [[cpu-instructions-registres]]
* [[simd-vectorisation]]

