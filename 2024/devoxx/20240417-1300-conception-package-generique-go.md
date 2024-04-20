# Conception des packages génériques "slices" et "maps" en Go

## Main info

Go supporte ENFIN les generics, après 10 ans d'attente.

Celà ouvre la voie à des vraies fonctions génériques dans la librairie standard, pour manipuler nos slices et maps de façon un peu plus propre et idiomatique. Mais concevoir une nouvelle API claire, intelligible, efficiente n'est pas chose facile!

Passons en revue quelques nouvelles fonctionnalités, et les tradeoffs associés.

## Notes

- Go language opinionated
- Une seule façon de formater
- Pas moyen de customiser le GC