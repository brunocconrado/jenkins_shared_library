# Jenkins shared library: Tutorial `Hands-On`

Vamos começar esse tutorial de `Jenkins Shared Library` construindo a infra necessária. Para isso vamos utilizar imagens docker e o [`docker-compose`](https://docs.docker.com/compose/install/) para orquestrar os containers.

O [`docker-compose.yml`](https://github.com/clodonil/jenkins_shared_library/blob/master/docker-compose.yml) que faz a declaração das imagens do `jenkins` e do `gitlab`.


Para começar faça o clone do projeto do git.
```bash
$ git clone https://github.com/clodonil/jenkins_shared_library.git
```

No diretório do projeto, suba os container utilizar o [`docker-compose`](https://docs.docker.com/compose/install/).

```bash
$ docker-compose up
```

Como as imagens em execução, podemos acessar também o `jenkins` pela url `http://localhost:8080` e o `gitab` pela url `http://localhost`.

Na configuração do jenkins, é necessário recuperar o token que está no diretório `/var/jenkins_home/secrets/initialAdminPassword` para seguir a instalação.

Esse processo pode ser feito conectando diretamente no container como mostra a imagem a seguir.

![img1](https://github.com/clodonil/jenkins_shared_library/imgs/img1.png)

Também é possível listar os logs do container para obter esse token. Veja qual o processo que fica mais fácil para você.

```bash 
$ docker logs jenkins_shared_library_jenkins_1


*************************************************************
*************************************************************
*************************************************************

Jenkins initial setup is required. An admin user has been created and a password generated.
Please use the following password to proceed to installation:

ce83575d55d2418fafc98f86f1151cdb

This may also be found at: /var/jenkins_home/secrets/initialAdminPassword

*************************************************************
*************************************************************
*************************************************************
```
