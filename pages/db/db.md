---
title: PostGreSQL
tags: [getting_started, troubleshooting]
keywords: database
summary:
sidebar: db_sidebar
toc: true
permalink: db.html
folder: db
---

## Instalação

## Verificação

1. Verificando o banco

    ```shell
    psql -h HOST -U USUARIODOBANCO -W
    SELECT version();
    ```

2. Configuração do IP  e porta do servidor 

    ```shell        
    $ sudo nano /etc/postgresql/9.6/main/postgresql.conf
    ```

3. Configuração forma de acesso dos usuários

    ```shell
    $ sudo nano /etc/postgresql/9.6/main/pg_hba.conf
    ```

4. Criação de usuário banco de dados

    ```shell
    psql -h 192.168.42.1 -U postgres -W

    CREATE USER <nomedousuario> SUPERUSER INHERIT CREATEDB CREATEROLE;
    ALTER USER nomedousuario> with password <my_secure_password>;
    ALTER USER <nomedousuario> PASSWORD <nova_senha>;
    ```

5. LOG

    ```shell
    $ nano /var/log/postgresql/postgresql-9.6-main.log
    ```

{% include links.html %}
