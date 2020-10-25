[![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg)](https://lerna.js.org/)
# Lerna Starter Monorepo
Lerna based monorepo using Git submodules for nested packages.

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

## Using Lerna
This monorepo uses [lerna.js](https://lerna.js.org/) for package management. Lerna enables project-level local package management in a development environmnet.
Make sure that packages refer to the correct local version otherwise lerna will try to fetch the version stored on npmjs.

Run `lerna bootstrap` to bootstrap the packages.

## Repositories
* [example](https:/example.com): Example Package