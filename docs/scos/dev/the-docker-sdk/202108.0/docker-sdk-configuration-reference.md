---
title: Docker SDK configuration reference
description: Instructions for the most common configuration cases of the Docker SDK.
last_updated: Jun 16, 2021
template: howto-guide-template
originalLink: https://documentation.spryker.com/2021080/docs/docker-sdk-configuration-reference
originalArticleId: 624e91c2-a207-41b4-957f-98de2a96f90b
redirect_from:
  - /2021080/docs/docker-sdk-configuration-reference
  - /2021080/docs/en/docker-sdk-configuration-reference
  - /docs/docker-sdk-configuration-reference
  - /docs/en/docker-sdk-configuration-reference
---

This document is a quick reference for the most common configuration options of the Docker SDK.

The configuration parameters in this document are examplary. You may need to adjust them per your project requirements.



## Сonfiguring Opcache

To configure Opcache, adjust `deploy.*.yml` as follows:

```yaml
image:
    tag: spryker/php:7.3
    php:
        ini:
            "opcache.revalidate_freq": 0
            "opcache.enable_cli": 0
            "opcache.enable": 0
            ...
```

## Defining a memory limit

To define a memory limit, adjust `deploy.*.yml` as follows:

```yaml
image:
    tag: spryker/php:7.3
    php:
        ini:
            "memory_limit": 512m
```

## Providing custom environment variables to Spryker applications

To provide custom environment variables to Spryker applications, adjust `deploy.*.yml` as follows:

```yaml
image:
    tag: spryker/php:7.3
    environment:
        MY_CUSTOM_ENVIRONMENT_VARIABLE: 1
        ...
```

{% info_block infoBox %}

The environment variables defined in `environment:` are embedded into all application images.

{% endinfo_block %}

## Increasing maximum upload size

To increase maximum upload size, update `deploy.*.yml` as follows:

1. In Nginx configuration, update maximum request body size:
```yaml
...
		applications:
			backoffice:
				application: backoffice
				http:
					max-request-body-size: {request_body_size_value}
				...
```

2. Update PHP memory limit:

```yaml
image:
    ...
    php:
        ini:
            memory_limit: {memroy_limit_value}
            ...
```
