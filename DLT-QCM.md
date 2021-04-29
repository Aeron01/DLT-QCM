# Exercices Distributed Ledger Technology

- Un arbre de merkle nécessite une paire de hashes pour produire un nouveau hash parent. Il faut donc absolument que le nombre de transactions qui produiront le `Merkle root` soit pair.  
  Comment est géré le cas ou le nombre de transactions dans le Block à valider est impair pour générer un `Merlke root` ?

correction : elle est simplement dupliquer.

Les nœuds considèrent toujours que la chaîne la plus longue est la bonne et continueront à l'étendre. Si deux nœuds diffusent simultanément des versions différentes du bloc suivant, certains nœuds peuvent recevoir l'un ou l'autre en premier. Dans ce cas, ils travaillent sur la première qu'ils ont reçue, mais sauvegardent l'autre branche au cas où elle deviendrait plus longue. Le lien sera rompu lorsque la prochaine preuve de travail sera trouvée et qu'une branche deviendra plus longue; les nœuds qui travaillaient sur l'autre branche passeront alors à la plus longue

- Dans le réseau bitcoin, Comment un nouveau noeud arrive t'il à retrouver ses pairs et ainsi rejoindre le réseau ?
  Expliquer le processus avec vos propres mots.

Tant qu'ils atteind de nombreux noeuds, il entrera rapidement dans un bloc et pourra faire sa demande pour recevoir le bloc suivant.

- Pouvez vous nommer au moins une personne qui a ou aurait pu influencer directement ou indirectement la création de Bitcoin par ses travaux (une personne qui n'a pas été nommée dans le cours)?

 1- Nicholas J. Szabo : créateur du système décentraliser bit gold, et qui est l'une des deux sources de bases du Bitcoin.

 2- Hal Finney : à travailler avec Wei Dai sur b-money qui est l'autre source de base du Bitcoin.

- Avec vos propres recherches et grâce aux compétences acquises en cours pouvez vous expliquer comment une Blockchain crée un lien entre ses différents Blocks?

Chaque bloc contiens un header (qui est crypter par SHA256) et celui du header du bloc précedent. Au final le Merkel root contiens tous les headers des blocs. Essayer d'en changer un, change completement le Merkel root, ce qui la rend invalide.

- Quelle structure de données informatique peut représenter le mieux cette chaine de Block: https://en.wikipedia.org/wiki/List_of_data_structures ?

correction : la liste chaîner

1- Merkle Tree

- Si je souhaite modifier une transaction de 10 bitcoin que j'ai effectué il y a 6 mois en une transaction de 1 Bitcoin, que dois je modifier dans la Blockchain et que dois je mettre en oeuvre pour que cette modification persiste ?  
  Est ce possible selon vous ?

  Il faudrais le changer la transaction dans le bloc d'il y a 6 mois et refaire tous les calculs de tous les blocs suivant jusqu'à maintenant. Ce qui demande une puissance de calcul, d'énergie et de temps quasi impossible.Ce qui rend la possibilité de faire un tel changement impossible actuellement. Peut-être qu'avec un ordinateur quantique abordable par le comun des mortels, mais ce n'est pas pour tout de suite :D.

correction : Il faudrait aussi recuillir 51% des noeuds (donc 51% du réseau) pour cela. Ce que les utilisateur n'accepteront jamais car il ne veullent pas que le reseau appartinnent à quelqu'un (et donc en est le contrôle). Dans le cas ou cela arriverais, tous les utilisateurs partiront sur un autre reseau avec une copie de la bloc chaine et continuer sur ce dernier. Car leur but est de se faire de l'argent sans qu'il y est quelqu'un qui controle cette bloc chaîne.
