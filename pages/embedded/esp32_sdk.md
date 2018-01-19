---
title: SDK ESP32(esp-idf)
keywords: embarcado
sidebar: embedded_sidebar
toc: true
permalink: esp32_sdk.html
folder: embedded
---

## Instalação 

1. Clonar o repositório oficial e os submodulos 

    ```shell
    $ git clone --recursive https://github.com/espressif/esp-idf
    ```
2. Adicionar no .bashrc a variável de ambiente IDF_PATH apontando para o bin do repositório clonado 

    ```
    export IDF_PATH=~/esp/esp-idf
    ```

## Atualização

1. Atualizando o repositorio local do sdk.

    ```shell
    $ git pull
    $ git pull --recurse-submodules
    ```

## Referências: 
       
[Get started](http://esp-idf.readthedocs.io/en/latest/get-started/)

[Git hub espressif](https://github.com/espressif/esp-idf/blob/master/docs/get-started/linux-setup.rst)

[Read docs](http://esp-idf.readthedocs.io/en/v3.0-rc1/)

[configuração openocd](http://esp-idf.readthedocs.io/en/latest/api-guides/jtag-debugging/tips-and-quirks.html#jtag-debugging-tip-openocd-configure-target)


{% include links.html %}
