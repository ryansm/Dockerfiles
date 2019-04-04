# Angular

## Objetivo

Esta imagem permite o desenvolvimento com o [Angular Framework](https://angular.io/) através da ferramenta [Angular CLI](https://github.com/angular/angular-cli).

## Como utilizar

Esta imagem está disponível via docker image, hospedada no Docker Hub com a tag [```ryansm/angular```]().

### Criando um projeto

Navegue até a pasta onde o projeto será criado e digite o seguinte comando:

``` bash
docker run --rm -it -v $PWD:/var/www/html ryansm/angular ng new app
```

### Levantando o projeto

Você pode utilizar via docker-compose, como no exemplo abaixo:

``` yaml
version: "3"

services:
  angular:
    image: ryansm/angular
    restart: always
    environment:
      - NODE_ENV=development
    volumes:
      - ./app:/var/www/html
    ports:
      - "4200:4200"
```

Execute o seguinte comando:

``` bash
docker-compose up -d
```

Espere alguns instantes ou acompanhe o status da compilação do projeto com o seguinte comando:

``` bash
docker-compose logs -f angular
```

Após isso navegue no endereço: `http://localhost:4200/`. O app recarregará automaticamente caso você altere algum código-fonte.