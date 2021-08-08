[![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg)](https://lerna.js.org/)
# Lerna Starter Monorepo
Opinionated Lerna based monorepo using Git submodules for nested packages.

## Using pnpm
We use [pnpm](https://pnpm.io/) as a symlynk based drop-in replacement package manager for NPM. PNPM will help you save significant storage space by avoiding instaling duplicate copies of your dependencies. 
Install pnpm
```
npm i -g pnpm
```
Now whenever you want to install your dependencies
```
pnpm i
```

## Using Lerna

This monorepo uses [lerna.js](https://lerna.js.org/) for package management. Lerna enables project-level local package management in a development environmnet.
Make sure that packages refer to the correct local version otherwise lerna will try to fetch the version stored on npmjs.
Install your dependencies
```
lerna bootstrap
```
Lerna will link your packages and download the required dependencies.
### A note on package hoisting
By default this Lerna setup uses hoisting, which refers to storing shared depedencies at the root `node_modules` folder of the project as opposed to having copies (symlinks when using pnpm) in each package. This is a design decision to as fix to an [issue](https://github.com/pnpm/pnpm/issues/2743) when multiple packages install React as a dependency.

See [hoist.md](https://github.com/lerna/lerna/blob/main/doc/hoist.md) for more info.

## Using Git Submodules
This monorepos relies on git submodules to reference nested packages.
This accomodates boths use cases of developing within the workspace or only within a single nested repo when working on a specific component. 
See [Git-Tools-Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules) on using git submodules.

When pulling the workspace repo with submodules for the first time, you will need to initialize the submodules.
```
git submodule init
```

To add a submodule.
```
git submodule add https://github.com/leovigna/example
```