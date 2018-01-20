---
title: Django
keywords: django
sidebar: web_sidebar
toc: true
permalink: django.html
folder: web
---

## Instalação 

1. Preparar um ambiente virtual Python (detalhes [aqui][python_enviroment])

2. Instalar os pacotes que estão listados no arquivo requeriments.txt

    ```shell
    $ workon <enviroment_name>
    $ pip install -r requerements.txt
    ````
    
3. Executando a aplicação
 
    ```shell
    $ python <APP_DIR>/manage.py runserver <IP_SERVER>
    ```

Obs.: Instalação do adm do postgree (pgAdmin4) instalado separado, pois não está no repositório.

{% include links.html %}
