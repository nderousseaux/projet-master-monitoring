# Monitoring projet master

Partie monitoring du projet master.

L'idée est d'afficher sur une interface web les données de monitoring.

Elle sera composée de 3 parties :

- Un front-end, qui affichera les données
- Un back-end, qui récupérera les données de monitoring et les stockera dans une base de données
- Une base de données, qui stockera les données de monitoring

Ce répo est la partie front-end. Le back-end, et la base de donnée est en submodule.


## Project setup in development
```bash
npm install # install dependencies
npm run serve # run development server
```

### Lints and fixes files
```bash
npm run lint
```

## Build localy in production

### Build docker image
```bash
docker build -t monitoring-pm $(for i in `cat .env`; do out+="--build-arg $i " ; done; echo $out;out="") .
```

### Run docker container
```bash
docker run -d -p 80:80 monitoring-pm
```