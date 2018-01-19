---
title: Debug ESP32
keywords: embarcado
sidebar: embedded_sidebar
toc: true
permalink: esp32_debug.html
folder: embedded
---

## Instalação

1. Instalar as dependências
    
    ```shell
    $ sudo apt-get install build-essential git-core cmake doxygen libusb-1.0 make libtool pkg-config autoconf automake texinfo
    ```


2. Clonar o repositório do opencocd para o esp32 (2)
 
    ```shell
    $ git clone --recursive https://github.com/espressif/openocd-esp32.git
    ```

3. Compilar OpenOCD usando a sequência de comandos abaixo (2):

    ```shell
    $ cd <diretorio onde foi clonado>
    $ sudo apt-get install make libtool pkg-config autoconf automake texinfo libusb-1.0 
    $ ./bootstrap (when building from the git repository)
    $ ./configure --enable-sysfsgpio --enable-bcm2835gpio
    $ make
    $ sudo make install
    ```

Observações:

(1) O ESP32 utiliza um fork do openocd. Essa versão pode ser adquirida através do comando abaixo:

(2) As opções **--enable-sysfsgpio** **--enable-bcm2835gpio** são para uso do da Raspberry como jtag adapter

## Referências: 
       
[Get started](http://esp-idf.readthedocs.io/en/latest/get-started/)

[Git hub espressif](https://github.com/espressif/esp-idf/blob/master/docs/get-started/linux-setup.rst)

[Read docs](http://esp-idf.readthedocs.io/en/v3.0-rc1/)

[configuração openocd](http://esp-idf.readthedocs.io/en/latest/api-guides/jtag-debugging/tips-and-quirks.html#jtag-debugging-tip-openocd-configure-target)


{% include links.html %}
