# fullstack-cra-monorepo-boilerplate

This boilerplate contains

- [`create-react-app`](https://github.com/facebook/create-react-app) template React project with the following extensions.
  - [`react-app-rewired`](https://github.com/timarney/react-app-rewired)
  - [`customize-cra`](https://github.com/arackaf/customize-cra)
  - [`babel-plugin-root-import`](https://github.com/entwicklerstube/babel-plugin-root-import)
- [`express-generator`](https://github.com/expressjs/generator) generated Express template with Pug viewer and [`nodemon`](https://github.com/remy/nodemon).

This project uses `Yarn v2 workspaces`, so no more symbolic links - which means **`workspaces` can now be hosted on Docker**. All the modules & lock files will be installed & cached into the project root. See [Yarn v2 documentation](https://yarnpkg.com/features/pnp) for details.

Frontend & backend are separate workspaces with their own `package.json`, located in `/packages/`. This project when locally run will concurrently start the `client` (frontend) and `server` (backend) workspaces. However, each one will be mounted as their own services in Docker.

The method to mount the project to Docker is based on [this project](https://github.com/huy-nguyen/yarn-v2-workspace-docker-vs-code). Please read Huy Nguyen's [article](https://www.huy.dev/yarn-v2-workspace-docker-vs-code-2020-03-23/) for the explanation.

## Table of Contents

- [Installation](`#installation)
- [Usage](#usage)
- [Support](#support)
- [Contributing](#contributing)

## Installation

**Make sure you have [Yarn](https://github.com/yarnpkg/yarn) installed.**

1. Clone this project

```
git clone https://github.com/harryprabowo/fullstack-cra-boilerplate
```

2. Open a terminal at project root and install dependencies.  
   Please note that `docker-compose build` **will fail** if this is not done in advance.

```
yarn
```

3. Clone `ENV.SAMPLE` and rename to `.env`.

## Usage

Start the project.

```
yarn start
```

`yarn start` is configured with [`concurrently`](https://github.com/kimmobrunfeldt/concurrently) to run `client` and `server` workspaces concurrently.

You can also run each workspaces independently.

```
yarn workspace <workspace-name> start`
```

To use with Docker, first build the container.

```
docker-compose build
```

and finally

```
docker-compose up
```

## Support

Please [open an issue](https://github.com/harryprabowo/fullstack-cra-boilerplate/issues/new) for support.

## Contributing

Please contribute using [Github Flow](https://guides.github.com/introduction/flow/). Create a branch, add commits, and [open a pull request](https://github.com/harryprabowo/fullstack-cra-boilerplate/compare/).
