Création d'un site de salle de sport sécurisé, codé en PHP, HTML et Bootstrap.

Le style de ce site a été fait entièrement grâce à la librairie CSS Bootstrap et quelques images.

La gestion de la redirection des pages de ce site a été faite via un contrôleur, car cette méthode est plus efficace et rapide plutôt que de remettre les chemins sur chaque page. Tous les formulaires de ce site utilisent la méthode POST ainsi que la variable superglobale $_POST afin d'enregistrer les données dans la base de données via des requêtes SQL.

(Ce site est doté de la technologie PHPMailer, qui permet de se connecter à une adresse e-mail via un code d'application, puis d'envoyer un e-mail via la méthode $_POST, etc.) Grâce à cette technologie, j'ai pu sécuriser mon application en ajoutant plusieurs options telles que l'inscription et la réinitialisation de mot de passe (que j'ai dû désactiver par mesure de sécurité).

Concernant la base de données, je lui ai attribué 3 tables : utilisateurs (cette table sert à authentifier et identifier chaque utilisateur), password_resets (cette table sert à modifier le mot de passe d'un individu) et enfin une table commentaires. Cette table servait à m'envoyer des messages via la page contact, lorsque la page sendmail.php possédait mon code d'application ainsi que mon adresse e-mail (que j'ai dû désactiver par sécurité).

Quand un utilisateur s'inscrit sur mon site, token.php génère un code unique et aléatoire grace  a une fonction. ce code est ensuite sauvegardé dans la base de données. Ensuite, sendmail.php intègre ce code dans un lien et l'envoie automatiquement par e-mail à l'utilisateur via PHPMailer. Enfin, lorsque l'utilisateur clique sur ce lien, verrification.php récupère le code et l'e-mail, les compare avec ceux stockés en base de données, et si tout correspond, il active définitivement le compte en passant validation_mail à 1.Si la ligne validation_mail est a 0 cela signifie alors qu'un utilisateurs s'est inscrit mais n'as pas cliquez sur lien recus sur sont adresse email.

Pour tester mon  système d'authentification, rendez-vous sur le site magicpaille.com devloppez entierement par moi. Il s'agit d'un site de post-it  et de partage de notes destiné à mon entreprise d'e-commerce GNC-HOLDING, afin de nous permettre de sauvegarder et de partager des notes pour faciliter notre organisation au sein de l'entreprise.
