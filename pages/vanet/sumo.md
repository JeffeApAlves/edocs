---
title: SUMO
keywords: sumo
hide_sidebar: false
sidebar: vanet_sidebar
toc: true
permalink: sumo_install.html
folder: vanet
---

## Instalação

1. Instalar os pacotes
    
    ```shell
    $ sudo apt-get install sumo sumo-tools sumo-doc
    ```

2. Adicionar a variável de ambiente SUMO_HOME

    ```shell
    $ nano $HOME/.baschrc
    $ SUMO_HOME=<path_do_sumo>
    ```

## Execução

2. Para rodar com o modo gráfico habilitado

    ```shell
    $ sumo-gui <arquivo.cfg>
    ```

## Referências: 

[Manual de instalação](http://sumo.dlr.de/wiki/Installing)

{% include links.html %}
