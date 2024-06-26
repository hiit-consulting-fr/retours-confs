# Rendre une application multitenant sans embêter les développeurs

## Main info

De nombreuses applications sont dans un premier temps développées de manière monotenant (une instance par client), avant de devoir être rendues multitenant (des instances mutualisées entre différents clients), le plus souvent pour limiter les coûts.

Chez Mirakl, nous sommes passés par là et avons dû transformer notre application monotenant en application multitenant. Notre objectif a été de rendre notre application multitenant en faisant en sorte que cela soit 100 % transparent pour les développeurs, afin de limiter les erreurs possibles et la charge mentale. C'est un chemin semé d'embûches durant lequel nous avons fait face à de nombreuses problématiques.

Ce talk propose un retour d'expérience sur comment nous avons fait, les difficultés techniques rencontrées, les enseignements que nous en avons tirés, les erreurs à éviter, nos recommandations...

On parlera d'exemple concrets de la vraie vie avec des bases de données, du Kafka, des batchs, des micro-services... Bref, un résumé de comment rendre une application complexe multitenant en limitant la charge mentale.

## Notes

