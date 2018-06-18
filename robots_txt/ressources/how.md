De base le robot google index l'ensemble des liens d'un site web, pour éviter que certaine page n'y apparaissent exemple : /admin /adminLog etc.. on peut créer un file robots.txt à la racine: http://[host]/robots.txt ce file servira de règle pour le robot google tout les liens Disallow: /something seront ignoré par le robot google.

Dans le cas présent : le file robots.txt resemble a ca : 



User-agent: *
Disallow: /whatever
Disallow: /.hidden

Sur la route /whatever on trouver un file httppasswd
un user root et un mot de passe hash : root:8621ffdbc5698829397d97767ac13db3
Il suffit alors de trouver le type de hash, il existe des sites pour cela, on voit que le mot de passe est en md5, des sites existent aussi pour reverse certain hash dont le md5, le mot de passe décrypté nous donne le mot : dragon
Ultérieurement nous avions trouver une page /admin demandant un login et un mot de passe. On essaye donc root/dragon.