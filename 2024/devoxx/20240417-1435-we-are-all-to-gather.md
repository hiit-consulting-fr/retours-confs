# We are all to gather
## Main info
45' by Remi Forax (Université Eiffel, Paris)

see the conference here:

TL;DR: 
Une bonne explication globale et un live coding de la nouvelle API Gather (dans les streams java) présente en preview sur java 22
Je recommande de lire OCP17 chap10 sur les streams pour comprendre le fonctionnement global des streams et des collectors avant d'écouter cette conf.

## Notes

Fonctionnements des streams
un stream est composé de 3 types d'opérators:
- Spliterator: source de données
- Opérateurs intermédiaires: filter, flatmap, map...
- Opérateur final: collect, reduce, toList...

Java 22 introduit un nouveau type d'étape intermédiaire via l'API Gather. On définit des Gatherer:  
- Permet de définir n'importe quel type d'opération intermédiaire 
- Ressemble a l'API Collector (On retrouve, comme pour les collectors, de nombreux gathere prédifini dans Gatherers.

Un gatherer est défini par:  
- initializer: C'est un supplier (Supplier<T>) qui est utilisé pour conserver l'état de l'opérateur (dans le cas d'un limit(3) par exemple il faut garder l'état pour savoir combien d'élément on a déjà passé dans le stream).
- Integrateur
- Combinor: combine le résultat des différents threads en cas d'exécution //
- Finisher: Permet de définir le fonctionnement de l'opérateur dans le cas où l'état de fin est atteint (dans le cas limit(3) quand on a déjà process 3 éléments)


La suite de la conf est un live coding qui a pour but de recoder via l'interface gather les opérateurs intermédiaires connus des streams (filter, limit et je sais plus lequel, 3 jours de confs, on oubli forcément des trucs)
