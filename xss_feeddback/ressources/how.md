Security breach name 	: XSS (Cross-site scripting) persistant

Principle 				: Insérer du code html/js/php dans un input pour essayer d'accéder à des données sensibles ou modifier la perception du site aux autres utilisateurs.

Solve 					: Stringifier les valeurs envoyé par le user.

In case 				: Sur la page feedback, un seul des deux inputs stringify la valeur entré par le user, le second ne fait que limiter la taille de son input,
							il nous a donc suffit de changer ca taille maximum pour ensuite y insérer du code.

							code 	: <u> COUCOU </u>