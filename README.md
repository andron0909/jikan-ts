# jikan-ts

![Language Shield](https://img.shields.io/badge/language-typescript-blue?style=for-the-badge)
![License Shield](https://img.shields.io/badge/license-mit-blueviolet?style=for-the-badge)
![Build Shield](https://img.shields.io/badge/build-passing-brightgreen?style=for-the-badge)
![Coverage Shield](https://img.shields.io/badge/coverage-80%25-yellow?style=for-the-badge)
![Code Style Shield](https://img.shields.io/badge/code%20style-Prettier-magenta?style=for-the-badge)

> Jikan API wrapper for Typescript and Javascript with build in typings.

## Features

- 💅 Fully typed
- ♻ Http Request Cache
- 📄 Configurable Logging
- 📦 ESM with tree shaking support

## Installation

```bash
npm install --save @tutkli/jikan-ts
# or
yarn add @tutkli/jikan-ts # recommended
```

## Basic Example

Using a specific client, like AnimeClient:

```ts
import { AnimeClient } from '@tutkli/jikan-ts';

(async () => {
  const animeClient = new AnimeClient();

  await animeClient
    .getAnimeById(1)
    .then((jikanResponse) => console.log(jikanResponse.data.title)) // will output "Cowboy Bebob"
    .catch((error) => console.error(error));
})();
```

Or, using the JikanClient:

```ts
import { JikanClient } from '@tutkli/jikan-ts';

(async () => {
  const jikanClient = new JikanClient();

  await jikanClient.anime
    .getAnimeById(1)
    .then((jikanResponse) => console.log(jikanResponse.data.title)) // will output "Cowboy Bebob"
    .catch((error) => console.error(error));
})();
```

## Client configuration

Jikan-ts has default cache and logging configurations. If you want to customize any configuration, you can do so by passing `cacheOptions` or `loggerOptions` arguments when instantiating a client.

### Cache Configuration

To use a specific configuration, pass the cacheOptions argument when instantiating a client:

```ts
import {AnimeClient} from '@tutkli/jikan-ts';

const animeClient = new AnimeClient({ 
    cacheOptions: { ... } // your custom axios-cache-interceptor options
  }
);
```

See also: [axios-cache-interceptor Configuration](https://axios-cache-interceptor.js.org/#/pages/configuration).

### Logging Configuration

To enable logging, pass the `loggerOptions` argument with `enabled: true`. You can also customize the styling of the logger with your custom tslog settings.

```ts
import {AnimeClient} from '@tutkli/jikan-ts';

const animeClient = new AnimeClient({ 
    loggerOptions: { 
        enabled: true, // enables logging
        settings: { ... } // [Optional] your custom tslog settings
    } 
  }
);
```

See also: [tslog Settings](https://tslog.js.org/#/?id=settings).

## Available Clients

- AnimeClient
- MangaClient
- TopClient
- JikanClient (Main client)

## Leave you feedback

- Did you find this project useful? [Leave a ⭐](https://github.com/tutkli/jikan-ts)
- Found a problem? [Create an issue 🔎](https://github.com/tutkli/jikan-ts/issues)
- Want to contribute? [Submit a PR 📑](https://github.com/tutkli/jikan-ts/pulls)

