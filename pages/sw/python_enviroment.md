---
title: Ambiente virtual Python
keywords: virtualenvwrapper workon
tags: [python]
sidebar: sw_sidebar
toc: true
permalink: python_enviroment.html
folder: sw
---

## Instalação

1. Instalar a ferramenta de gerenciamento de ambientes Python (virtualenvwrapper)
    ```shell
    $ sudo pip install virtualenvwrapper
    ```

## Configuração

2. Adicionar o path do repositório de ambientes
    ```shell
    $ echo source /usr/local/bin/virtualenvwrapper.sh >> ~/.bashrc
    ```
3. Criar repositório de ambientes
    ```shell
    $ mkdir ~/.virtualenvs
    ```
4. Criar e configurar a variável de ambiente 
    ```shell
    $ echo 'export WORKON_HOME=$HOME/.virtualenvs' >> ~/.bashrc && . ~/.bashrc
    ```

## Execução 

1. Ativar o ambiente

    ```shell
    $ workon nome_ambiente
    ```

## Comandos básicos

### Criar um ambiente

```shell
$ mkvirtualenv --python=path <nameOfEnvironment>
```

Para descobrir qual é o path do python usar o comando


```shell
$ which python
```

### Listar os ambientes

```shell
$ lsvirtualenv <nameOfEnvironment>
```

### Excluir o ambiente

```shell
$ rmvirtualenv <nameOfEnvironment>
```

### Copiar o ambiente

```shell
$ cpvirtualenv <nameOfEnvironment>
```

## Info adicionais

Selecionar outra versão do Python

```shell
$ sudo update-alternatives --config python
```

## Referências: 

[link1](https://pt.stackoverflow.com/questions/52/como-usar-o-virtualenv-para-gerenciar-as-depend%C3%AAncias-duma-aplica%C3%A7%C3%A3o-python)

[link2](https://stackoverflow.com/questions/16123459/virtualenvwrapper-and-python-3)


{% include links.html %}