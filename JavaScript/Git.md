Git 
=====


Git checkout
-----------
Moyen de se positionner sur un élément.

Git commit
-----------

Un commit dans un dépôt (repository) git enregistre une image (snapshot) de tous les fichiers du repertoire. C'est une sorte de c/c.

Git branch
------------
Les branches sont simplement des références sur un commit spécifique. Une branche est un moyen d'exprimer "Je veux inclure le contenu de ce commit et de tous les commits parents."

Git merge
-----------
Combiner le contenu de deux branches. Faire un 'merge' avec Git crée un commit spécial qui a deux parents. Un commit avec deux parents indique en susbtance "Je veux inclure le contenu de ce parent et le contenu de cet autre parent, et l'ensemble de leurs parents."

Git remote
-----------
Copies de votre dépôt local sur un autre ordinateur.
Le dépôt distant sert de sauvegarde ! Le dépôt local de git a la capacité de restaurer des fichiers à un état précédent (comme vous le savez), mais toutes les informations sont stockées localement. En ayant des copies de votre dépôt git sur d'autres ordinateurs, vous pouvez perdre vos données et toujours repartir de là où vous en étiez resté.
les dépôts distants sociabilisent le projet ! Maintenant qu'il est hébergé quelque part ailleurs, vos amis peuvent y contribuer facilement (ou récupérer vos derniers changements).

Git clone
-----------
Dans le monde réel sera la commande que vous utiliserez pour créer des copies locales des dépôts distants.

Les branches distantes de git
-----------------------------
Lorsqu'on l'on clone, une nouvelle branche est apparue dans votre dépôt local appelée o/master. Ce type de branche est appelée une branche distante ; les branches distantes ont des propriétés spécifiques car elles servent à un but précis.
Les branches distantes reflètent l'état des dépôts distants (depuis la dernière fois où vous avez parlé avec ceux-ci). Elles vous aident à comprendre les différences entre votre travail et le travail public -- une étape critique à effectuer avant de partager son travail avec les autres.
Les branches distantes ont une propriété particulière: quand vous vous rendez dessus (checkout), `HEAD` est détaché. Git fait cela car vous ne pouvez pas travailler sur ces branches directement ; vous devez travailler ailleurs et ensuite partager votre travail avec le dépôt distant (après quoi vos branches distantes seront mises à jour).

Qu'est ce que `o`?
-------------------
Vous vous demandez peut-être ce qu'est le préfixe o/ devant ces branches distantes. En pratique, les branches distantes ont aussi une convention de nommage (obligatoire) -- elles sont affichées avec le format :

`<nom dépôt distant>/<nom de la branche>`

Donc, si vous regardez une branche nommée `o/master`, le nom de la branche est `master` et le nom du dépôt distant est `o`.

La plupart des développeurs nomment leur principal dépôt distant origin, pas o. C'est si commun que git configure en fait votre dépôt local pour être nommé origin quand vous faîtes un git clone du dépôt.

Malheureusement le nom complet origin ne rentre pas dans notre interface graphique et nous utilisons donc o comme raccourci :( Rappelez-vous juste que quand vous utilisez le vrai git, votre dépôt distant est probablement nommé origin!

Cela fait beaucoup d'un coup, donc voyons cela en action.

Git fetch
---------
Permet de rapporter (fetch) des données depuis un dépôt distant vers le nôtre.

`git fetch` procède en deux étapes principales, ni plus ni moins. Cela :

*télécharge les commits que le dépôt distant possède mais qui ne sont pas dans le nôtre, puis...
met à jour nos branches distantes (par exemple, o/master).
git fetch prend en fait notre représentation locale du dépôt distant pour la synchroniser avec ce à quoi le dépôt distant ressemble réellement (à ce moment-là).
*Nous avons dit que les branches distantes reflètent l'état du dépôt distant depuis la dernière fois où vous avez parlé à ces branches distantes. `git fetch` est le moyen de parler à ces branches distantes ! La relation entre git fetch et les branches distantes devrait vous apparaître clairement maintenant.

`git fetch` contacte le dépôt distant par Internet (via un protocole comme http:// ou git://).

`git fetch`, cependant, ne change rien à votre état local. Il ne met pas à jour votre branche master et ne va pas changer quelque chose aux fichiers qui se trouvent actuellement dans votre répertoire de travail.

C'est important à comprendre car un nombre important de développeurs pensent qu'exécuter git fetch va mettre leur dépôt local dans le même état que le distant. Cela peut télécharger toutes les données nécessaires pour faire cela, mais cela ne change en réalité rien sur vos fichiers locaux. 

Au bout du compte, vous pouvez vous représenter `git fetch` comme une étape de téléchargement.

Git pull
--------
le principe de rapatrier (fetch) les branches distantes puis les fusionner (merge) est si commun que git a en réalité une commande pour faire les deux à la fois ! Cette commande est `git pull`.

Git push
---------
Responsable de l'envoi de vos changements vers un dépôt distant et de la mise à jour de ce dépôt pour incorporer vos commits.




