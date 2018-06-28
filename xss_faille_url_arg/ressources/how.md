Security breach name 	: XSS (Cross-site scripting) non-persistant via l'url

Principle 				: Insérer du code html/js/php dans un url pour essayer d'accéder à des données sensibles.

Solve 					: Masquer les arguments présents dans l'url.

In case 				: Dans l'url nous avions accès au nom de la page inclus ainsi qu'à la source de l'image. Nous avons donc essayé 
							d'insérer : une autre image, du code html/php/js en brut, une image en base 64, du code php/js en base64 avec comme MIME (médiatype) image/png,
							du code avec comme MIME text/plain et enfin du code avec comme MIME text/html. Code en question : [ <script> alert("BIM") </script> ].

http://192.168.143.133/?page=media&src=data:text/html;base64,PHNjcmlwdD4gYWxlcnQoIkJJTSIpOyA8L3NjcmlwdD4=
