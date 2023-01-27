<!-- 1 Para que en este repo público nadie pueda hacer determinadas cosas configuraremos las credenciales: Vamos a settings | secrets | Click en Actions y crearé un par de repository secrets. Son como variables ocultas que nadie puede ver (de hecho, después de crearla ya no la podremos ver más) -->

<!-- 2 Click en New repository secret - Name: DOCKER_USER y Secret: anguiano (usuario de docker) | Click Add secret. Una vez creado puedo reemplazarlo pero no lo puedo ver -->

<!-- 3 Crearé un token de acceso en dockerhub:  Icono de mi usuario / Account Setting / Security / Click en New Access Token y escribo "Github-Actions". En las opciones de Access permissions selecciono Read & Write | Click en Generar-->

<!-- 4 Una vez que copie el token ya no lo podré ver más -->

<!-- 5 Voy a Github...: Click en New repository secret  - Name: DOCKER_PASSWORD y Secret: PEGO EL TOKEN | Click Add secret  -->

<!-- 6 Voy a Dokerhub y creo un Repositorio privado (solo puedo hacer uno): Name: docker-graphql - Create -->

<!-- 7 Voy a Github | Actions | Docker Image (Hay varios así que compruebo que ponga "Build a Docker image to deploy, or push to a registry"). Click en Configurar - Veo que me crea un archivo docker-image.yml cuya ruta es docker-graphql/.github/worflows/ -->

<!-- 8 Reviso el ARCHIVO docker-image.yml DE GITHUB ACTIONS

// Este nombre lo podría cambiar
name: Docker Image CI

// Son los triggers en los que quiero que se dispare esta acción
on:
  // Quiero que se dispare la acción cada vez que hago un push a la rama main
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

// El trabajo que queremos hacer
jobs:

  build:
    // Va a correr en un ubuntu (como alpine)
    runs-on: ubuntu-latest

    steps:
    // Esto es un repositorio en github que ya viene con ciertos procedimientos
    - uses: actions/checkout@v3
    - name: Build the Docker image
      // Hemos entrado en ese ubunto y ejecutamos el comando de construcción
      run: docker build . --file Dockerfile --tag my-image-name:$(date +%s)
 -->

<!-- 9 En Github Click en Start commit (no hace falta poner nombre) | Click en Commit new file y puedo ver en en repo de github una carpeta .github/workflows -->

<!-- 10 clicko en Actions y veo que está intentando hacer esa acción, que no funciona. -->

<!-- 11 desde los tres puntitos de su dcha la cancelo -->

<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center">A progressive <a href="http://nodejs.org" target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore" target="_blank"><img src="https://img.shields.io/npm/dm/@nestjs/common.svg" alt="NPM Downloads" /></a>
<a href="https://circleci.com/gh/nestjs/nest" target="_blank"><img src="https://img.shields.io/circleci/build/github/nestjs/nest/master" alt="CircleCI" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master" target="_blank"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#9" alt="Coverage" /></a>
<a href="https://discord.gg/G7Qnnhy" target="_blank"><img src="https://img.shields.io/badge/discord-online-brightgreen.svg" alt="Discord"/></a>
<a href="https://opencollective.com/nest#backer" target="_blank"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor" target="_blank"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec" target="_blank"><img src="https://img.shields.io/badge/Donate-PayPal-ff3f59.svg"/></a>
    <a href="https://opencollective.com/nest#sponsor"  target="_blank"><img src="https://img.shields.io/badge/Support%20us-Open%20Collective-41B883.svg" alt="Support us"></a>
  <a href="https://twitter.com/nestframework" target="_blank"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

## Description

[Nest](https://github.com/nestjs/nest) framework TypeScript starter repository.

## Installation

```bash
$ npm install
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Test

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://kamilmysliwiec.com)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](LICENSE).
