---
category: getting-started
slug: /getting-started/install
title: Installation
description: Yarn's in-depth installation guide.
sidebar_position: 2
---

:::tip
The preferred way to manage Yarn is by-project and through [Corepack](https://nodejs.org/dist/latest/docs/api/corepack.html), a tool shipped by default with Node.js. Modern releases of Yarn aren't meant to be installed globally, or from npm.
:::

1. Start by enabling Corepack, if it isn't already:

<CommandLineHighlight type={`code`} lines={[{type: `command`, command: {name: `corepack`, path: [`enable`], argv: [`enable`]}, split: false, tooltip: null, tokens: [{type: `path`, segmentIndex: 0, text: `enable`}]}]}/>

2. Then initialize a new project:

```
yarn init -2
```

## Updating Yarn

Any time you'll want to update Yarn to the latest version, just run:

```
yarn set version stable
yarn install
```

Yarn will then configure your project to use the most recent stable binary.

:::tip
Yarn also frequently ships Release Candidate builds. Use `yarn set version canary` should you need a feature not released on the stable channel yet. Those builds are very stable, the only difference with the regular channel being a more staggered migration between major as we implement new breaking changes.
:::

## Installing the latest build fresh from master

You may want to test a version of Yarn so recent it hasn't been released in a Release Candidate yet, or even not merged. The following command will clone, build, and install Yarn in your project, straight from our repository:

```
yarn set version from sources
```

It accepts a `--branch` flag which you can use to test specific PRs:

```
yarn set version from sources --branch 1211
```

:::caution
Unlike the stable and canary channels, the `yarn set version from sources` command can't leverage Corepack and will need to store the Yarn binary inside the `.yarn/releases` folder and reference it from your project's `.yarnrc.yml` file.
:::
