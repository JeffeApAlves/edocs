---
title: Ambiente virtual Python (virtualenvwrapper)
keywords: virtualenvwrapper
tags: [django]
sidebar: python_sidebar
toc: true
permalink: python_enviroment.html
folder: python
---

## Instalação

1. Instalar a ferramenta de gerenciamento de ambientes Python
    ```shell
    $ sudo pip install virtualenvwrapper
    ```
2. Adiciona o path de repositorios de ambientes
    ```shell
    $ echo source /usr/local/bin/virtualenvwrapper.sh >> ~/.bashrc
    ```
3. Cria repositorio de ambientes
    ```shell
    $ mkdir ~/.virtualenvs
    ```
4. Cria e configura a variável de ambiente 
    ```shell
    $ echo 'export WORKON_HOME=$HOME/.virtualenvs' >> ~/.bashrc && . ~/.bashrc
    ```
5. Descobre a path da versao que se deseja
    ```shell
    $ which pythonXX-->saida e a path
    ```

## Execução 

1.7 Ativa o ambiente

```shell
$ workon nome_ambiente
```

## Comandos básicos
1. Cria um ambiente
```shell
$ mkvirtualenv --python=path <nameOfEnvironment>
```
1. Lista os ambientes
```shell
$ lsvirtualenv <nameOfEnvironment>
```

1. Exclui o ambiente
```shell
$ rmvirtualenv <nameOfEnvironment>
```

1. Copia o ambiente
```shell
$ cpvirtualenv <nameOfEnvironment>
```

## Info adicionais

Selecionar outra versão do Python

```shell
$ sudo update-alternatives --config python
```
## Referencias: 

[link1](https://pt.stackoverflow.com/questions/52/como-usar-o-virtualenv-para-gerenciar-as-depend%C3%AAncias-duma-aplica%C3%A7%C3%A3o-python)

[link2](https://stackoverflow.com/questions/16123459/virtualenvwrapper-and-python-3)


{% include links.html %}
