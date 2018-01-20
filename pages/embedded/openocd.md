---
title: OpenOCD
keywords: openocd raspberry jtag debug
sidebar: embedded_sidebar
toc: true
hide_sidebar: false
permalink: openocd.html
folder: openocd
---


## Raspberry (as JTAG adapter)

Criará um server para clientes gdb. Rodando na raspberry pi 0, transformando-a em um adapter jtag. É possível configurar a interface permitindo
a RB, através do GPIO, conectar na porta JTAG do dispositivo target que se pretende debugar.
    
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
