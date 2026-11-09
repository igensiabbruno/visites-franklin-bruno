### question :

# 1 que contient le fichier ¬/.ssh/allowed_signers et a quoi sert il :

- il contient le type de clé public, l'email, et la clé public. on stock une ligne par personne autorisé, il permets de certifié la siganture

# 2 qu'est ce qui distingue creer depuis un model (template) d'un fork ?

- dasn le cas du template il n'y a pas d'historique contrairement au fork qui embarque l'historique

# 3 apres le quash que devient la branche local, et pourquoi git bracnhe -d peut refuser de la supprimer

- sur le status de la branche, elle existe toujours en local, mais en remote elle est supprimer et fusioné sur le main en 1 seul commit. avec le -d(minuscule) il peut etre refuser car il y a des controle de securité d'action, car git considere qu'il est possible d'avoir des pertes

# 4 Pourquoi --force-with-lease et non --force, et qu'est ce que ca vérifie

- le --force-with-lease vérifie l'etat de la bracnhe diistante, et qu'elle corespond a la reference de la brache distant enregistré en local, car --force ne vérifie pas ca.

# 5 que ce passe t'il si on commit avec un fichier python mal formaté ? et avec git commit --no-verify

- commit avec --no-verify ne declanche pas le hook "pre-commit", parcontre avec un commit classique ca declenche le hook et ca effectue les verifications de formatage et bloque le commit

## PARTIE QUESTIONS :

# combien de temp c'est ecoulé entre notre premier commit et sa fusion sur le main

D'apres les commit visible sur le GUI il ya eu 26 minutes et 6 secondes.

# qu'est ce qui ne dépend pas de Github dans ce TP

Tout le travail local (commandes Git, signatures SSH, résolution de conflits, conteneurisation Docker, tests pytest et contrôles pre-commit/ruff) est universel et fonctionne à l'identique sur GitLab, Gitea ou Forgejo. En revanche, les interactions distantes changent de syntaxe et d'outillage : la CLI GitHub (gh) est remplacée par glab ou tea, le terme « Pull Request » devient « Merge Request » sur GitLab, et l'enregistrement de la clé publique de signature dépend de l'interface propre à chaque forge.

# pourquoi signer les commits si la forge vérifie déjà qui pousse ?

L'authentification réseau de la forge contrôle uniquement le droit d'accès au serveur distant lors du dépôt, tandis que la signature cryptographique prouve de manière infalsifiable l'identité de l'auteur réel et garantit l'intégrité du code, même en dehors de la plateforme.
