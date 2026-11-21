# erzs247.github.io

Pages de connexion Firebase (« auth helper ») hébergées sur le domaine des applis
[RiftDex](https://erzs247.github.io/riftdex/) et [NightDex](https://erzs247.github.io/nightdex/).

Les téléphones isolent les données de chaque site : quand la connexion Google passe par
`<projet>.firebaseapp.com`, l'appli installée sur l'écran d'accueil ne retrouve pas le résultat au retour
et l'utilisateur revient non connecté. Servir ces fichiers depuis `erzs247.github.io/__/auth/` met la connexion
sur le même site que l'appli.

Fichiers copiés tels quels depuis `https://<projet>.firebaseapp.com/__/auth/` (identiques pour tous les projets) :
`handler`, `handler.js`, `experiments.js`, `iframe`, `iframe.js`. GitHub Pages sert `handler.html` à l'adresse
`/__/auth/handler` et `iframe.html` à `/__/auth/iframe`. `.nojekyll` empêche Jekyll d'ignorer le dossier `__`.

Pour chaque projet Firebase qui l'utilise : `authDomain` = `erzs247.github.io` dans la configuration de l'appli, et
`https://erzs247.github.io/__/auth/handler` ajouté aux « URI de redirection autorisés » du client OAuth Web
(console Google Cloud → API et services → Identifiants).

Voir https://firebase.google.com/docs/auth/web/redirect-best-practices (option 4).
