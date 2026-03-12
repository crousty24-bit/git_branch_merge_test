# git_branch_merge_test

🌿 Git Branch & Merge Cheatsheet 

Pour coder à plusieurs sur un même programme, les règles de bonne gestion (appliquées par toutes les start-ups modernes) sont les suivantes :

- On ne travaille JAMAIS directement sur la branche `master` ;
- Quand un développeur code, il travaille sur une fonctionnalité **précise** et doit donc créer une branche dédiée à ce travail. Elle doit porter un nom en lien avec la fonctionnalité (pas le nom du développeur !). Ex : `scrapping_every_hour` ou `show_total_market_valuation` ;
- On livre la fonctionnalité en fusionnant la branche dans `master` (en 2 merge, cf. ci-dessous);
- Une fois la branche fusionnée, le développeur peut la supprimer de son ordinateur.

Voici un résumé des commandes pratiques à utiliser pour manipuler les branches :

- `$ git branch` : affiche toutes les branches de ton repo Git, puis t'indique sur laquelle tu es actuellement
- `$ git branch nom_de_ta_feature` : créé une branche portant pour nom "nom_de_ta_feature"
- `$ git checkout nom_de_ta_branche` : se positionne sur la branche qui s'appelle "nom_de_ta_branche"
- `$ git merge nom_de_ta_branche` : fusionne la branche "n"om_de_ta_branche" VERS la branche sur laquelle tu te trouves actuellement. Seule la branche **sur laquelle tu te trouves** sera altérée (pas l'autre).

Enfin, si tu ne devais retenir qu'un seul truc de la leçon, voici les étapes de la gestion/fusion de branche. Si tu suis cette démarche, tu ne devrais pas avoir de souci 😉.

1. Se positionner sur master : `$ git checkout master`
2. Mettre à jour master sur son ordi : `$ git pull origin master`
3. Créer une branche, depuis master, pour travailler : `$ git branch nom_de_ta_feature`
4. Se placer sur cette branche : `$ git checkout nom_de_ta_feature`  
    À partir de là, tu peux travailler sur ta branche OKLM, repasser d'une branche à l'autre avec `git checkout`, tout en n'oubliant pas de faire des commits (`git add .` et `$ git commit -m "this is what i did"`)
5. Fusionner sa branche dans master (en 2 étapes de merge) :
    - `$ git checkout master`
    - `$ git pull origin master`
    - `$ git checkout nom_de_ta_feature`
    - `$ git merge master` + gérer les conflits si besoin
    - `$ git checkout master`
    - `$ git merge nom_de_ta_feature` + gérer les conflits si besoin
    - `$ git push origin master`