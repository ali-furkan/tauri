# Changelog

## \[1.0.0-beta-rc.5]

- Improve error logging.
  - [5cc4b11](https://www.github.com/tauri-apps/tauri/commit/5cc4b11f5d00a1e7e580e31785b31c491c06d8d7) feat(cli.rs): add context to errors ([#1674](https://www.github.com/tauri-apps/tauri/pull/1674)) on 2021-05-01
- Adds Webview2 version on `info` command.
  - [2b4e2b7](https://www.github.com/tauri-apps/tauri/commit/2b4e2b7560515b76002d0c724bcca1f470ed106f) feat(cli.rs/info): get webview2 version on windows ([#1669](https://www.github.com/tauri-apps/tauri/pull/1669)) on 2021-05-04
- Adds `--runner [PROGRAM]` argument on the `dev` and `build` command, allowing using the specified program to run and build the application (example program: `cross`).
  - [5c1fe52](https://www.github.com/tauri-apps/tauri/commit/5c1fe52c2bd74e2a8f6c99c2870af967e6309e8d) feat(cli.rs): allow using cross instead of cargo, add target triple arg ([#1664](https://www.github.com/tauri-apps/tauri/pull/1664)) on 2021-04-30
- Adds `--target [TARGET_TRIPLE]` option to the `build` command (example: `--target arm-unknown-linux-gnueabihf`).
  - [5c1fe52](https://www.github.com/tauri-apps/tauri/commit/5c1fe52c2bd74e2a8f6c99c2870af967e6309e8d) feat(cli.rs): allow using cross instead of cargo, add target triple arg ([#1664](https://www.github.com/tauri-apps/tauri/pull/1664)) on 2021-04-30
- Rename `--target` option on the `build` command to `--bundle`.
  - [5c1fe52](https://www.github.com/tauri-apps/tauri/commit/5c1fe52c2bd74e2a8f6c99c2870af967e6309e8d) feat(cli.rs): allow using cross instead of cargo, add target triple arg ([#1664](https://www.github.com/tauri-apps/tauri/pull/1664)) on 2021-04-30
- Properly kill `beforeDevCommand` process.
  - [ac2cbcb](https://www.github.com/tauri-apps/tauri/commit/ac2cbcb131819e01074e1ed8fb6808260c56a027) fix(cli.rs): `before dev` process kill, closes [#1626](https://www.github.com/tauri-apps/tauri/pull/1626) ([#1700](https://www.github.com/tauri-apps/tauri/pull/1700)) on 2021-05-04
- Adds support to `tauri` dependency as string and table on `Cargo.toml`.
  - [df8bdcf](https://www.github.com/tauri-apps/tauri/commit/df8bdcf0631fd4e1e7035eb20a954574da96de66) feat(cli.rs): add support to string and table dependency, closes [#1653](https://www.github.com/tauri-apps/tauri/pull/1653) ([#1654](https://www.github.com/tauri-apps/tauri/pull/1654)) on 2021-04-29
- Show `framework` and `bundler` on the `info` command by reading the `package.json` file and matching known dependencies.
  - [152c755](https://www.github.com/tauri-apps/tauri/commit/152c755c4787b323ca3469c45934cc1e4d368cfa) feat(cli.rs): `framework` and `bundler` on info cmd, closes [#1681](https://www.github.com/tauri-apps/tauri/pull/1681) ([#1682](https://www.github.com/tauri-apps/tauri/pull/1682)) on 2021-05-02

## \[1.0.0-beta-rc.4]

- Fixes the Message `command` name value on plugin invoke handler.
  - Bumped due to a bump in tauri.
  - [422dd5e](https://www.github.com/tauri-apps/tauri/commit/422dd5e2a0a03bb1556915c78f110bfab092c874) fix(core): command name on plugin invoke handler ([#1577](https://www.github.com/tauri-apps/tauri/pull/1577)) on 2021-04-21
  - [f575aaa](https://www.github.com/tauri-apps/tauri/commit/f575aaad71f23d44b2f89cf9ee5d84817dc3bb7a) fix: change files not referencing core packages ([#1619](https://www.github.com/tauri-apps/tauri/pull/1619)) on 2021-04-25
- The package info APIs now checks the `package` object on `tauri.conf.json`.
  - Bumped due to a bump in tauri.
  - [8fd1baf](https://www.github.com/tauri-apps/tauri/commit/8fd1baf69b14bb81d7be9d31605ed7f02058b392) fix(core): pull package info from tauri.conf.json if set ([#1581](https://www.github.com/tauri-apps/tauri/pull/1581)) on 2021-04-22
  - [f575aaa](https://www.github.com/tauri-apps/tauri/commit/f575aaad71f23d44b2f89cf9ee5d84817dc3bb7a) fix: change files not referencing core packages ([#1619](https://www.github.com/tauri-apps/tauri/pull/1619)) on 2021-04-25

## \[1.0.0-beta-rc.3]

- Check if distDir assets are built after running `beforeDevCommand`.
  - [a670d3a](https://www.github.com/tauri-apps/tauri/commit/a670d3a457bc0c0135b879c746d26a5f121c87a7) fix(cli.rs): check if distDir exists after running `beforeDevCommand` ([#1586](https://www.github.com/tauri-apps/tauri/pull/1586)) on 2021-04-22
- Fixes `tauri info` display version for the `@tauri-apps/api` package.
  - [0012782](https://www.github.com/tauri-apps/tauri/commit/0012782e43bd4e7e49528853c226b8e0e24b8794) fix(cli.rs): `info` command `npm_package_version` parsing `beta-rc` ([#1587](https://www.github.com/tauri-apps/tauri/pull/1587)) on 2021-04-22
- Fixes crash on usage of modifier keys on Windows when running `tauri init`.
  - [d623d95](https://www.github.com/tauri-apps/tauri/commit/d623d95fcb67736bc0862866b347c7102cde66aa) fix(cli.rs): inliner dialoguer & console until they publish, fixes [#1492](https://www.github.com/tauri-apps/tauri/pull/1492) ([#1610](https://www.github.com/tauri-apps/tauri/pull/1610)) on 2021-04-25
- Enable `tauri` `updater` feature when `tauri.conf.json > tauri > updater > active` is set to `true`.
  - [9490b25](https://www.github.com/tauri-apps/tauri/commit/9490b257d2564840eb0c9167340bf444bca84699) fix(cli.rs): enable the `updater` feature on cli ([#1597](https://www.github.com/tauri-apps/tauri/pull/1597)) on 2021-04-23

## \[1.0.0-beta-rc.2]

- Add missing camelcase rename for config
  - [bdf7072](https://www.github.com/tauri-apps/tauri/commit/bdf707285e3d307ab083009c274ccb56d5053ff2) fix(cli.rs/info): add missing camelCase rename ([#1505](https://www.github.com/tauri-apps/tauri/pull/1505)) on 2021-04-14
- Fix `tauri info`
- Properly detect `yarn` and `npm` versions on windows.
- Fix a panic caused by a wrong field name in `metadata.json`
- [71666e9](https://www.github.com/tauri-apps/tauri/commit/71666e9f9cfb5499a727b3f95182e89073f67d7b) fix(cli.rs): fix panic & use `cmd` to run `yarn`&`npm` on windows ([#1511](https://www.github.com/tauri-apps/tauri/pull/1511)) on 2021-04-17
- Sync `metadata.json` via script to update version reference to cli.js, tauri (core) and tauri-build.
  - [1f64927](https://www.github.com/tauri-apps/tauri/commit/1f64927362ef20761d7cd3591281519eb292aa33) chore: sync cli.rs metadata.json file versions ([#1534](https://www.github.com/tauri-apps/tauri/pull/1534)) on 2021-04-19

## \[1.0.0-beta-rc.1]

- Missing the `files` property in the package.json which mean that the `dist` directory was not published and used.
  - Bumped due to a bump in api.
  - [b2569a7](https://www.github.com/tauri-apps/tauri/commit/b2569a729a3caa88bdba62abc31f0665e1323aaa) fix(js-api): dist ([#1498](https://www.github.com/tauri-apps/tauri/pull/1498)) on 2021-04-15

## \[1.0.0-beta-rc.0]

- You can now run `cargo tauri build -t none` to speed up the build if you don't need executables.
  - [4d507f9](https://www.github.com/tauri-apps/tauri/commit/4d507f9adfb26819f9d6406b191fdaa6188145f4) feat(cli/core): add support for building without targets ([#1203](https://www.github.com/tauri-apps/tauri/pull/1203)) on 2021-02-10
  - [aea6145](https://www.github.com/tauri-apps/tauri/commit/aea614587bddab930d552512b54e18624fbf573e) refactor(repo): add /tooling folder ([#1457](https://www.github.com/tauri-apps/tauri/pull/1457)) on 2021-04-12
- The `dev` and `build` pipeline is now written in Rust.
  - [3e8abe3](https://www.github.com/tauri-apps/tauri/commit/3e8abe376407bb0ca8893602590ed9edf7aa71a1) feat(cli) rewrite the core CLI in Rust ([#851](https://www.github.com/tauri-apps/tauri/pull/851)) on 2021-01-30
  - [aea6145](https://www.github.com/tauri-apps/tauri/commit/aea614587bddab930d552512b54e18624fbf573e) refactor(repo): add /tooling folder ([#1457](https://www.github.com/tauri-apps/tauri/pull/1457)) on 2021-04-12
- Run `beforeDevCommand` and `beforeBuildCommand` in a shell.
  - [32eb0d5](https://www.github.com/tauri-apps/tauri/commit/32eb0d562b135d8df19c78ff22aa53c73f459c76) feat(cli): run beforeDev and beforeBuild in a shell, closes [#1295](https://www.github.com/tauri-apps/tauri/pull/1295) ([#1399](https://www.github.com/tauri-apps/tauri/pull/1399)) on 2021-03-28
  - [aea6145](https://www.github.com/tauri-apps/tauri/commit/aea614587bddab930d552512b54e18624fbf573e) refactor(repo): add /tooling folder ([#1457](https://www.github.com/tauri-apps/tauri/pull/1457)) on 2021-04-12
- Fixes `<a target="_blank">` polyfill.
  - [4ee044a](https://www.github.com/tauri-apps/tauri/commit/4ee044a3e662a0ac2be98f7e1286088d721c3307) fix(cli): use correct arg in `_blanks` links polyfill ([#1362](https://www.github.com/tauri-apps/tauri/pull/1362)) on 2021-03-17
  - [aea6145](https://www.github.com/tauri-apps/tauri/commit/aea614587bddab930d552512b54e18624fbf573e) refactor(repo): add /tooling folder ([#1457](https://www.github.com/tauri-apps/tauri/pull/1457)) on 2021-04-12
- Update all code files to have our license header.
  - [bf82136](https://www.github.com/tauri-apps/tauri/commit/bf8213646689175f8a158b956911f3a43e360690) feat(license): SPDX Headers ([#1449](https://www.github.com/tauri-apps/tauri/pull/1449)) on 2021-04-11
  - [a6def70](https://www.github.com/tauri-apps/tauri/commit/a6def7066eec19c889b0f14cc1e475bf209a332e) Refactor(tauri): move tauri-api and tauri-updater to tauri ([#1455](https://www.github.com/tauri-apps/tauri/pull/1455)) on 2021-04-11
  - [aea6145](https://www.github.com/tauri-apps/tauri/commit/aea614587bddab930d552512b54e18624fbf573e) refactor(repo): add /tooling folder ([#1457](https://www.github.com/tauri-apps/tauri/pull/1457)) on 2021-04-12
- Adds `productName` and `version` configs on `tauri.conf.json > package`.
  - [5b3d9b2](https://www.github.com/tauri-apps/tauri/commit/5b3d9b2c07da766f81981ba7c4961cd354d51340) feat(config): allow setting product name and version on tauri.conf.json ([#1358](https://www.github.com/tauri-apps/tauri/pull/1358)) on 2021-03-22
  - [aea6145](https://www.github.com/tauri-apps/tauri/commit/aea614587bddab930d552512b54e18624fbf573e) refactor(repo): add /tooling folder ([#1457](https://www.github.com/tauri-apps/tauri/pull/1457)) on 2021-04-12
- The `info` command was rewritten in Rust.
  - [c3e06ee](https://www.github.com/tauri-apps/tauri/commit/c3e06ee9e88b3631da6eeb17d61ddd41cd5c6fe9) refactor(cli): rewrite info in Rust ([#1389](https://www.github.com/tauri-apps/tauri/pull/1389)) on 2021-03-25
  - [aea6145](https://www.github.com/tauri-apps/tauri/commit/aea614587bddab930d552512b54e18624fbf573e) refactor(repo): add /tooling folder ([#1457](https://www.github.com/tauri-apps/tauri/pull/1457)) on 2021-04-12
- The `init` command was rewritten in Rust.
  - [f72b93b](https://www.github.com/tauri-apps/tauri/commit/f72b93b676ba8c48fd9273c187de3dbbc410fa0f) refactor(cli): rewrite init command in Rust ([#1382](https://www.github.com/tauri-apps/tauri/pull/1382)) on 2021-03-24
  - [aea6145](https://www.github.com/tauri-apps/tauri/commit/aea614587bddab930d552512b54e18624fbf573e) refactor(repo): add /tooling folder ([#1457](https://www.github.com/tauri-apps/tauri/pull/1457)) on 2021-04-12
- All the arguments passed after `tauri dev --` are now propagated to the binary.
  - [4e9d31c](https://www.github.com/tauri-apps/tauri/commit/4e9d31c70ba13f1cabe830c6519a1b5f4789fd7b) feat(cli): propagate args passed after `dev --`, closes [#1406](https://www.github.com/tauri-apps/tauri/pull/1406) ([#1407](https://www.github.com/tauri-apps/tauri/pull/1407)) on 2021-03-30
  - [aea6145](https://www.github.com/tauri-apps/tauri/commit/aea614587bddab930d552512b54e18624fbf573e) refactor(repo): add /tooling folder ([#1457](https://www.github.com/tauri-apps/tauri/pull/1457)) on 2021-04-12
- Alpha version of tauri-updater. Please refer to the `README` for more details.
  - [6d70c8e](https://www.github.com/tauri-apps/tauri/commit/6d70c8e1e256fe839c4a947375bb529d7b4f7301) feat(updater): Alpha version ([#643](https://www.github.com/tauri-apps/tauri/pull/643)) on 2021-04-05
  - [a6def70](https://www.github.com/tauri-apps/tauri/commit/a6def7066eec19c889b0f14cc1e475bf209a332e) Refactor(tauri): move tauri-api and tauri-updater to tauri ([#1455](https://www.github.com/tauri-apps/tauri/pull/1455)) on 2021-04-11
  - [aea6145](https://www.github.com/tauri-apps/tauri/commit/aea614587bddab930d552512b54e18624fbf573e) refactor(repo): add /tooling folder ([#1457](https://www.github.com/tauri-apps/tauri/pull/1457)) on 2021-04-12
