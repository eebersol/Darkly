Security breach name 	: Crawler hidden folder

Principle 				: Parser des dossiers censé ne pas être accessbible. Créer un crawler pour lire le contenu de chacun des dossiers contenant un README. Placer le resultat dans un fichier puis grep le tout.

Solve 					: Créer un fichier sur son serveur bloquant l'accès à certains fichiers / dossiers (ex: .htaccess)

In case 				: Exécuter ce script et attendre (cela peut prendre quelques minutes)
							./script.rb http://[IP] .hidden/ > result.txt
