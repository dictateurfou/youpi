* Sur le MCD ci-présent, on ne sait pas quelle est la référence. Ce qui serait bien, c'est de souligner le champ qui sert de liaison (regarder l'exemple a la fin).

* Dans le "LIKE" entouré, je vois "many-to-many" avec "1,1". 
Cette cardinalité indique un "one-to-one".
 ** a coter du user il aurait fallu mettre "0,n" :
 ** Le "0" pour dire que le minimum est 0 (l'utilisateur peut avoir liké 0 mug).
 ** Le "n" pour dire que c'est un nombre qui peut varier, cela peut être 1 comme 10, 100...


* La cardinalité dans ce sens : user -> has -> address 0,n n'est pas bonne dans le contexte. Il est précisé qu'un utilisateur a une ou plusieurs adresses et qu'il peut également ne pas en avoir.

* Pour les likes, il aurait été préférable d'ajouter une table intermédiaire. Je te donne un exemple ci-dessous pour illustrer mes propos. J'ai ajouté deux cardinalités avec des commentaires pour que tu comprennes. Je n'en ai pas ajouté à un endroit précis pour que tu puisses le compléter toi-même grâce aux explications.

 ![This is a alt text.](https://cdn.discordapp.com/attachments/760716097925283853/1082147728915709982/dfdf.drawio_5.png "This is a sample image.")
 
Dans l'ensemble, c'est plutôt bien. Je t'invite à prendre en compte les commentaires pour corriger tes erreurs.

Si mes explications n'ont pas suffi, voici deux courtes vidéos qui sont efficaces pour comprendre.
 
 https://www.youtube.com/watch?v=2Oskf-eiB60
 https://www.youtube.com/watch?v=WvMheNdSCoA
