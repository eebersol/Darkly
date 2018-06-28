Security breach name 	: Robots.txt breach

Principle 				: Accéder à la page destiné aux robots d'indexation, pour trouver des urls que les développeurs ne souhaitaient pas voir apparaitre dans google.

Solve 					: Contrôler que les pages indiqués dans robots.txt ne soient pas exploitables par des utilisateurs malveillants ou encore masquer ce robots.txt

In case 				: En accédant au robots.txt on voit ceci : 
						{
							User-agent: *
							Disallow: /whatever
							Disallow: /.hidden
						}
						On essaye donc d'accéder à ses Urls sur la route /whatever on retrouve un file httppasswd avec le login/mot de passe root:8621ffdbc5698829397d97767ac13db3,
						il ne nous restaient plus qu'à trouver le hashage du mot de passe et de le reverse. (md5). Le mot de passe ainsi trouvé est dragon.
						il nous suffit d'aller sur /admin pour se log et obtenir le flag