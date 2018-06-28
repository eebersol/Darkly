Security breach name 	: Upload

Principle 				: Réussir à upload un fichier inattendu grâce à la modification du header, du nom du fichier (null byte) ou encore d'utiliser la double extension.

Solve 					: Faire un meilleur contrôle du nom du fichier envoyé.

In case 				: Dans le cas présent nous avons utilisé le browser firefox car google Chrome ne permet pas la 	modification à la voler des headers, grâce au logiciel burp suite
							nous pouvions intercepter et modifier les valeurs dune request header. Il ne nous restait plus qu'a modifier le conten-type pour faire croire au serveur qu enous étions entrain d'upload une image et non un script php.






							1.active foxyproxy
							2.active burpsuite
							3.open mozilla go to : http://[ip]/index.php?page=upload#
							4.open burp - proxy / intercep
							5. modify header and forward
