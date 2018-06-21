Security breach name 	: Brut Force.

Principle 				: Tester de multiple combinaison pour un couple login / mot de passe.

Solve 					: Utiliser un captcha pour empêcher des requêtes en boucles ou bloquer une adresse IP au bout d'un certain nombre de requêtes consécutives.

In case 				: Dans le cas présent, nous sommes parti du principe qu'un compte admin devait exister,
							on utilise donc un mélange de brut force et d'attaque par dictionnaire
						( https://www.journaldugeek.com/2017/12/20/voici-la-liste-des-25-mots-de-passe-les-plus-populaires-et-probablement-les-moins-surs-de-2017/ ).