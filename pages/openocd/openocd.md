---
title: OpenOCD
keywords: openocd
sidebar: openocd_sidebar
toc: true
hide_sidebar: true
permalink: openocd.html
folder: openocd
---


## Raspberry (as JTAG adapter)

Através do GPIO a Rb irá se conectar na porta JTAG do dispositivo target que se pretende debugar e subirá o servidor gdb.
    
### Configuração da interface do OpenOCD

1. Abrir o arquivo de configuração da interface para edição 

```shell
$ nano /usr/local/share/openocd/scripts/interface/raspberrypi-native.cfg
```

2. Adicionar ou editar as propriedades

```shell           
bcm2835gpio_swd_nums 25 24
bcm2835gpio_trst_num 7 
bcm2835gpio_srst_num 18
adapter_khz 20000
```

### Instalação do wiringpi

Biblioteca de manipulação de GPIO. (utilizada na função de reset do ESP32)

```shell
$ sudo apt-get install wiringpi
```

{% include links.html %}
