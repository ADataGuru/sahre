
# Questions à réviser — CPU, cache, SIMD

## CPU et registres
- Que devient un programme après compilation ?
- Pourquoi les registres sont-ils plus rapides que la mémoire ?
- Une variable du code source correspond-elle toujours à une case mémoire ?

## Superscalaire et out-of-order
- Pourquoi le CPU peut-il exécuter certaines instructions en parallèle ?
- Quelle est la différence entre superscalaire et out-of-order ?
- Pourquoi le réordonnancement ne doit-il pas changer le résultat visible ?

## Mémoire et cache
- Pourquoi la RAM introduit-elle de la latence ?
- Qu’est-ce qu’une ligne de cache ?
- Pourquoi les accès contigus sont-ils souvent plus rapides ?
- Pourquoi L1 est-il plus rapide mais plus petit que L3 ?

## SIMD
- Que signifie SIMD ?
- Pourquoi une instruction SIMD peut-elle accélérer un calcul vectoriel ?
- Quelle différence entre SIMD et multithreading ?
- Comment reconnaître du SIMD explicite dans un binaire ?

## Prédication et divergence
- Pourquoi une condition peut-elle réduire l’efficacité SIMD ?
- À quoi sert un masque de prédication ?
- Pourquoi cette notion est-elle aussi utile pour comprendre les GPU ?

## Multithreading CPU
- Comment le multithreading masque-t-il la latence mémoire ?
- Pourquoi plus de threads n’est-il pas toujours meilleur ?
- Que fait l’OS quand il planifie un thread ?

