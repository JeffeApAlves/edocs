---
title: Redis
keywords: redis
sidebar: redis_sidebar
toc: false
permalink: redis.html
folder: data
---


# Configuração

1. Configuração da senha 

    ```shell
    redis-cli ping
    echo -n "senha" | md5sum
    redis-cli SET user.admin.password <code_md5>
    ```

{% include links.html %}
