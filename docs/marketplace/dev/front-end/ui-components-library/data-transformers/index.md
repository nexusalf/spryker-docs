---
title: Data Transformers
last_updated: Jun 07, 2021
description: This document provides details about the Data Transformers service in the Components Library.
template: concept-topic-template
---

This document explains the Data Transformers service in the Components Library.

## Overview

Data Transformers are responsible for transforming data from one form to another based on a certain configuration.
As a result, backend systems can manipulate data without changing the frontend at all (such as table datasource, select datasource).

Anyone may use the Data Transformer Service to modify data by configuring a specific `DataTransformer`.

```html
<spy-select
    [datasource]="{
        type: 'http',
        transform: {
            type: 'chain',
            transformers: [
                {
                    type: 'array-map',
                    mapItems: {
                        type: 'object-map',
                        mapProps: {
                            colId: {
                                type: 'date-parse',
                            },
                        },
                    },
                },
                {
                    type: 'collate',
                    configurator: {
                        type: 'table',
                    },
                },
                {
                    type: 'lens',
                    path: 'data',
                    transformer: {
                        type: 'array-map',
                        mapItems: {
                            type: 'object-map',
                            mapProps: {
                                colId: {
                                    type: 'date-serialize',
                                },
                            },
                        },
                    },
                },
            ],
        },
    }"
>
</spy-select>
```

## Main Service

With the main module, you can register any data transformer by key via the static method `withTransformers()`. This method assigns the data transformer object to the `DataTransformerTypesToken`.

The main service injects all registered types from the `DataTransformerTypesToken`.

`transform()` method finds the specific service from the `DataTransformerTypesToken` by `config.type` (from the argument) and returns an observable with data by `DataTransformer.transform()`.

## Data Transformer

Data Transformer is an Angular Service that encapsulates the algorithm of how the data is transformed after a response is received.

Data Transformer must implement a specific interface (`DataTransformer`) and then be registered to the Data Transformer Module via `DataTransformerModule.withTransformers()`,

```ts
// Module augmentation
import { DataTransformerConfig } from '@spryker/data-transformer';

declare module '@spryker/data-transformer' {
    interface DataTransformerRegistry {
        'custom': CustomDataTransformerConfig;
    }
}

export type CustomDataTransformerData = object;
export type CustomDataTransformerDataT = unknown;

export interface CustomDataTransformerConfig extends DataTransformerConfig {
    property: unknown;
    ...
}

// Service implementation
@Injectable({
    providedIn: 'root',
})
export class CustomDataTransformerService implements 
    DataTransformer<CustomDataTransformerData, CustomDataTransformerDataT> {
    transform(
        data: CustomDataTransformerData,
        config: CustomDataTransformerConfig,
    ): Observable<CustomDataTransformerDataT> {
        ...
    }
}

@NgModule({
    imports: [
        DataTransformerModule.withTransformers({
            custom: CustomDataTransformerService,
        }),
    ],
})
export class RootModule {}
```

The context in which the Data Transformer operates is determined by the local injector where it is being used.

## Interfaces

Below you can find interfaces for the Data Transformer service configuration and Data Transformer type:

```ts
interface DataTransformerService {
    transform(data: unknown, config: DataTransformerConfig): Observable<unknown>;
}

interface DataTransformerConfig {
    type: DataTransformerType;

    // Reserved for types that may have extra configuration
    [extraConfig: string]: unknown;
}

interface DataTransformer<D, DT> {
    transform(
        data: D,
        config: DataTransformerConfig,
        injector?: Injector,
    ): Observable<DT>;
}
```

## Data Transformer types

There are a few common Data Transformers that are available in the UI library as separate packages:

- [Collate](/docs/marketplace/dev/front-end/ui-components-library/data-transformers/collate/) - sorts, filters, and paginates data based on configuration. It has extra extension points:
    - [Data Configurators](/docs/marketplace/dev/front-end/ui-components-library/data-transformers/collate/data-configurators/) - are services that allow configuring re-population data (sorting, pagination, filtering). These services are registered via `CollateDataTransformer.withConfigurators()`. There are a few common Collate Data Configurators that are available:
    - [Filters](/docs/marketplace/dev/front-end/ui-components-library/data-transformers/collate/filters/) - are services that extend the filtering. You need to register them via `CollateDataTransformer.withFilters()`. There are a few common Collate Filters that are available:
- [Array-map](/docs/marketplace/dev/front-end/ui-components-library/data-transformers/array-map.html) - executes another Data Transformer from the config for every object in the array.
- [Chain](/docs/marketplace/dev/front-end/ui-components-library/data-transformers/chain.html) - executes another Data Transformer in sequence via configuration.
- [Date-parse](/docs/marketplace/dev/front-end/ui-components-library/data-transformers/date-parse.html) - parses the string value as a Date ISO into the JS Date Object.
- [Date-serialize](/docs/marketplace/dev/front-end/ui-components-library/data-transformers/date-serialize.html) - serializes JS Date Object into a Date ISO string.
- [Lens](/docs/marketplace/dev/front-end/ui-components-library/data-transformers/lens.html) - updates the nested object by path using another Data Transformer set up with a configuration object.
- [Object-map](/docs/marketplace/dev/front-end/ui-components-library/data-transformers/object-map.html) - executes another Data Transformer from the config for each object in the object.
- [Pluck](/docs/marketplace/dev/front-end/ui-components-library/data-transformers/pluck.html) - selects and returns a nested object by path via configuration.
