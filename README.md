[![dotenvx](https://dotenvx.com/better-banner.png)](https://dotenvx.com)

*a better dotenv*–from the creator of [`dotenv`](https://github.com/motdotla/dotenv).

* run anywhere (cross-platform)
* multi-environment
* encrypted envs

&nbsp;


### Quickstart [![npm version](https://img.shields.io/npm/v/@dotenvx/dotenvx.svg)](https://www.npmjs.com/package/@dotenvx/dotenvx) [![downloads](https://img.shields.io/npm/dw/@dotenvx/dotenvx)](https://www.npmjs.com/package/@dotenvx/dotenvx) [![test suite](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/motdotenv/bb76445765a9731e7d824a6efdf53524/raw/dotenvxTestCount.json)](https://github.com/dotenvx/dotenvx/tree/main/tests) 

Install and use it in code just like `dotenv`.

```sh
npm install @dotenvx/dotenvx --save
```
```js
// index.js
require('@dotenvx/dotenvx').config()

console.log(`Hello ${process.env.HELLO}`)
```

&nbsp;

or install globally - *unlocks dotenv for any language, framework, or platform!*

<details><summary>with curl 🌐 </summary><br>

```sh
curl -sfS https://dotenvx.sh | sh
dotenvx help
```

[![curl installs](https://img.shields.io/endpoint?url=https://dotenvx.sh/stats/curl&label=curl%20installs)](https://github.com/dotenvx/dotenvx.sh/blob/main/install.sh)

&nbsp;

</details>

<details><summary>with brew 🍺</summary><br>

```sh
brew install dotenvx/brew/dotenvx
dotenvx help
```

[![brew installs](https://img.shields.io/github/downloads/dotenvx/dotenvx/total?label=brew%20installs)](https://github.com/dotenvx/homebrew-brew/blob/main/Formula/dotenvx.rb)

&nbsp;

</details>

<details><summary>with docker 🐳</summary><br>

```sh
docker run -it --rm -v $(pwd):/app dotenv/dotenvx help
```

[![docker pulls](https://img.shields.io/docker/pulls/dotenv/dotenvx)](https://hub.docker.com/r/dotenv/dotenvx)

&nbsp;

</details>

<details><summary>with github releases 🐙</summary><br>

```sh
curl -L -o dotenvx.tar.gz "https://github.com/dotenvx/dotenvx/releases/latest/download/dotenvx-$(uname -s)-$(uname -m).tar.gz"
tar -xzf dotenvx.tar.gz
./dotenvx help
```

[![github releases](https://img.shields.io/github/downloads/dotenvx/dotenvx/total)](https://github.com/dotenvx/dotenvx/releases)

&nbsp;

</details>


<details><summary>or with windows 🟦🟩🟥🟨</summary><br>

```sh
winget install dotenvx
dotenvx help
```

</details>

&nbsp;

## Run Anywhere

```sh
$ echo "HELLO=World" > .env
$ echo "console.log('Hello ' + process.env.HELLO)" > index.js

$ node index.js
Hello undefined # without dotenvx

$ dotenvx run -- node index.js
Hello World # with dotenvx
> :-D
```

see [extended quickstart guide](https://dotenvx.com/docs/quickstart)

More examples

* <details><summary>TypeScript 📘</summary><br>

  ```json
  // package.json
  {
    "type": "module",
    "dependencies": {
      "chalk": "^5.3.0"
    }
  }
  ```

  ```js
  // index.ts
  import chalk from 'chalk'
  console.log(chalk.blue(`Hello ${process.env.HELLO}`))
  ```

  ```sh
  $ npm install
  $ echo "HELLO=World" > .env

  $ dotenvx run -- npx tsx index.ts
  Hello World
  ```

  </details>
* <details><summary>Deno 🦕</summary><br>

  ```sh
  $ echo "HELLO=World" > .env
  $ echo "console.log('Hello ' + Deno.env.get('HELLO'))" > index.ts

  $ deno run --allow-env index.ts
  Hello undefined

  $ dotenvx run -- deno run --allow-env index.ts
  Hello World
  ```

  </details>
* <details><summary>Bun 🥟</summary><br>

  ```sh
  $ echo "HELLO=Test" > .env.test
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ bun index.js
  Hello undefined

  $ dotenvx run -f .env.test -- bun index.js
  Hello Test
  ```

  </details>
* <details><summary>Python 🐍</summary><br>

  ```sh
  $ echo "HELLO=World" > .env
  $ echo 'import os;print("Hello " + os.getenv("HELLO", ""))' > index.py

  $ dotenvx run -- python3 index.py
  Hello World
  ```

  see [extended python guide](https://dotenvx.com/docs/quickstart)

  </details>
* <details><summary>PHP 🐘</summary><br>

  ```sh
  $ echo "HELLO=World" > .env
  $ echo '<?php echo "Hello {$_SERVER["HELLO"]}\n";' > index.php

  $ dotenvx run -- php index.php
  Hello World
  ```

  see [extended php guide](https://dotenvx.com/docs/quickstart)

  </details>
* <details><summary>Ruby 💎</summary><br>

  ```sh
  $ echo "HELLO=World" > .env
  $ echo 'puts "Hello #{ENV["HELLO"]}"' > index.rb

  $ dotenvx run -- ruby index.rb
  Hello World
  ```

  see [extended ruby guide](https://dotenvx.com/docs/quickstart)

  </details>
* <details><summary>Go 🐹</summary><br>

  ```sh
  $ echo "HELLO=World" > .env
  $ echo 'package main; import ("fmt"; "os"); func main() { fmt.Printf("Hello %s\n", os.Getenv("HELLO")) }' > main.go

  $ dotenvx run -- go run main.go
  Hello World
  ```

  see [extended go guide](https://dotenvx.com/docs/quickstart)

  </details>
* <details><summary>Rust 🦀</summary><br>

  ```sh
  $ echo "HELLO=World" > .env
  $ echo 'fn main() {let hello = std::env::var("HELLO").unwrap_or("".to_string());println!("Hello {hello}");}' > src/main.rs

  $ dotenvx run -- cargo run
  Hello World
  ```

  see [extended rust guide](https://dotenvx.com/docs/quickstart)

  </details>
* <details><summary>Java ☕️</summary><br>

  ```sh
  $ echo "HELLO=World" > .env
  $ echo 'public class Index { public static void main(String[] args) { System.out.println("Hello " + System.getenv("HELLO")); } }' > index.java

  $ dotenvx run -- java index.java
  Hello World
  ```

  </details>
* <details><summary>Clojure 🌿</summary><br>

  ```sh
  $ echo "HELLO=World" > .env
  $ echo '(println "Hello" (System/getenv "HELLO"))' > index.clj

  $ dotenvx run -- clojure -M index.clj
  Hello World
  ```

  </details>
* <details><summary>.NET 🔵</summary><br>

  ```sh
  $ dotnet new console -n HelloWorld -o HelloWorld
  $ cd HelloWorld
  $ echo "HELLO=World" | Out-File -FilePath .env -Encoding utf8
  $ echo 'Console.WriteLine($"Hello {Environment.GetEnvironmentVariable("HELLO")}");' > Program.cs

  $ dotenvx run -- dotnet run
  Hello World
  ```

  </details>
* <details><summary>Bash 🖥️</summary><br>

  ```sh
  $ echo "HELLO=World" > .env

  $ dotenvx run --quiet -- sh -c 'echo Hello $HELLO'
  Hello World
  ```

  </details>
* <details><summary>Fish 🐠</summary><br>

  ```sh
  $ echo "HELLO=World" > .env

  $ dotenvx run --quiet -- sh -c 'echo Hello $HELLO'
  Hello World
  ```

  </details>
* <details><summary>Cron ⏰</summary><br>

  ```sh
  # run every day at 8am
  0 8 * * * dotenvx run -- /path/to/myscript.sh
  ```

  </details>
* <details><summary>Frameworks ▲</summary><br>

  ```sh
  $ dotenvx run -- next dev
  $ dotenvx run -- npm start
  $ dotenvx run -- bin/rails s
  $ dotenvx run -- php artisan serve
  ```

  see [framework guides](https://dotenvx.com/docs#frameworks)

  </details>
* <details><summary>Docker 🐳</summary><br>

  ```sh
  $ docker run -it --rm -v $(pwd):/app dotenv/dotenvx run -- node index.js
  ```

  Or in any image:

  ```sh
  FROM node:latest
  RUN echo "HELLO=World" > .env && echo "console.log('Hello ' + process.env.HELLO)" > index.js
  RUN curl -fsS https://dotenvx.sh/install.sh | sh
  CMD ["dotenvx", "run", "--", "echo", "Hello $HELLO"]
  ```

  see [docker guide](https://dotenvx.com/docs/platforms/docker)

  </details>
* <details><summary>CI/CDs 🐙</summary><br>

  ```yaml
  name: build
  on: [push]
  jobs:
    build:
      runs-on: ubuntu-latest
      steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: 16
      - run: curl -fsS https://dotenvx.sh/install.sh | sh
      - run: dotenvx run -- node build.js
        env:
          DOTENV_KEY: ${{ secrets.DOTENV_KEY }}
  ```

  see [github actions guide](https://dotenvx.com/docs/cis/github-actions)

  </details>
* <details><summary>Platforms</summary><br>

  ```sh
  # heroku
  heroku buildpacks:add https://github.com/dotenvx/heroku-buildpack-dotenvx

  # docker
  RUN curl -fsS https://dotenvx.sh/install.sh | sh

  # vercel
  npm install @dotenvx/dotenvx --save
  ```

  see [platform guides](https://dotenvx.com/docs#platforms)

  </details>
* <details><summary>Process Managers</summary><br>

  ```js
  // pm2
  "scripts": {
    "start": "dotenvx run -- pm2-runtime start ecosystem.config.js --env production"
  },
  ```

  see [process manager guides](https://dotenvx.com/docs#process-managers)

  </details>
* <details><summary>npx</summary><br>

  ```sh
  # alternatively use npx
  $ npx @dotenvx/dotenvx run -- node index.js
  $ npx @dotenvx/dotenvx run -- next dev
  $ npx @dotenvx/dotenvx run -- npm start
  ```

  </details>
* <details><summary>npm</summary><br>

  ```sh
  $ npm install @dotenvx/dotenvx --save
  ```

  ```json
  {
    "scripts": {
      "start": "./node_modules/.bin/dotenvx run -- node index.js"
    },
    "dependencies": {
      "@dotenvx/dotenvx": "^0.5.0"
    }
  }
  ```

  ```sh
  $ npm run start

  > start
  > ./node_modules/.bin/dotenvx run -- node index.js

  [dotenvx][info] loading env (1) from .env
  Hello World
  ```

  </details>
* <details><summary>Git</summary><br>

  ```sh
  # use as a git submodule
  $ git dotenvx run -- node index.js
  $ git dotenvx run -- next dev
  $ git dotenvx run -- npm start
  ```

  </details>
* <details><summary>Variable Expansion</summary><br>

  Reference and expand variables already on your machine for use in your .env file.

  ```ini
  # .env
  USERNAME="username"
  DATABASE_URL="postgres://${USERNAME}@localhost/my_database"
  ```
  ```js
  // index.js
  console.log('DATABASE_URL', process.env.DATABASE_URL)
  ```
  ```sh
  $ dotenvx run --debug -- node index.js
  [dotenvx@0.14.1] injecting env (2) from .env
  DATABASE_URL postgres://username@localhost/my_database
  ```

  </details>
* <details><summary>Command Substitution</summary><br>

  Add the output of a command to one of your variables in your .env file.

  ```ini
  # .env
  DATABASE_URL="postgres://$(whoami)@localhost/my_database"
  ```
  ```js
  // index.js
  console.log('DATABASE_URL', process.env.DATABASE_URL)
  ```
  ```sh
  $ dotenvx run --debug -- node index.js
  [dotenvx@0.14.1] injecting env (1) from .env
  DATABASE_URL postgres://yourusername@localhost/my_database
  ```

  </details>


&nbsp;

## Multiple Environments

> Create a `.env.production` file and use `-f` to load it. It's straightforward, yet flexible.
```sh
$ echo "HELLO=production" > .env.production
$ echo "console.log('Hello ' + process.env.HELLO)" > index.js

$ dotenvx run -f .env.production -- node index.js
[dotenvx][info] loading env (1) from .env.production
Hello production
> ^^
```

More examples

* <details><summary>multiple `.env` files</summary><br>

  ```sh
  $ echo "HELLO=local" > .env.local

  $ echo "HELLO=World" > .env

  $ dotenvx run -f .env.local -f .env -- node index.js
  [dotenvx][info] loading env (1) from .env.local,.env
  Hello local
  ```

  </details>

* <details><summary>`--overload` flag</summary><br>

  ```sh
  $ echo "HELLO=local" > .env.local

  $ echo "HELLO=World" > .env

  $ dotenvx run -f .env.local -f .env --overload -- node index.js
  [dotenvx][info] loading env (1) from .env.local,.env
  Hello World
  ```

* <details><summary>`--verbose` flag</summary><br>

  ```sh
  $ echo "HELLO=production" > .env.production

  $ dotenvx run -f .env.production --verbose -- node index.js
  [dotenvx][verbose] injecting env from /path/to/.env.production
  [dotenvx][verbose] HELLO set
  [dotenvx][info] loading env (1) from .env.production
  Hello production
  ```

* <details><summary>`--debug` flag</summary><br>

  ```sh
  $ echo "HELLO=production" > .env.production

  $ dotenvx run -f .env.production --debug -- node index.js
  [dotenvx][debug] configuring options
  [dotenvx][debug] {"envFile":[".env.production"]}
  [dotenvx][verbose] injecting env from /path/to/.env.production
  [dotenvx][debug] reading env from /path/to/.env.production
  [dotenvx][debug] parsing env from /path/to/.env.production
  [dotenvx][debug] {"HELLO":"production"}
  [dotenvx][debug] writing env from /path/to/.env.production
  [dotenvx][verbose] HELLO set
  [dotenvx][debug] HELLO set to production
  [dotenvx][info] loading env (1) from .env.production
  Hello production
  ```

  </details>
* <details><summary>`--quiet` flag</summary><br>

  Use `--quiet` to suppress all output (except errors).

  ```sh
  $ echo "HELLO=production" > .env.production

  $ dotenvx run -f .env.production --quiet -- node index.js
  Hello production
  ```

  </details>
* <details><summary>`--log-level` flag</summary><br>

  Set `--log-level` to whatever you wish. For example, to supress warnings (risky), set log level to `error`:

  ```sh
  $ echo "HELLO=production" > .env.production

  $ dotenvx run -f .env.production --log-level=error -- node index.js
  Hello production
  ```

  Available log levels are `error, warn, info, verbose, debug, silly`

  </details>
* <details><summary>`--convention` flag</summary><br>

  Load envs using [Next.js' convention](https://nextjs.org/docs/pages/building-your-application/configuring/environment-variables#environment-variable-load-order). Set `--convention` to `nextjs`:

  ```sh
  $ echo "HELLO=development local" > .env.development.local
  $ echo "HELLO=local" > .env.local
  $ echo "HELLO=development" > .env.development
  $ echo "HELLO=env" > .env

  $ dotenvx run --convention=nextjs -- node index.js
  Hello development local
  ```

  (more conventions available upon request)

  </details>

&nbsp;

## Encryption

> Add encryption to your `.env` files with a single command. Use `dotenvx encrypt`.

```sh
$ dotenvx encrypt
✔ encrypted (.env)
```

![encrypted .env](https://github.com/dotenvx/dotenvx/assets/3848/2a8c3dc5-cd8e-4a08-8a59-c24d0535c81a)

> A `DOTENV_PUBLIC_KEY` (encryption key) and a `DOTENV_PRIVATE_KEY` (decryption key) are generated using the same public-key cryptography as [Bitcoin](https://en.bitcoin.it/wiki/Secp256k1).

More examples

* <details><summary>`.env`</summary><br>

  ```sh
  $ echo "HELLO=World" > .env
  $ dotenvx encrypt
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ dotenvx run -- node index.js
  [dotenvx] injecting env (2) from .env
  Hello World
  ```

  </details>
* <details><summary>`.env.production`</summary><br>

  ```sh
  $ echo "HELLO=Production" > .env.production
  $ dotenvx encrypt -f .env.production
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ DOTENV_PRIVATE_KEY_PRODUCTION="<.env.production private key>" dotenvx run -- node index.js
  [dotenvx] injecting env (2) from .env.production
  Hello Production
  ```

  Note the `DOTENV_PRIVATE_KEY_PRODUCTION` ends with `_PRODUCTION`. This instructs `dotenvx run` to load the `.env.production` file.

  </details>
* <details><summary>`.env.ci`</summary><br>

  ```sh
  $ echo "HELLO=Ci" > .env.ci
  $ dotenvx encrypt -f .env.ci
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ DOTENV_PRIVATE_KEY_CI="<.env.ci private key>" dotenvx run -- node index.js
  [dotenvx] injecting env (2) from .env.ci
  Hello Ci
  ```

  Note the `DOTENV_PRIVATE_KEY_CI` ends with `_CI`. This instructs `dotenvx run` to load the `.env.ci` file. See the pattern?

  </details>
* <details><summary>combine multiple encrypted .env files</summary><br>

  ```sh
  $ dotenvx set HELLO World -f .env
  $ dotenvx set HELLO Production -f .env.production
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ DOTENV_PRIVATE_KEY="<.env private key>" DOTENV_PRIVATE_KEY_PRODUCTION="<.env.production private key>" dotenvx run -- node index.js
  [dotenvx] injecting env (3) from .env, .env.production
  Hello World
  ```

  Note the `DOTENV_PRIVATE_KEY` instructs `dotenvx run` to load the `.env` file and the `DOTENV_PRIVATE_KEY_PRODUCTION` instructs it to load the `.env.production` file. See the pattern?

  </details>
* <details><summary>combine multiple encrypted .env files for monorepo</summary><br>

  ```sh
  $ mkdir app1
  $ mkdir app2
  $ dotenvx set HELLO app1 -f app1/.env.ci
  $ dotenvx set HELLO app2 -f app2/.env.ci
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ DOTENV_PRIVATE_KEY_CI="<app1/privat ci key>,<app2/private ci key>" dotenvx run -f app1/.env.ci -f app2/.env.ci -- node index.js
  [dotenvx] injecting env (2) from app1/.env.ci,app2/.env.ci
  Hello app1

  $ DOTENV_PRIVATE_KEY_CI="<app1/privat ci key>,<app2/private ci key>" dotenvx run -f app1/.env.ci -f app2/.env.ci --overload -- node index.js
  [dotenvx] injecting env (2) from app1/.env.ci,app2/.env.ci
  Hello app2
  ```

  Note the `DOTENV_PRIVATE_KEY_CI` (and any `DOTENV_PRIVATE_KEY*`) can take multiple private keys by simply comma separating them.

  </details>
* <details><summary>`--stdout`</summary><br>

  ```sh
  $ echo "HELLO=World" > .env
  $ dotenvx encrypt --stdout
  $ dotenvx encrypt --stdout > .env.encrypted
  ```

  </details>

* <details><summary>other curves</summary><br>

  > `secp256k1` is a well-known and battle tested curve, in use with Bitcoin and other cryptocurrencies, but we are open to adding support for more curves.
  > 
  > If your organization's compliance department requires [NIST approved curves](https://csrc.nist.gov/projects/elliptic-curve-cryptography) or other curves like `curve25519`, please reach out at [security@dotenvx.com](mailto:security@dotenvx.com).

  </details>

&nbsp;

## Advanced

> Become a `dotenvx` power user.
>

* <details><summary>`run` - Variable Expansion</summary><br>

  Reference and expand variables already on your machine for use in your .env file.

  ```ini
  # .env
  USERNAME="username"
  DATABASE_URL="postgres://${USERNAME}@localhost/my_database"
  ```
  ```js
  // index.js
  console.log('DATABASE_URL', process.env.DATABASE_URL)
  ```
  ```sh
  $ dotenvx run --debug -- node index.js
  [dotenvx] injecting env (2) from .env
  DATABASE_URL postgres://username@localhost/my_database
  ```

  </details>
* <details><summary>`run` - Command Substitution</summary><br>

  Add the output of a command to one of your variables in your .env file.

  ```ini
  # .env
  DATABASE_URL="postgres://$(whoami)@localhost/my_database"
  ```
  ```js
  // index.js
  console.log('DATABASE_URL', process.env.DATABASE_URL)
  ```
  ```sh
  $ dotenvx run --debug -- node index.js
  [dotenvx] injecting env (1) from .env
  DATABASE_URL postgres://yourusername@localhost/my_database
  ```

  </details>
* <details><summary>`run` - Shell Expansion</summary><br>

  Prevent your shell from expanding inline `$VARIABLES` before dotenvx has a chance to inject it. Use a subshell.

  ```sh
  $ dotenvx run --env="HELLO=World" -- sh -c 'echo Hello $HELLO'
  Hello World
  ```

  </details>
* <details><summary>`run` - multiple `-f` flags</summary><br>

  Compose multiple `.env` files for environment variables loading, as you need.

  ```sh
  $ echo "HELLO=local" > .env.local
  $ echo "HELLO=World" > .env
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ dotenvx run -f .env.local -f .env -- node index.js
  [dotenvx] injecting env (1) from .env.local, .env
  Hello local
  ```

  </details>
* <details><summary>`run --env HELLO=String`</summary><br>

  Set environment variables as a simple `KEY=value` string pair.

  ```sh
  $ echo "HELLO=World" > .env
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ dotenvx run --env HELLO=String -f .env -- node index.js
  [dotenvx] injecting env (1) from .env, and --env flag
  Hello String
  ```

  </details>
* <details><summary>`run --overload`</summary><br>

  Override existing env variables. These can be variables already on your machine or variables loaded as files consecutively. The last variable seen will 'win'.

  ```sh
  $ echo "HELLO=local" > .env.local
  $ echo "HELLO=World" > .env
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ dotenvx run -f .env.local -f .env --overload -- node index.js
  [dotenvx] injecting env (1) from .env.local, .env
  Hello World
  ```

  </details>
* <details><summary>`DOTENV_PRIVATE_KEY=key run`</summary><br>
  
  Decrypt your encrypted `.env` by setting `DOTENV_PRIVATE_KEY` before `dotenvx run`.

  ```sh
  $ touch .env
  $ dotenvx set HELLO encrypted
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  # check your .env.keys files for your privateKey
  $ DOTENV_PRIVATE_KEY="122...0b8" dotenvx run -- node index.js
  [dotenvx] injecting env (2) from .env
  Hello encrypted
  ```

  </details>
* <details><summary>`DOTENV_PRIVATE_KEY_PRODUCTION=key run`</summary><br>

  Decrypt your encrypted `.env.production` by setting `DOTENV_PRIVATE_KEY_PRODUCTION` before `dotenvx run`. Alternatively, this can be already set on your server or cloud provider.

  ```sh
  $ touch .env.production
  $ dotenvx set HELLO "production encrypted" -f .env.production
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  # check .env.keys for your privateKey
  $ DOTENV_PRIVATE_KEY_PRODUCTION="122...0b8" dotenvx run -- node index.js
  [dotenvx] injecting env (2) from .env.production
  Hello production encrypted
  ```

  Note the `DOTENV_PRIVATE_KEY_PRODUCTION` ends with `_PRODUCTION`. This instructs dotenvx run to load the `.env.production` file.

  </details>
* <details><summary>`DOTENV_PRIVATE_KEY_CI=key dotenvx run`</summary><br>

  Decrypt your encrypted `.env.ci` by setting `DOTENV_PRIVATE_KEY_CI` before `dotenvx run`. Alternatively, this can be already set on your server or cloud provider.

  ```sh
  $ touch .env.ci
  $ dotenvx set HELLO "ci encrypted" -f .env.production
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  # check .env.keys for your privateKey
  $ DOTENV_PRIVATE_KEY_CI="122...0b8" dotenvx run -- node index.js
  [dotenvx] injecting env (2) from .env.ci
  Hello ci encrypted
  ```

  Note the `DOTENV_PRIVATE_KEY_CI` ends with `_CI`. This instructs dotenvx run to load the `.env.ci` file. See the pattern?

  </details>
* <details><summary>`DOTENV_PRIVATE_KEY=key DOTENV_PRIVATE_KEY_PRODUCTION=key run` - Combine Multiple</summary><br>

  Decrypt your encrypted `.env` and `.env.production` files by setting `DOTENV_PRIVATE_KEY` and `DOTENV_PRIVATE_KEY_PRODUCTION` before `dotenvx run`. 

  ```sh
  $ touch .env
  $ touch .env.production
  $ dotenvx set HELLO encrypted
  $ dotenvx set HELLO "production encrypted" -f .env.production
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  # check .env.keys for your privateKeys
  $ DOTENV_PRIVATE_KEY="122...0b8" DOTENV_PRIVATE_KEY_PRODUCTION="122...0b8" dotenvx run -- node index.js
  [dotenvx] injecting env (3) from .env, .env.production
  Hello encrypted

  $ DOTENV_PRIVATE_KEY_PRODUCTION="122...0b8" DOTENV_PRIVATE_KEY="122...0b8" dotenvx run -- node index.js
  [dotenvx] injecting env (3) from .env.production, .env
  Hello production encrypted
  ```

  Compose any encrypted files you want this way. As long as a `DOTENV_PRIVATE_KEY_${environment}` is set, the values from `.env.${environment}` will be decrypted at runtime.

  </details>
* <details><summary>`run --verbose`</summary><br>

  Set log level to `verbose`. ([log levels](https://docs.npmjs.com/cli/v8/using-npm/logging#setting-log-levels))

  ```sh
  $ echo "HELLO=production" > .env.production
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ dotenvx run -f .env.production --verbose -- node index.js
  loading env from .env.production (/path/to/.env.production)
  HELLO set
  [dotenvx] injecting env (1) from .env.production
  Hello production
  ```

  </details>
* <details><summary>`run --debug`</summary><br>

  Set log level to `debug`. ([log levels](https://docs.npmjs.com/cli/v8/using-npm/logging#setting-log-levels))

  ```sh
  $ echo "HELLO=production" > .env.production
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ dotenvx run -f .env.production --debug -- node index.js
  process command [node index.js]
  options: {"env":[],"envFile":[".env.production"]}
  loading env from .env.production (/path/to/.env.production)
  {"HELLO":"production"}
  HELLO set
  HELLO set to production
  [dotenvx] injecting env (1) from .env.production
  executing process command [node index.js]
  expanding process command to [/opt/homebrew/bin/node index.js]
  Hello production
  ```

  </details>
* <details><summary>`run --quiet`</summary><br>

  Use `--quiet` to suppress all output (except errors). ([log levels](https://docs.npmjs.com/cli/v8/using-npm/logging#setting-log-levels))

  ```sh
  $ echo "HELLO=production" > .env.production
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ dotenvx run -f .env.production --quiet -- node index.js
  Hello production
  ```

  </details>
* <details><summary>`run --log-level`</summary><br>

  Set `--log-level` to whatever you wish. For example, to supress warnings (risky), set log level to `error`:

  ```sh
  $ echo "HELLO=production" > .env.production
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ dotenvx run -f .env.production --log-level=error -- node index.js
  Hello production
  ```

  Available log levels are `error, warn, info, verbose, debug, silly` ([source](https://docs.npmjs.com/cli/v8/using-npm/logging#setting-log-levels))

  </details>
* <details><summary>`run --convention=nextjs`</summary><br>

  Load envs using [Next.js' convention](https://nextjs.org/docs/pages/building-your-application/configuring/environment-variables#environment-variable-load-order). Set `--convention` to `nextjs`:

  ```sh
  $ echo "HELLO=development local" > .env.development.local
  $ echo "HELLO=local" > .env.local
  $ echo "HELLO=development" > .env.development
  $ echo "HELLO=env" > .env
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ dotenvx run --convention=nextjs -- node index.js
  [dotenvx] injecting env (1) from .env.development.local, .env.local, .env.development, .env
  Hello development local
  ```

  (more conventions available upon request)

  </details>
* <details><summary>`get KEY`</summary><br>

  Return a single environment variable's value.

  ```sh
  $ echo "HELLO=World" > .env

  $ dotenvx get HELLO
  World
  ```

  </details>
* <details><summary>`get KEY -f`</summary><br>

  Return a single environment variable's value from a specific `.env` file.

  ```sh
  $ echo "HELLO=World" > .env
  $ echo "HELLO=production" > .env.production

  $ dotenvx get HELLO -f .env.production
  production
  ```

  </details>
* <details><summary>`get KEY --env`</summary><br>

  Return a single environment variable's value from a `--env` string.

  ```sh
  $ dotenvx get HELLO --env HELLO=String -f .env.production
  String
  ```

  </details>

* <details><summary>`get KEY --overload`</summary><br>

  Return a single environment variable's value where each found value is overloaded.

  ```sh
  $ echo "HELLO=World" > .env
  $ echo "HELLO=production" > .env.production

  $ dotenvx get HELLO -f .env.production --env HELLO=String -f .env --overload
  World
  ```

  </details>
* <details><summary>`get KEY --convention=nextjs`</summary><br>

  Return a single environment variable's value using [Next.js' convention](https://nextjs.org/docs/pages/building-your-application/configuring/environment-variables#environment-variable-load-order). Set `--convention` to `nextjs`:

  ```sh
  $ echo "HELLO=development local" > .env.development.local
  $ echo "HELLO=local" > .env.local
  $ echo "HELLO=development" > .env.development
  $ echo "HELLO=env" > .env
  $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

  $ dotenvx get HELLO --convention=nextjs
  development local
  ```

  </details>
* <details><summary>`get` (json)</summary><br>

  Return a json response of all key/value pairs in a `.env` file.

  ```sh
  $ echo "HELLO=World" > .env

  $ dotenvx get
  {"HELLO":"World"}
  ```

  </details>
* <details><summary>`get --all`</summary><br>

  Return preset machine envs as well.

  ```sh
  $ echo "HELLO=World" > .env

  $ dotenvx get --all
  {"PWD":"/some/file/path","USER":"username","LIBRARY_PATH":"/usr/local/lib", ..., "HELLO":"World"}
  ```

  </details>
* <details><summary>`get --all --pretty-print`</summary><br>

  Make the output more readable - pretty print it.

  ```sh
  $ echo "HELLO=World" > .env

  $ dotenvx get --all --pretty-print
  {
    "PWD": "/some/filepath",
    "USER": "username",
    "LIBRARY_PATH": "/usr/local/lib",
    ...,
    "HELLO": "World"
  }
  ```

  </details>
* <details><summary>`set KEY value`</summary><br>

  Set an encrypted key/value (on by default).

  ```sh
  $ touch .env

  $ dotenvx set HELLO World
  set HELLO with encryption (.env)
  ```

  </details>
* <details><summary>`set KEY value -f`</summary><br>

  Set an (encrypted) key/value for another `.env` file.

  ```sh
  $ touch .env.production

  $ dotenvx set HELLO production -f .env.production
  set HELLO with encryption (.env.production)
  ```

  </details>
* <details><summary>`set KEY "value with spaces"`</summary><br>

  Set a value containing spaces.

  ```sh
  $ touch .env.ci

  $ dotenvx set HELLO "my ci" -f .env.ci
  set HELLO with encryption (.env.ci)
  ```

  </details>
* <details><summary>`set KEY -- "- + * ÷"`</summary><br>

  If your value starts with a dash (`-`), then place two dashes instructing the cli that there are no more flag arguments.

  ```sh
  $ touch .env.ci

  $ dotenvx set HELLO -f .env.ci -- "- + * ÷"
  set HELLO with encryption (.env.ci)
  ```

  </details>
* <details><summary>`set KEY value --plain`</summary><br>

  Set a plaintext key/value.

  ```sh
  $ touch .env

  $ dotenvx set HELLO World --plain
  set HELLO (.env)
  ```

  </details>
* <details><summary>`encrypt`</summary><br>

  Encrypt the contents of a `.env` file to an encrypted `.env` file.

  ```sh
  $ echo "HELLO=World" > .env

  $ dotenvx encrypt
  ✔ encrypted (.env)
  ✔ key added to .env.keys (DOTENV_PRIVATE_KEY)
  ℹ add .env.keys to .gitignore: [echo ".env.keys" >> .gitignore]
  ℹ run [DOTENV_PRIVATE_KEY='122...0b8' dotenvx run -- yourcommand] to test decryption locally
  ```

  </details>
* <details><summary>`encrypt -f`</summary><br>

  Encrypt the contents of a specified `.env` file to an encrypted `.env` file.

  ```sh
  $ echo "HELLO=World" > .env
  $ echo "HELLO=Production" > .env.production

  $ dotenvx encrypt -f .env.production
  ✔ encrypted (.env.production)
  ✔ key added to .env.keys (DOTENV_PRIVATE_KEY_PRODUCTION)
  ℹ add .env.keys to .gitignore: [echo ".env.keys" >> .gitignore]
  ℹ run [DOTENV_PRIVATE_KEY_PRODUCTION='bff..bc4' dotenvx run -- yourcommand] to test decryption locally
  ```

  </details>
* <details><summary>`encrypt -k`</summary><br>

  Specify the key(s) to encrypt by passing `--key`.

  ```sh
  $ echo "HELLO=World\nHELLO2=Universe" > .env

  $ dotenvx encrypt -k HELLO2
  ✔ encrypted (.env)
  ```

  </details>
* <details><summary>`encrypt --stdout`</summary><br>

  Encrypt the contents of a `.env` file and send to stdout.

  ```sh
  $ echo "HELLO=World" > .env
  $ dotenvx encrypt --stdout
  #/-------------------[DOTENV_PUBLIC_KEY]--------------------/
  #/            public-key encryption for .env files          /
  #/       [how it works](https://dotenvx.com/encryption)     /
  #/----------------------------------------------------------/
  DOTENV_PUBLIC_KEY="034af93e93708b994c10f236c96ef88e47291066946cce2e8d98c9e02c741ced45"
  # .env
  HELLO="encrypted:BDqDBibm4wsYqMpCjTQ6BsDHmMadg9K3dAt+Z9HPMfLEIRVz50hmLXPXRuDBXaJi/LwWYEVUNiq0HISrslzQPaoyS8Lotg3gFWJTsNCdOWnqpjF2xNUX2RQiP05kAbEXM6MWVjDr"
  ```

  or send to a file:

  ```sh
  $ echo "HELLO=World" > .env
  $ dotenvx encrypt --stdout > somefile.txt
  ```

  </details>
* <details><summary>`decrypt`</summary><br>

  Decrypt the contents of an encrypted `.env` file to an unencrypted `.env` file.

  ```sh
  $ echo "HELLO=World" > .env
  $ dotenvx encrypt
  ✔ encrypted (.env)
  $ dotenvx decrypt
  ✔ decrypted (.env)
  ```

  </details>
* <details><summary>`decrypt -f`</summary><br>

  Decrypt the contents of a specified encrypted `.env` file to an unencrypted `.env` file.

  ```sh
  $ echo "HELLO=World" > .env
  $ echo "HELLO=Production" > .env.production

  $ dotenvx encrypt -f .env.production
  ✔ encrypted (.env.production)
  $ dotenvx decrypt -f .env.production
  ✔ decrypted (.env.production)
  ```

  </details>
* <details><summary>`decrypt --stdout`</summary><br>

  Decrypt the contents of an encrypted `.env` file and send to stdout.

  ```sh
  $ dotenvx decrypt --stdout
  #/-------------------[DOTENV_PUBLIC_KEY]--------------------/
  #/            public-key encryption for .env files          /
  #/       [how it works](https://dotenvx.com/encryption)     /
  #/----------------------------------------------------------/
  DOTENV_PUBLIC_KEY="034af93e93708b994c10f236c96ef88e47291066946cce2e8d98c9e02c741ced45"
  # .env
  HELLO="World"
  ```

  or send to a file:

  ```sh
  $ dotenvx decrypt --stdout > somefile.txt
  ```

  </details>

* <details><summary>`help`</summary><br>

  Output help for `dotenvx`.

  ```sh
  $ dotenvx help
  Usage: @dotenvx/dotenvx [options] [command]

  a better dotenv–from the creator of `dotenv`

  Options:
    -l, --log-level <level>           set log level (default: "info")
    -q, --quiet                       sets log level to error
    -v, --verbose                     sets log level to verbose
    -d, --debug                       sets log level to debug
    -V, --version                     output the version number
    -h, --help                        display help for command

  Commands:
    run [options]                     inject env at runtime [dotenvx run -- yourcommand]
    get [options] [key]               return a single environment variable
    set [options] <KEY> <value>       set a single environment variable
    encrypt [options]                 convert .env file(s) to encrypted .env file(s)
    decrypt [options]                 convert encrypted .env file(s) to plain .env file(s)
    pro                               🏆 pro
    ext [command] [args...]           🔌 extensions
    help [command]                    display help for command
  ```

  You can get more detailed help per command with `dotenvx help COMMAND`.

  ```sh
  $ dotenvx help run
  Usage: @dotenvx/dotenvx run [options]

  inject env at runtime [dotenvx run -- yourcommand]

  Options:
    -e, --env <strings...>            environment variable(s) set as string (example: "HELLO=World") (default: [])
    -f, --env-file <paths...>         path(s) to your env file(s) (default: [])
    -fv, --env-vault-file <paths...>  path(s) to your .env.vault file(s) (default: [])
    -o, --overload                    override existing env variables
    --convention <name>               load a .env convention (available conventions: ['nextjs'])
    -h, --help                        display help for command

  Examples:

    $ dotenvx run -- npm run dev
    $ dotenvx run -- flask --app index run
    $ dotenvx run -- php artisan serve
    $ dotenvx run -- bin/rails s

  Try it:

    $ echo "HELLO=World" > .env
    $ echo "console.log('Hello ' + process.env.HELLO)" > index.js

    $ dotenvx run -- node index.js
    [dotenvx] injecting env (1) from .env
    Hello World
  ```

  </details>
* <details><summary>`--version`</summary><br>

  Check current version of `dotenvx`.

  ```sh
  $ dotenvx --version
  X.X.X
  ```

  </details>

### Extensions 🔌

* <details><summary>`ext ls`</summary><br>

  Print all `.env` files in a tree structure.

  ```sh
  $ touch .env
  $ touch .env.production
  $ mkdir -p apps/backend
  $ touch apps/backend/.env

  $ dotenvx ext ls
  ├─ .env.production
  ├─ .env
  └─ apps
     └─ backend
        └─ .env
  ```

  </details>
* <details><summary>`ext ls directory`</summary><br>

  Print all `.env` files inside a specified path to a directory.

  ```sh
  $ touch .env
  $ touch .env.production
  $ mkdir -p apps/backend
  $ touch apps/backend/.env

  $ dotenvx ext ls apps/backend
  └─ .env
  ```

  </details>
* <details><summary>`ext ls -f`</summary><br>

  Glob `.env` filenames matching a wildcard.

  ```sh
  $ touch .env
  $ touch .env.production
  $ mkdir -p apps/backend
  $ touch apps/backend/.env
  $ touch apps/backend/.env.prod

  $ dotenvx ext ls -f **/.env.prod*
  ├─ .env.production
  └─ apps
     └─ backend
        └─ .env.prod
  ```

  </details>
* <details><summary>`ext genexample`</summary><br>

  In one command, generate a `.env.example` file from your current `.env` file contents.

  ```sh
  $ echo "HELLO=World" > .env

  $ dotenvx ext genexample
  ✔ updated .env.example (1)
  ```

  ```ini
  # .env.example
  HELLO=""
  ```

  </details>
* <details><summary>`ext genexample -f`</summary><br>

  Pass multiple `.env` files to generate your `.env.example` file from the combination of their contents.

  ```sh
  $ echo "HELLO=World" > .env
  $ echo "DB_HOST=example.com" > .env.production

  $ dotenvx ext genexample -f .env -f .env.production
  ✔ updated .env.example (2)
  ```

  ```ini
  # .env.example
  HELLO=""
  DB_HOST=""
  ```

  </details>
* <details><summary>`ext genexample directory`</summary><br>

  Generate a `.env.example` file inside the specified directory. Useful for monorepos.

  ```sh
  $ echo "HELLO=World" > .env
  $ mkdir -p apps/backend
  $ echo "HELLO=Backend" > apps/backend/.env

  $ dotenvx ext genexample apps/backend
  ✔ updated .env.example (1)
  ```

  ```ini
  # apps/backend/.env.example
  HELLO=""
  ```

  </details>
* <details><summary>`ext gitignore`</summary><br>

  Gitignore your `.env` files.

  ```sh
  $ dotenvx ext gitignore
  creating .gitignore
  appending .env* to .gitignore
  done
  ```

  </details>
* <details><summary>`ext precommit`</summary><br>

  Prevent `.env` files from being committed to code.

  ```sh
  $ dotenvx ext precommit
  [dotenvx][precommit] success
  ```

  </details>
* <details><summary>`ext precommit --install`</summary><br>

  Install a shell script to `.git/hooks/pre-commit` to prevent accidentally committing any `.env` files to source control.

  ```sh
  $ dotenvx ext precommit --install
  [dotenvx][precommit] dotenvx precommit installed [.git/hooks/pre-commit]
  ```

  </details>
* <details><summary>`ext prebuild`</summary><br>

  Prevent `.env` files from being built into your docker containers.

  Add it to your `Dockerfile`.

  ```sh
  RUN curl -fsS https://dotenvx.sh | sh

  ...

  RUN dotenvx ext prebuild
  CMD ["dotenvx", "run", "--", "node", "index.js"]
  ```

  </details>
* <details><summary>`ext scan`</summary><br>

  Use [gitleaks](https://gitleaks.io) under the hood to scan for possible secrets in your code.

  ```sh
  $ dotenvx ext scan

      ○
      │╲
      │ ○
      ○ ░
      ░    gitleaks

  100 commits scanned.
  no leaks found
  ```

  </details>

&nbsp;

## Guides

> Go deeper into using `dotenvx` with detailed framework and platform guides.
>

* <a href="https://dotenvx.com/docs/platforms/digital-ocean">Digital Ocean <img src="https://api.iconify.design/devicon/digitalocean.svg" alt="Digital Ocean" width="20" /></a>
* <a href="https://dotenvx.com/docs/platforms/docker">Docker <img src="https://api.iconify.design/skill-icons/docker.svg" alt="Docker" width="20" /></a>
* <a href="https://dotenvx.com/docs/platforms/fly">Fly.io <img src="https://api.iconify.design/logos/fly-icon.svg" alt="Fly.io" width="20" /></a>
* <a href="https://dotenvx.com/docs/cis/github-actions">GitHub Actions <img src="https://api.iconify.design/devicon/github.svg" alt="GitHub" width="20" /></a>
* <a href="https://dotenvx.com/docs/platforms/heroku">Heroku <img src="https://api.iconify.design/skill-icons/heroku.svg" alt="Heroku" width="20" /></a>
* <a href="https://dotenvx.com/docs/platforms/netlify">Netlify <img src="https://api.iconify.design/skill-icons/netlify-light.svg" alt="Netlify" width="20" /></a>
* <a href="https://dotenvx.com/docs/package-managers/npm">NPM <img src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/npm.svg" alt="NPM Logo" width="20" height="20" style="fill:#CB3837;"></a>
* <a href="https://dotenvx.com/docs/monorepos/nx">Nx <img src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/nx.svg" alt="Nx Logo" width="20" height="20" style="fill:#143055;"></a>
* <a href="https://dotenvx.com/docs/platforms/render">Render <img src="https://api.iconify.design/simple-icons/render.svg" alt="Render" width="20" /></a>
* <a href="https://dotenvx.com/docs/platforms/railway">Railway <img src="https://api.iconify.design/simple-icons/railway.svg" alt="Railway" width="20" /></a>
* <a href="https://dotenvx.com/docs/monorepos/turborepo">Turborepo <img src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/turborepo.svg" alt="Turborepo Logo" width="20" height="20" style="fill:#EF4444;"></a>
* <a href="https://dotenvx.com/docs/platforms/vercel">Vercel <img src="https://api.iconify.design/devicon/vercel.svg" alt="Vercel" width="20" /></a>
* [more](https://dotenvx.com/docs/guides)
  * <a href="https://dotenvx.com/docs/guides#node-js">Node.js <img src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/nodejs.svg" alt="Node.js Logo" width="20" height="20" style="fill:#5FA04E;"></a>
  * <a href="https://dotenvx.com/docs/guides#python">Python <img src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/python.svg" alt="Python Logo" width="20" height="20" style="fill:#3776AB;"></a>
  * <a href="https://dotenvx.com/docs/guides#php">PHP <img src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/php.svg" alt="PHP Logo" width="20" height="20" style="fill:#777BB4;"></a>
  * <a href="https://dotenvx.com/docs/guides#ruby">Ruby <img src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/ruby.svg" alt="Ruby Logo" width="20" height="20" style="fill:#CC342D;"></a>
  * <a href="https://dotenvx.com/docs/guides#rust">Rust <img src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/rust.svg" alt="Rust Logo" width="20" height="20" style="fill:#000000;"></a>

&nbsp;

## FAQ

#### Why am I getting the error `node: .env: not found`?

You are using Node 20 or greater and it adds a differing implementation of `--env-file` flag support. Rather than warn on a missing `.env` file (like dotenv has historically done), it raises an error: `node: .env: not found`.

This fix is easy. Replace `--env-file` with `-f`.

```bash
# from this:
./node_modules/.bin/dotenvx run --env-file .env -- yourcommand
# to this:
./node_modules/.bin/dotenvx run -f .env -- yourcommand
```

[more context](https://github.com/dotenvx/dotenvx/issues/131)

#### What happened to the `.env.vault` file?

I've decided we should sunset it as a technological solution to this.

The `.env.vault` file got us far, but it had limitations such as:

* *Pull Requests* - it was difficult to tell which key had been changed
* *Security* - there was no mechanism to give a teammate the ability to encrypt without also giving them the ability to decrypt. Sometimes you just want to let a contractor encrypt a new value, but you don't want them to know the rest of the secrets.
* *Conceptual* - it takes more mental energy to understand the `.env.vault` format. Encrypted values inside a `.env` file is easier to quickly grasp.
* *Combining Multiple Files* - there was simply no mechanism to do this well with the `.env.vault` file format.

That said, the `.env.vault` tooling will still stick around for at least 1 year under `dotenvx vault` parent command. I'm still using it in projects as are many thousands of other people.

#### How do I migrate my `.env.vault` file(s) to encrypted `.env` files?

Run `$ dotenvx vault migrate` and follow the instructions.

&nbsp;

## Contributing

You can fork this repo and create [pull requests](https://github.com/dotenvx/dotenvx/pulls) or if you have questions or feedback:

* [github.com/dotenvx/dotenvx](https://github.com/dotenvx/dotenvx/issues) - bugs and discussions
* [@dotenvx 𝕏](https://x.com/dotenvx) (DMs are open)
