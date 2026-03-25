# CI/CD

## Questions

1) Créez un fichier `docker-compose.yml` et ajoutez-y un service `db` s'appuyant sur l'image Docker `postgres:latest`.

2) Créez une base de données `city_api` avec une table `city` contenant les colonnes suivantes :
    - `id`, un entier non signé non nul, clé primaire de la colonne ;
    - `department_code`, une chaîne de caractères non nulle ;
    - `insee_code`, une chaîne de caractères ;
    - `zip_code`, une chaîne de caractères ;
    - `name`, une chaîne de caractères non nulle ;
    - `lat`, un flottant non nul ;
    - `lon`, un flottant non nul.

3) Dans le langage de votre choix, créez un service web ayant les spécifications suivantes :
    - `POST /city` avec pour corps de la requête un JSON au format décrit plus bas doit retourner un code `201` et enregistrer la ville dans la base de données ;
    - `GET /city` doit retourner un code `200` avec la liste des villes au format JSON ;
    - `GET /_health` doit retourner un code `204`.

    Vous pouvez trouver un exemple de JSON [ici](https://github.com/leroyguillaume/tps/blob/main/cities.json).

    Faîtes en sorte que votre service soit configurable avec les variables d'environnement suivantes :
    - `CITY_API_ADDR`, qui correspond à l'adresse d'écoute de votre serveur HTTP (par défaut, `127.0.0.1`) ;
    - `CITY_API_PORT`, qui correspond au port d'écoute de votre serveur HTTP (par défaut, `2022`) ;
    - `CITY_API_DB_URL`, qui correspond à l'URL de connexion vers la base de données (le service doit planter si non specifié) ;
    - `CITY_API_DB_USER`, qui correspond au nom d'utilisateur utilisé pour se connecter à la base de données (le service doit planter si non specifié) ;
    - `CITY_API_DB_PWD`, qui correspond au mot de passe utilisé pour se connecter à l base de données (le service doit planter si non specifié).

4) Écrivez les tests suivants :
    - un test qui s'assure que l'insertion dans la base de données fonctionne correctement ;
    - un test qui s'assure que la récupération de la liste des villes fonctionne correctement ;
    - un test qui s'assure que l'endpoint de healthcheck fonctionne correctement.

5) Écrivez un fichier `Dockerfile` à la racine de votre projet. Testez que votre image Docker est correcte.

6) Utilisez [pre-commit](https://pre-commit.com/) pour linter le code (Dockerfile inclus).

7) Écrivez un workflow GitHub Actions `quality` pour que pre-commit soit exécuté à chaque push.

8) Écrivez un workflow GitHub Actions `tests` pour exécuter les tests. La database ne doit pas être mocked.

9) Modifiez le workflow pour qu'un build de l'image Docker soit réalisé à chaque push. Faites en sorte que le build soit caché pour optimiser le temps d'exécution.

10) Ajoutez un scan trivy dans ce workflow.

11) Ajoutez un workflow pour exécuter [Renovate](https://docs.renovatebot.com/).

12) Réflechissez et implémentez un workflow de release.
