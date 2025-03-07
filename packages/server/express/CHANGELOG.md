# @verdaccio/server

## 6.0.0-6-next.42

### Patch Changes

- @verdaccio/api@6.0.0-6-next.36
- @verdaccio/auth@6.0.0-6-next.32
- @verdaccio/core@6.0.0-6-next.53
- @verdaccio/loaders@6.0.0-6-next.22
- @verdaccio/logger@6.0.0-6-next.21
- verdaccio-audit@11.0.0-6-next.16
- @verdaccio/store@6.0.0-6-next.33
- @verdaccio/web@6.0.0-6-next.40
- @verdaccio/config@6.0.0-6-next.53
- @verdaccio/middleware@6.0.0-6-next.32
- @verdaccio/utils@6.0.0-6-next.21

## 6.0.0-6-next.41

### Patch Changes

- @verdaccio/core@6.0.0-6-next.52
- @verdaccio/config@6.0.0-6-next.52
- @verdaccio/api@6.0.0-6-next.35
- @verdaccio/auth@6.0.0-6-next.31
- @verdaccio/loaders@6.0.0-6-next.21
- @verdaccio/logger@6.0.0-6-next.20
- @verdaccio/middleware@6.0.0-6-next.31
- verdaccio-audit@11.0.0-6-next.15
- @verdaccio/store@6.0.0-6-next.32
- @verdaccio/utils@6.0.0-6-next.20
- @verdaccio/web@6.0.0-6-next.39

## 6.0.0-6-next.40

### Patch Changes

- Updated dependencies [a23628be]
- Updated dependencies [4b29d715]
  - @verdaccio/web@6.0.0-6-next.38
  - @verdaccio/api@6.0.0-6-next.34
  - @verdaccio/auth@6.0.0-6-next.30
  - @verdaccio/config@6.0.0-6-next.51
  - @verdaccio/core@6.0.0-6-next.51
  - @verdaccio/middleware@6.0.0-6-next.30
  - verdaccio-audit@11.0.0-6-next.14
  - @verdaccio/loaders@6.0.0-6-next.20
  - @verdaccio/store@6.0.0-6-next.31
  - @verdaccio/logger@6.0.0-6-next.19
  - @verdaccio/utils@6.0.0-6-next.19

## 6.0.0-6-next.39

### Patch Changes

- Updated dependencies [b4cc8001]
  - @verdaccio/api@6.0.0-6-next.33
  - @verdaccio/web@6.0.0-6-next.37
  - @verdaccio/core@6.0.0-6-next.50
  - @verdaccio/config@6.0.0-6-next.50
  - @verdaccio/auth@6.0.0-6-next.29
  - @verdaccio/loaders@6.0.0-6-next.19
  - @verdaccio/logger@6.0.0-6-next.18
  - @verdaccio/middleware@6.0.0-6-next.29
  - verdaccio-audit@11.0.0-6-next.13
  - @verdaccio/store@6.0.0-6-next.30
  - @verdaccio/utils@6.0.0-6-next.18

## 6.0.0-6-next.38

### Patch Changes

- Updated dependencies [ce013d2f]
  - @verdaccio/api@6.0.0-6-next.32
  - @verdaccio/store@6.0.0-6-next.29
  - @verdaccio/web@6.0.0-6-next.36
  - @verdaccio/core@6.0.0-6-next.49
  - @verdaccio/config@6.0.0-6-next.49
  - @verdaccio/auth@6.0.0-6-next.28
  - @verdaccio/loaders@6.0.0-6-next.18
  - @verdaccio/logger@6.0.0-6-next.17
  - @verdaccio/middleware@6.0.0-6-next.28
  - verdaccio-audit@11.0.0-6-next.12
  - @verdaccio/utils@6.0.0-6-next.17

## 6.0.0-6-next.37

### Major Changes

- 9fc2e796: feat(plugins): improve plugin loader

  ### Changes

  - Add scope plugin support to 6.x https://github.com/verdaccio/verdaccio/pull/3227
  - Avoid config collisions https://github.com/verdaccio/verdaccio/issues/928
  - https://github.com/verdaccio/verdaccio/issues/1394
  - `config.plugins` plugin path validations
  - Updated algorithm for plugin loader.
  - improved documentation (included dev)

  ## Features

  - Add scope plugin support to 6.x https://github.com/verdaccio/verdaccio/pull/3227
  - Custom prefix:

  ```
  // config.yaml
  server:
    pluginPrefix: mycompany
  middleware:
    audit:
        foo: 1
  ```

  This configuration will look up for `mycompany-audit` instead `Verdaccio-audit`.

  ## Breaking Changes

  ### sinopia plugins

  - `sinopia` fallback support is removed, but can be restored using `pluginPrefix`

  ### plugin filter

  - method rename `filter_metadata`->`filterMetadata`

  ### Plugin constructor does not merge configs anymore https://github.com/verdaccio/verdaccio/issues/928

  The plugin receives as first argument `config`, which represents the config of the plugin. Example:

  ```
  // config.yaml
  auth:
    plugin:
       foo: 1
       bar: 2

  export class Plugin<T> {
    public constructor(config: T, options: PluginOptions) {
      console.log(config);
      // {foo:1, bar: 2}
   }
  }
  ```

### Patch Changes

- Updated dependencies [43f32687]
- Updated dependencies [9fc2e796]
- Updated dependencies [62c24b63]
  - @verdaccio/api@6.0.0-6-next.31
  - @verdaccio/core@6.0.0-6-next.48
  - @verdaccio/store@6.0.0-6-next.28
  - @verdaccio/auth@6.0.0-6-next.27
  - @verdaccio/config@6.0.0-6-next.48
  - @verdaccio/loaders@6.0.0-6-next.17
  - verdaccio-audit@11.0.0-6-next.11
  - @verdaccio/web@6.0.0-6-next.35
  - @verdaccio/utils@6.0.0-6-next.16
  - @verdaccio/logger@6.0.0-6-next.16
  - @verdaccio/middleware@6.0.0-6-next.27

## 6.0.0-6-next.36

### Patch Changes

- @verdaccio/core@6.0.0-6-next.47
- @verdaccio/config@6.0.0-6-next.47
- @verdaccio/api@6.0.0-6-next.30
- @verdaccio/auth@6.0.0-6-next.26
- @verdaccio/loaders@6.0.0-6-next.16
- @verdaccio/logger@6.0.0-6-next.15
- @verdaccio/middleware@6.0.0-6-next.26
- @verdaccio/store@6.0.0-6-next.27
- @verdaccio/utils@6.0.0-6-next.15
- @verdaccio/web@6.0.0-6-next.34
- verdaccio-audit@11.0.0-6-next.10

## 6.0.0-6-next.35

### Patch Changes

- Updated dependencies [b849128d]
  - @verdaccio/api@6.0.0-6-next.29
  - @verdaccio/core@6.0.0-6-next.8
  - @verdaccio/store@6.0.0-6-next.26
  - @verdaccio/web@6.0.0-6-next.33
  - @verdaccio/auth@6.0.0-6-next.25
  - @verdaccio/config@6.0.0-6-next.17
  - @verdaccio/loaders@6.0.0-6-next.15
  - @verdaccio/logger@6.0.0-6-next.14
  - @verdaccio/middleware@6.0.0-6-next.25
  - @verdaccio/utils@6.0.0-6-next.14
  - verdaccio-audit@11.0.0-6-next.10

## 6.0.0-6-next.34

### Patch Changes

- 351aeeaa: fix(deps): @verdaccio/utils should be a prod dep of local-storage
- Updated dependencies [351aeeaa]
  - @verdaccio/api@6.0.0-6-next.28
  - @verdaccio/auth@6.0.0-6-next.24
  - @verdaccio/core@6.0.0-6-next.7
  - @verdaccio/loaders@6.0.0-6-next.14
  - @verdaccio/logger@6.0.0-6-next.13
  - verdaccio-audit@11.0.0-6-next.10
  - @verdaccio/store@6.0.0-6-next.25
  - @verdaccio/web@6.0.0-6-next.32
  - @verdaccio/middleware@6.0.0-6-next.24
  - @verdaccio/config@6.0.0-6-next.16
  - @verdaccio/utils@6.0.0-6-next.13

## 6.0.0-6-next.33

### Patch Changes

- Updated dependencies [37274e4c]
  - @verdaccio/api@6.0.0-6-next.27
  - @verdaccio/store@6.0.0-6-next.24
  - @verdaccio/web@6.0.0-6-next.31
  - @verdaccio/auth@6.0.0-6-next.23
  - @verdaccio/core@6.0.0-6-next.6
  - @verdaccio/loaders@6.0.0-6-next.13
  - @verdaccio/logger@6.0.0-6-next.12
  - verdaccio-audit@11.0.0-6-next.9

## 6.0.0-6-next.32

### Major Changes

- 292c0a37: feat!: replace deprecated request dependency by got

  This is a big refactoring of the core, fetching dependencies, improve code, more tests and better stability. This is essential for the next release, will take some time but would allow modularize more the core.

  ## Notes

  - Remove deprecated `request` by other `got`, retry improved, custom Agent ( got does not include it built-in)
  - Remove `async` dependency from storage (used by core) it was linked with proxy somehow safe to remove now
  - Refactor with promises instead callback wherever is possible
  - ~Document the API~
  - Improve testing, integration tests
  - Bugfix
  - Clean up old validations
  - Improve performance

  ## 💥 Breaking changes

  - Plugin API methods were callbacks based are returning promises, this will break current storage plugins, check documentation for upgrade.
  - Write Tarball, Read Tarball methods parameters change, a new set of options like `AbortController` signals are being provided to the `addAbortSignal` can be internally used with Streams when a request is aborted. eg: `addAbortSignal(signal, fs.createReadStream(pathName));`
  - `@verdaccio/streams` stream abort support is legacy is being deprecated removed
  - Remove AWS and Google Cloud packages for future refactoring [#2574](https://github.com/verdaccio/verdaccio/pull/2574).

### Minor Changes

- 00d1d2a1: chore: env variable for launch fastify

  - Update fastify to major release `v4.3.0`
  - Update CLI launcher

  via CLI

  ```
  VERDACCIO_SERVER=fastify verdaccio
  ```

  with docker

  ```
  docker run -it --rm --name verdaccio \
    -e "VERDACCIO_SERVER=8080" -p 8080:8080 \
    -e "VERDACCIO_SERVER=fastify" \
    verdaccio/verdaccio
  ```

### Patch Changes

- Updated dependencies [292c0a37]
- Updated dependencies [a3a209b5]
- Updated dependencies [00d1d2a1]
  - @verdaccio/api@6.0.0-6-next.26
  - @verdaccio/auth@6.0.0-6-next.23
  - @verdaccio/config@6.0.0-6-next.15
  - @verdaccio/core@6.0.0-6-next.6
  - @verdaccio/loaders@6.0.0-6-next.13
  - @verdaccio/logger@6.0.0-6-next.12
  - @verdaccio/middleware@6.0.0-6-next.23
  - verdaccio-audit@11.0.0-6-next.9
  - @verdaccio/store@6.0.0-6-next.23
  - @verdaccio/utils@6.0.0-6-next.12
  - @verdaccio/web@6.0.0-6-next.30

## 6.0.0-6-next.31

### Patch Changes

- Updated dependencies [a828a5f6]
  - @verdaccio/web@6.0.0-6-next.29
  - @verdaccio/api@6.0.0-6-next.25
  - @verdaccio/store@6.0.0-6-next.22

## 6.0.0-6-next.30

### Patch Changes

- Updated dependencies [d43894e8]
- Updated dependencies [d08fe29d]
  - @verdaccio/config@6.0.0-6-next.14
  - @verdaccio/web@6.0.0-6-next.28
  - @verdaccio/api@6.0.0-6-next.25
  - @verdaccio/auth@6.0.0-6-next.22
  - @verdaccio/loaders@6.0.0-6-next.12
  - @verdaccio/store@6.0.0-6-next.22
  - @verdaccio/core@6.0.0-6-next.5
  - @verdaccio/logger@6.0.0-6-next.11
  - verdaccio-audit@11.0.0-6-next.8
  - @verdaccio/middleware@6.0.0-6-next.22

## 6.0.0-6-next.29

### Major Changes

- 82cb0f2b: feat!: config.logs throw an error, logging config not longer accept array or logs property

  ### 💥 Breaking change

  This is valid

  ```yaml
  log: { type: stdout, format: pretty, level: http }
  ```

  This is invalid

  ```yaml
  logs: { type: stdout, format: pretty, level: http }
  ```

  or

  ```yaml
  logs:
    - [{ type: stdout, format: pretty, level: http }]
  ```

### Minor Changes

- 5167bb52: feat: ui search support for remote, local and private packages

  The command `npm search` search globally and return all matches, with this improvement the user interface
  is powered with the same capabilities.

  The UI also tag where is the origin the package with a tag, also provide the latest version and description of the package.

### Patch Changes

- Updated dependencies [82cb0f2b]
- Updated dependencies [5167bb52]
  - @verdaccio/api@6.0.0-6-next.24
  - @verdaccio/config@6.0.0-6-next.13
  - @verdaccio/core@6.0.0-6-next.5
  - @verdaccio/logger@6.0.0-6-next.11
  - @verdaccio/web@6.0.0-6-next.27
  - @verdaccio/store@6.0.0-6-next.21
  - @verdaccio/auth@6.0.0-6-next.21
  - @verdaccio/loaders@6.0.0-6-next.12
  - @verdaccio/middleware@6.0.0-6-next.21
  - @verdaccio/utils@6.0.0-6-next.11
  - verdaccio-audit@11.0.0-6-next.8

## 6.0.0-6-next.28

### Patch Changes

- Updated dependencies [31d661c7]
  - @verdaccio/loaders@6.0.0-6-next.11
  - @verdaccio/auth@6.0.0-6-next.20
  - @verdaccio/store@6.0.0-6-next.20
  - @verdaccio/web@6.0.0-6-next.26
  - @verdaccio/api@6.0.0-6-next.23
  - @verdaccio/middleware@6.0.0-6-next.20

## 6.0.0-6-next.27

### Patch Changes

- Updated dependencies [aeff267d]
  - @verdaccio/auth@6.0.0-6-next.19
  - @verdaccio/api@6.0.0-6-next.22
  - @verdaccio/middleware@6.0.0-6-next.19
  - @verdaccio/web@6.0.0-6-next.25

## 6.0.0-6-next.26

### Patch Changes

- Updated dependencies [b78f3525]
  - @verdaccio/logger@6.0.0-6-next.10
  - @verdaccio/api@6.0.0-6-next.21
  - @verdaccio/auth@6.0.0-6-next.18
  - @verdaccio/loaders@6.0.0-6-next.10
  - @verdaccio/middleware@6.0.0-6-next.18
  - @verdaccio/store@6.0.0-6-next.19
  - @verdaccio/web@6.0.0-6-next.24

## 6.0.0-6-next.25

### Minor Changes

- 048ac95e: feat: align with v5 ui endpoints and ui small bugfix

### Patch Changes

- Updated dependencies [048ac95e]
- Updated dependencies [730b5d8c]
  - @verdaccio/web@6.0.0-6-next.23
  - @verdaccio/logger@6.0.0-6-next.9
  - @verdaccio/api@6.0.0-6-next.20
  - @verdaccio/auth@6.0.0-6-next.17
  - @verdaccio/loaders@6.0.0-6-next.9
  - @verdaccio/middleware@6.0.0-6-next.17
  - @verdaccio/store@6.0.0-6-next.18

## 6.0.0-6-next.24

### Major Changes

- a828271d: refactor: download manifest endpoint and integrate fastify

  Much simpler API for fetching a package

  ```
   const manifest = await storage.getPackageNext({
        name,
        uplinksLook: true,
        req,
        version: queryVersion,
        requestOptions,
   });
  ```

  > not perfect, the `req` still is being passed to the proxy (this has to be refactored at proxy package) and then removed from here, in proxy we pass the request instance to the `request` library.

  ### Details

  - `async/await` sugar for getPackage()
  - Improve and reuse code between current implementation and new fastify endpoint (add scaffolding for request manifest)
  - Improve performance
  - Add new tests

  ### Breaking changes

  All storage plugins will stop to work since the storage uses `getPackageNext` method which is Promise based, I won't replace this now because will force me to update all plugins, I'll follow up in another PR. Currently will throw http 500

### Patch Changes

- Updated dependencies [a828271d]
- Updated dependencies [24b9be02]
- Updated dependencies [e75c0a3b]
- Updated dependencies [000d4374]
- Updated dependencies [b13a3fef]
  - @verdaccio/api@6.0.0-6-next.19
  - @verdaccio/store@6.0.0-6-next.17
  - @verdaccio/utils@6.0.0-6-next.10
  - @verdaccio/core@6.0.0-6-next.4
  - @verdaccio/middleware@6.0.0-6-next.16
  - verdaccio-audit@11.0.0-6-next.8
  - @verdaccio/web@6.0.0-6-next.22
  - @verdaccio/logger@6.0.0-6-next.8
  - @verdaccio/auth@6.0.0-6-next.16
  - @verdaccio/config@6.0.0-6-next.12
  - @verdaccio/loaders@6.0.0-6-next.8

## 6.0.0-6-next.23

### Patch Changes

- Updated dependencies [f86c31ed]
- Updated dependencies [20c9e43e]
  - @verdaccio/store@6.0.0-6-next.16
  - @verdaccio/utils@6.0.0-6-next.9
  - @verdaccio/web@6.0.0-6-next.21
  - @verdaccio/auth@6.0.0-6-next.15
  - @verdaccio/api@6.0.0-6-next.18
  - @verdaccio/config@6.0.0-6-next.11
  - @verdaccio/middleware@6.0.0-6-next.15
  - @verdaccio/loaders@6.0.0-6-next.7

## 6.0.0-6-next.22

### Patch Changes

- Updated dependencies [6c1eb021]
  - @verdaccio/core@6.0.0-6-next.3
  - @verdaccio/logger@6.0.0-6-next.7
  - @verdaccio/api@6.0.0-6-next.17
  - @verdaccio/auth@6.0.0-6-next.14
  - @verdaccio/config@6.0.0-6-next.10
  - @verdaccio/loaders@6.0.0-6-next.7
  - @verdaccio/middleware@6.0.0-6-next.14
  - @verdaccio/store@6.0.0-6-next.15
  - @verdaccio/utils@6.0.0-6-next.8
  - @verdaccio/web@6.0.0-6-next.20

## 6.0.0-6-next.21

### Major Changes

- 794af76c: Remove Node 12 support

  - We need move to the new `undici` and does not support Node.js 12

### Minor Changes

- 154b2ecd: refactor: remove @verdaccio/commons-api in favor @verdaccio/core and remove duplications

### Patch Changes

- Updated dependencies [794af76c]
- Updated dependencies [b702ea36]
- Updated dependencies [154b2ecd]
  - @verdaccio/api@6.0.0-6-next.16
  - @verdaccio/auth@6.0.0-6-next.13
  - @verdaccio/config@6.0.0-6-next.9
  - @verdaccio/core@6.0.0-6-next.2
  - @verdaccio/loaders@6.0.0-6-next.6
  - @verdaccio/logger@6.0.0-6-next.6
  - @verdaccio/middleware@6.0.0-6-next.13
  - verdaccio-audit@11.0.0-6-next.7
  - @verdaccio/store@6.0.0-6-next.14
  - @verdaccio/utils@6.0.0-6-next.7
  - @verdaccio/web@6.0.0-6-next.19

## 6.0.0-6-next.20

### Patch Changes

- Updated dependencies [2c594910]
  - @verdaccio/logger@6.0.0-6-next.5
  - @verdaccio/api@6.0.0-6-next.15
  - @verdaccio/auth@6.0.0-6-next.12
  - @verdaccio/loaders@6.0.0-6-next.5
  - @verdaccio/middleware@6.0.0-6-next.12
  - @verdaccio/store@6.0.0-6-next.13
  - @verdaccio/web@6.0.0-6-next.18

## 6.0.0-6-next.19

### Major Changes

- 459b6fa7: refactor: search v1 endpoint and local-database

  - refactor search `api v1` endpoint, improve performance
  - remove usage of `async` dependency https://github.com/verdaccio/verdaccio/issues/1225
  - refactor method storage class
  - create new module `core` to reduce the ammount of modules with utilities
  - use `undici` instead `node-fetch`
  - use `fastify` instead `express` for functional test

  ### Breaking changes

  - plugin storage API changes
  - remove old search endpoint (return 404)
  - filter local private packages at plugin level

  The storage api changes for methods `get`, `add`, `remove` as promise base. The `search` methods also changes and recieves a `query` object that contains all query params from the client.

  ```ts
  export interface IPluginStorage<T> extends IPlugin {
    add(name: string): Promise<void>;
    remove(name: string): Promise<void>;
    get(): Promise<any>;
    init(): Promise<void>;
    getSecret(): Promise<string>;
    setSecret(secret: string): Promise<any>;
    getPackageStorage(packageInfo: string): IPackageStorage;
    search(query: searchUtils.SearchQuery): Promise<searchUtils.SearchItem[]>;
    saveToken(token: Token): Promise<any>;
    deleteToken(user: string, tokenKey: string): Promise<any>;
    readTokens(filter: TokenFilter): Promise<Token[]>;
  }
  ```

### Patch Changes

- Updated dependencies [459b6fa7]
  - @verdaccio/api@6.0.0-6-next.14
  - @verdaccio/auth@6.0.0-6-next.11
  - @verdaccio/config@6.0.0-6-next.8
  - @verdaccio/commons-api@11.0.0-6-next.4
  - verdaccio-audit@11.0.0-6-next.6
  - @verdaccio/store@6.0.0-6-next.12
  - @verdaccio/utils@6.0.0-6-next.6
  - @verdaccio/web@6.0.0-6-next.17
  - @verdaccio/middleware@6.0.0-6-next.11
  - @verdaccio/loaders@6.0.0-6-next.4
  - @verdaccio/logger@6.0.0-6-next.4

## 6.0.0-6-next.18

### Patch Changes

- @verdaccio/auth@6.0.0-6-next.10
- @verdaccio/store@6.0.0-6-next.11
- @verdaccio/api@6.0.0-6-next.13
- @verdaccio/loaders@6.0.0-6-next.4
- @verdaccio/middleware@6.0.0-6-next.10
- @verdaccio/web@6.0.0-6-next.16

## 6.0.0-6-next.17

### Patch Changes

- Updated dependencies [f96b147e]
  - verdaccio-audit@11.0.0-6-next.5
  - @verdaccio/api@6.0.0-6-next.12

## 6.0.0-6-next.16

### Patch Changes

- Updated dependencies [d2c65da9]
  - @verdaccio/utils@6.0.0-6-next.5
  - @verdaccio/api@6.0.0-6-next.12
  - @verdaccio/auth@6.0.0-6-next.9
  - @verdaccio/config@6.0.0-6-next.7
  - @verdaccio/middleware@6.0.0-6-next.9
  - @verdaccio/store@6.0.0-6-next.10
  - @verdaccio/web@6.0.0-6-next.15
  - @verdaccio/loaders@6.0.0-6-next.4

## 6.0.0-6-next.15

### Patch Changes

- Updated dependencies [5ddfa526]
  - @verdaccio/store@6.0.0-6-next.9
  - @verdaccio/web@6.0.0-6-next.14
  - @verdaccio/api@6.0.0-6-next.11

## 6.0.0-6-next.14

### Patch Changes

- Updated dependencies [0da7031e]
  - @verdaccio/web@6.0.0-6-next.13
  - @verdaccio/api@6.0.0-6-next.10
  - @verdaccio/auth@6.0.0-6-next.8
  - @verdaccio/loaders@6.0.0-6-next.4
  - @verdaccio/logger@6.0.0-6-next.4
  - verdaccio-audit@11.0.0-alpha.4
  - @verdaccio/store@6.0.0-6-next.8

## 6.0.0-6-next.13

### Patch Changes

- Updated dependencies [aecbd226]
  - @verdaccio/web@6.0.0-6-next.12
  - @verdaccio/api@6.0.0-6-next.10
  - @verdaccio/auth@6.0.0-6-next.8
  - @verdaccio/loaders@6.0.0-6-next.4
  - @verdaccio/logger@6.0.0-6-next.4
  - verdaccio-audit@11.0.0-alpha.4
  - @verdaccio/store@6.0.0-6-next.8

## 6.0.0-6-next.12

### Patch Changes

- Updated dependencies [1b217fd3]
  - @verdaccio/config@6.0.0-6-next.6
  - @verdaccio/api@6.0.0-6-next.10
  - @verdaccio/auth@6.0.0-6-next.8
  - @verdaccio/loaders@6.0.0-6-next.4
  - @verdaccio/store@6.0.0-6-next.8
  - @verdaccio/web@6.0.0-6-next.11
  - @verdaccio/middleware@6.0.0-6-next.8

## 6.0.0-6-next.11

### Patch Changes

- 19d272d1: fix: restore logger on init

  Enable logger after parse configuration and log the very first step on startup phase.

  ```bash
   warn --- experiments are enabled, it is recommended do not use experiments in production comment out this section to disable it
   info --- support for experiment [token]  is disabled
   info --- support for experiment [search]  is disabled
  (node:50831) Warning: config.logs is deprecated, rename configuration to "config.log"
  (Use `node --trace-warnings ...` to show where the warning was created)
   info --- http address http://localhost:4873/
   info --- version: 6.0.0-6-next.11
   info --- server started
  ```

  - @verdaccio/api@6.0.0-6-next.9
  - @verdaccio/auth@6.0.0-6-next.7
  - @verdaccio/loaders@6.0.0-6-next.4
  - @verdaccio/logger@6.0.0-6-next.4
  - verdaccio-audit@11.0.0-alpha.4
  - @verdaccio/store@6.0.0-6-next.7
  - @verdaccio/web@6.0.0-6-next.10

## 6.0.0-6-next.10

### Patch Changes

- 648575aa: Bug Fixes

  - fix escaped slash in namespaced packages

  #### Related tickets

  https://github.com/verdaccio/verdaccio/pull/2193

- Updated dependencies [1810ed0d]
- Updated dependencies [648575aa]
  - @verdaccio/config@6.0.0-6-next.5
  - @verdaccio/utils@6.0.0-6-next.4
  - @verdaccio/api@6.0.0-6-next.9
  - @verdaccio/auth@6.0.0-6-next.7
  - @verdaccio/loaders@6.0.0-6-next.4
  - @verdaccio/store@6.0.0-6-next.7
  - @verdaccio/web@6.0.0-6-next.10
  - @verdaccio/middleware@6.0.0-6-next.7

## 6.0.0-6-next.9

### Patch Changes

- Updated dependencies [5c5057fc]
  - @verdaccio/config@6.0.0-6-next.4
  - @verdaccio/logger@6.0.0-6-next.4
  - @verdaccio/api@6.0.0-6-next.8
  - @verdaccio/auth@6.0.0-6-next.6
  - @verdaccio/loaders@6.0.0-6-next.4
  - @verdaccio/store@6.0.0-6-next.6
  - @verdaccio/web@6.0.0-6-next.9
  - verdaccio-audit@11.0.0-alpha.4
  - @verdaccio/middleware@6.0.0-6-next.6

## 6.0.0-6-next.8

### Patch Changes

- Updated dependencies [cb2281a5]
  - @verdaccio/store@6.0.0-6-next.5
  - @verdaccio/web@6.0.0-6-next.8
  - @verdaccio/api@6.0.0-6-next.7

## 5.0.0-alpha.7

### Patch Changes

- Updated dependencies [e0b7c4ff]
  - @verdaccio/web@5.0.0-alpha.7
  - @verdaccio/api@5.0.0-alpha.6

## 5.0.0-alpha.6

### Patch Changes

- @verdaccio/auth@5.0.0-alpha.5
- @verdaccio/api@5.0.0-alpha.6
- @verdaccio/middleware@5.0.0-alpha.5
- @verdaccio/web@5.0.0-alpha.6

## 5.0.0-alpha.5

### Major Changes

- f8a50baa: feat: standalone registry with no dependencies

  ## Usage

  To install a server with no dependencies

  ```bash
  npm install -g @verdaccio/standalone
  ```

  with no internet required

  ```bash
  npm install -g ./tarball.tar.gz
  ```

  Bundles htpasswd and audit plugins.

  ### Breaking Change

  It does not allow anymore the `auth` and `middleware` property at config file empty,
  it will fallback to those plugins by default.

### Patch Changes

- Updated dependencies [f8a50baa]
  - @verdaccio/auth@5.0.0-alpha.4
  - verdaccio-audit@10.0.0-alpha.4
  - @verdaccio/api@5.0.0-alpha.5
  - @verdaccio/middleware@5.0.0-alpha.4
  - @verdaccio/web@5.0.0-alpha.5

## 5.0.0-alpha.4

### Patch Changes

- fecbb9be: chore: add release step to private regisry on merge changeset pr
- Updated dependencies [fecbb9be]
  - @verdaccio/api@5.0.0-alpha.4
  - @verdaccio/auth@5.0.0-alpha.3
  - @verdaccio/config@5.0.0-alpha.3
  - @verdaccio/commons-api@10.0.0-alpha.3
  - @verdaccio/loaders@5.0.0-alpha.3
  - @verdaccio/logger@5.0.0-alpha.3
  - @verdaccio/middleware@5.0.0-alpha.3
  - @verdaccio/store@5.0.0-alpha.4
  - @verdaccio/utils@5.0.0-alpha.3
  - @verdaccio/web@5.0.0-alpha.4

## 5.0.0-alpha.3

### Minor Changes

- 54c58d1e: feat: add server rate limit protection to all request

  To modify custom values, use the server settings property.

  ```markdown
  server:

  ## https://www.npmjs.com/package/express-rate-limit#configuration-options

  rateLimit:
  windowMs: 1000
  max: 10000
  ```

  The values are intended to be high, if you want to improve security of your server consider
  using different values.

### Patch Changes

- Updated dependencies [54c58d1e]
  - @verdaccio/api@5.0.0-alpha.3
  - @verdaccio/auth@5.0.0-alpha.2
  - @verdaccio/config@5.0.0-alpha.2
  - @verdaccio/commons-api@10.0.0-alpha.2
  - @verdaccio/loaders@5.0.0-alpha.2
  - @verdaccio/logger@5.0.0-alpha.2
  - @verdaccio/middleware@5.0.0-alpha.2
  - @verdaccio/store@5.0.0-alpha.3
  - @verdaccio/utils@5.0.0-alpha.2
  - @verdaccio/web@5.0.0-alpha.3

## 5.0.0-alpha.2

### Patch Changes

- Updated dependencies [2a327c4b]
  - @verdaccio/api@5.0.0-alpha.2
  - @verdaccio/store@5.0.0-alpha.2
  - @verdaccio/web@5.0.0-alpha.2

## 5.0.0-alpha.1

### Major Changes

- d87fa026: feat!: experiments config renamed to flags

  - The `experiments` configuration is renamed to `flags`. The functionality is exactly the same.

  ```js
  flags: token: false;
  search: false;
  ```

  - The `self_path` property from the config file is being removed in favor of `config_file` full path.
  - Refactor `config` module, better types and utilities

- da1ee9c8: - Replace signature handler for legacy tokens by removing deprecated crypto.createDecipher by createCipheriv

  - Introduce environment variables for legacy tokens

  ### Code Improvements

  - Add debug library for improve developer experience

  ### Breaking change

  - The new signature invalidates all previous tokens generated by Verdaccio 4 or previous versions.
  - The secret key must have 32 characters long.

  ### New environment variables

  - `VERDACCIO_LEGACY_ALGORITHM`: Allows to define the specific algorithm for the token signature which by default is `aes-256-ctr`
  - `VERDACCIO_LEGACY_ENCRYPTION_KEY`: By default, the token stores in the database, but using this variable allows to get it from memory

### Minor Changes

- 26b494cb: feat: add typescript project references settings

  Reading https://ebaytech.berlin/optimizing-multi-package-apps-with-typescript-project-references-d5c57a3b4440 I realized I can use project references to solve the issue to pre-compile modules on develop mode.

  It allows to navigate (IDE) trough the packages without need compile the packages.

  Add two `tsconfig`, one using the previous existing configuration that is able to produce declaration files (`tsconfig.build`) and a new one `tsconfig` which is enables [_projects references_](https://www.typescriptlang.org/docs/handbook/project-references.html).

### Patch Changes

- b57b4338: Enable prerelease mode with **changesets**
- 31af0164: ESLint Warnings Fixed

  Related to issue #1461

  - max-len: most of the sensible max-len errors are fixed
  - no-unused-vars: most of these types of errors are fixed by deleting not needed declarations
  - @typescript-eslint/no-unused-vars: same as above

- Updated dependencies [d87fa026]
- Updated dependencies [42024c34]
- Updated dependencies [da1ee9c8]
- Updated dependencies [26b494cb]
- Updated dependencies [b57b4338]
- Updated dependencies [42dfed78]
- Updated dependencies [add778d5]
- Updated dependencies [31af0164]
  - @verdaccio/api@5.0.0-alpha.1
  - @verdaccio/auth@5.0.0-alpha.1
  - @verdaccio/config@5.0.0-alpha.1
  - @verdaccio/commons-api@10.0.0-alpha.1
  - @verdaccio/loaders@5.0.0-alpha.1
  - @verdaccio/logger@5.0.0-alpha.1
  - @verdaccio/middleware@5.0.0-alpha.1
  - @verdaccio/store@5.0.0-alpha.1
  - @verdaccio/utils@5.0.0-alpha.1
  - @verdaccio/web@5.0.0-alpha.1

## 5.0.0-alpha.1

### Major Changes

- d87fa0268: feat!: experiments config renamed to flags

  - The `experiments` configuration is renamed to `flags`. The functionality is exactly the same.

  ```js
  flags: token: false;
  search: false;
  ```

  - The `self_path` property from the config file is being removed in favor of `config_file` full path.
  - Refactor `config` module, better types and utilities

- da1ee9c82: - Replace signature handler for legacy tokens by removing deprecated crypto.createDecipher by createCipheriv

  - Introduce environment variables for legacy tokens

  ### Code Improvements

  - Add debug library for improve developer experience

  ### Breaking change

  - The new signature invalidates all previous tokens generated by Verdaccio 4 or previous versions.
  - The secret key must have 32 characters long.

  ### New environment variables

  - `VERDACCIO_LEGACY_ALGORITHM`: Allows to define the specific algorithm for the token signature which by default is `aes-256-ctr`
  - `VERDACCIO_LEGACY_ENCRYPTION_KEY`: By default, the token stores in the database, but using this variable allows to get it from memory

### Minor Changes

- 26b494cbd: feat: add typescript project references settings

  Reading https://ebaytech.berlin/optimizing-multi-package-apps-with-typescript-project-references-d5c57a3b4440 I realized I can use project references to solve the issue to pre-compile modules on develop mode.

  It allows to navigate (IDE) trough the packages without need compile the packages.

  Add two `tsconfig`, one using the previous existing configuration that is able to produce declaration files (`tsconfig.build`) and a new one `tsconfig` which is enables [_projects references_](https://www.typescriptlang.org/docs/handbook/project-references.html).

### Patch Changes

- b57b43388: Enable prerelease mode with **changesets**
- 31af01641: ESLint Warnings Fixed

  Related to issue #1461

  - max-len: most of the sensible max-len errors are fixed
  - no-unused-vars: most of these types of errors are fixed by deleting not needed declarations
  - @typescript-eslint/no-unused-vars: same as above

- Updated dependencies [d87fa0268]
- Updated dependencies [42024c346]
- Updated dependencies [da1ee9c82]
- Updated dependencies [26b494cbd]
- Updated dependencies [b57b43388]
- Updated dependencies [42dfed785]
- Updated dependencies [add778d55]
- Updated dependencies [31af01641]
  - @verdaccio/api@5.0.0-alpha.1
  - @verdaccio/auth@5.0.0-alpha.1
  - @verdaccio/config@5.0.0-alpha.1
  - @verdaccio/commons-api@10.0.0-alpha.0
  - @verdaccio/loaders@5.0.0-alpha.1
  - @verdaccio/logger@5.0.0-alpha.1
  - @verdaccio/middleware@5.0.0-alpha.1
  - @verdaccio/store@5.0.0-alpha.1
  - @verdaccio/utils@5.0.0-alpha.1
  - @verdaccio/web@5.0.0-alpha.1
