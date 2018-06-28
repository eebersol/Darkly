Security breach name 	: Directory traversal attack / include

Principle 				: Permet via des liens symboliques d'accéder à des contenues sensibles

Solve 					: Evaluer les arguments de l'url

In case 				: L'utilisation des liens symboliques dans l'url faisait apparaître des messages d'alertes différents, 	nous avons donc persévérés ...
							[IP]/?page=../../../../../../../etc/passwd