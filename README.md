https://medium.com/@mosheezderman/how-to-set-up-ci-cd-pipeline-for-a-node-js-app-with-jenkins-c51581cc783c


Deployer une appi node js depuis git par jenkins
jenkins est en local
le deploiement se fait sur ma machine
on utilise ngRok pour creer des liens public vers ma machine (ce ci est indispensable car les webhook exigent des des url public et non des localhots)
il faut ajouter un parametre de type string.
Ce parametre correspond au nom de la branche qu'on veut builder.
Dans le Pipeline il faut spécifier la variable pour le nom de la branche. (on peut aussi le faire lea config du job)