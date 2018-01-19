---
title: Toolchain ESP32
keywords: embarcado
sidebar: embedded_sidebar
toc: true
permalink: esp32_toolchain.html
folder: embedded
---

O toolchain possui um gdb client que pode ser usado com o OpenOCD para debug.

## Instalação

1. Fazer o download do arquivo. Escolher entre 32 e 64 conforme o sistemas operacional dos host.  

    ```shell
    $ wget https://dl.espressif.com/dl/xtensa-esp32-elf-linux64-1.22.0-73-ge28a011-5.2.0.tar.gz
    ```
or
    ```shell
    $ wget https://dl.espressif.com/dl/xtensa-esp32-elf-linux32-1.22.0-73-ge28a011-5.2.0.tar.gz
    ```
2. Descompacter em um diretório onde se deseja instalar o toolchain

    ```shell
    $ cd <local_de_destino>
    $ tar -xzf ~/Downloads/xtensa-esp32-elf-linux64-1.22.0-73-ge28a011-5.2.0.tar.gz
    ```

## Configuração

1. Adicionar no .bashrc o path do toolchain na variável PATH 

    ```shell
    export PATH=$PATH:<path do toolchain>/bin
    ```

## Referências: 
       
[Get started](http://esp-idf.readthedocs.io/en/latest/get-started/)

[Git hub espressif](https://github.com/espressif/esp-idf/blob/master/docs/get-started/linux-setup.rst)

[Read docs](http://esp-idf.readthedocs.io/en/v3.0-rc1/)

[configuração openocd](http://esp-idf.readthedocs.io/en/latest/api-guides/jtag-debugging/tips-and-quirks.html#jtag-debugging-tip-openocd-configure-target)


{% include links.html %}
