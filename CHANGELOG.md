# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

<!-- markdownlint-disable MD024 -->

## [6.0.1] (2019-08-20)

### Fixed

- allow options to come after commands, especially `nvh lsr --all`

## [6.0.0] (2019-08-16)

### Added

- version specified using release stream codenames, like `argon` ([#423])
- version specified using nightly et al ([#376])
- `n exec` for running arbitrary command with node and npm in `PATH` ([#185])
- `n run` with legacy aliases of `as` and `use`
- `n lsr` for listing matching remote versions, limited to 20 by default ([#383])
- `n doctor` for displaying diagnostic information
- `n install` for people used to other products with this command ([#524])
- `--insecure` to disable curl/wget certificate checks
- added npm version to installed message ([#210] [#484] [#574])
  
### Changed

- **Breaking** wget now checks certificates (secure by default, same as curl setup). (#475 #509)
- failure messages go to stderr instead of stdout
- prefixed `N_NODE_MIRROR` to eventually replace `NODE_MIRROR`
- **Breaking** `n ls` now lists local download versions (rather than remote versions)
- lookup available versions using `index.tab` rather than screen-scraping (#560)

### Fixed

- download errors display informative message, instead of just `Invalid version` ([#482] [#492] et al)
- improve reliability of downloads from custom node mirrors, including removing broken `is_oss_ok` ([#560])
- restrict downloads to versions with architecture available ([#463])

### Removed

- **Breaking** support for `PROJECT_NAME` and `PROJECT_URL` for custom downloads ([#342])

## [5.0.2] (2019-08-02)

### Added

- instructions to bottom of menu version selection

## [5.0.1] (2019-07-20)

### Changed

- removed reference to prerelease version of v5.0.0 from README

## [5.0.0] (2019-07-20)

### Added

- log message after install from cache (previously silent)
- extra logging after install if the active and installed node locations are different
- support for [NO_COLOR](http://no-color.org) and [CLICOLOR=0](https://bixense.com/clicolors)
- suppress progress and colour if not interactive tty
- define `N_USE_XZ` to download `.xz` compressed archives instead of `.gz` archives
  
### Changed

- reinstalling active node version always does reinstall (previously silently did nothing)
- log message for installing using menu now same format as `npm install` message
- updates to GitHub templates and guidelines for contributing et al

## [4.1.0] (2019-05-10)

### Added

- 'n uninstall` to remove node and npm
- describe `NODE_MIRROR` in `README`

### Removed

- `PROJECT_NAME` and `PROJECT_URL` from `README`. First step to deprecating `n project`. Open an issue if you still need this!

## [4.0.0] (2019-05-05)

Only minor functional changes, but technically could break scripts relying on specific behaviour.

### Fixed

- remove trailing space from `bin` output [#456]

### Added

- development tests [#545]

### Changed

- internal: improve shell script based on ShellCheck suggestions, quoting variables use etc [#187] [#465]
- put single quote marks around parameters to clarify error messages [#485]
- update terminology to be more careful with current/latest [#522]

## [3.0.2] (2019-04-07)

### Added

- instructions to avoid need for `sudo` when installing to `/usr/local`  [#416] [#562]

### Fixed

- permission denied errors when running read-only commands without sudo [#416]

## [3.0.1] (2019-04-05)

### Added

- install instruction using Homebrew (macOS) [#534]
- Table of Contents to README [#466]

### Fixed

- lts lookup on node mirrors which don't purge old versions (e.g. taobao) [#512]
- hide cursor while selecting version from menu [#528]

### Removed

- gitter badge from README, as gitter chatroom inactive
- inactive Core Team from README
- instructions for scripted install of npm from README, which should no longer be needed and not working on Mac [#536]

## [3.0.0] (2019-03-29)

### Added

- detect arm64 architecture [#448][] [#521][]

### Changed

- allow `n rm` of active version of node [#541][] [#169][] [#327][] [#441][]
- show more version examples in README, including partial version number [#548][]
- updated description of interactive version selection [#518][]
- make (old) stable an alias for lts [#467][] [#335][]
- replace use of `which` with more standard `command -v` [#532][]

### Fixed

- error messages when selecting from version menu if active node version not listed [#541][] [#292][] [#367][] [#391][] [#400][]
- removed inappropriate `shift` from prune function [#531][] [#529][]

### Removed

- Remove old io project support [#516][] [#331][]

<!-- reference links for issues and pull requests -->

[#169]: https://github.com/tj/n/issues/169
[#185]: https://github.com/tj/n/issues/185
[#187]: https://github.com/tj/n/issues/187
[#210]: https://github.com/tj/n/issues/210
[#292]: https://github.com/tj/n/issues/292
[#327]: https://github.com/tj/n/issues/327
[#331]: https://github.com/tj/n/issues/331
[#335]: https://github.com/tj/n/issues/335
[#342]: https://github.com/tj/n/issues/342
[#367]: https://github.com/tj/n/issues/367
[#376]: https://github.com/tj/n/issues/376
[#383]: https://github.com/tj/n/issues/383
[#391]: https://github.com/tj/n/issues/391
[#400]: https://github.com/tj/n/issues/400
[#416]: https://github.com/tj/n/issues/416
[#423]: https://github.com/tj/n/issues/423
[#441]: https://github.com/tj/n/issues/441
[#448]: https://github.com/tj/n/issues/448
[#456]: https://github.com/tj/n/issues/456
[#463]: https://github.com/tj/n/issues/463
[#465]: https://github.com/tj/n/issues/465
[#466]: https://github.com/tj/n/issues/466
[#467]: https://github.com/tj/n/issues/467
[#482]: https://github.com/tj/n/issues/482
[#484]: https://github.com/tj/n/issues/484
[#485]: https://github.com/tj/n/issues/485
[#492]: https://github.com/tj/n/issues/492
[#512]: https://github.com/tj/n/issues/512
[#516]: https://github.com/tj/n/issues/516
[#518]: https://github.com/tj/n/issues/518
[#521]: https://github.com/tj/n/issues/521
[#522]: https://github.com/tj/n/issues/522
[#524]: https://github.com/tj/n/issues/524
[#528]: https://github.com/tj/n/issues/528
[#529]: https://github.com/tj/n/issues/529
[#531]: https://github.com/tj/n/issues/531
[#532]: https://github.com/tj/n/issues/532
[#534]: https://github.com/tj/n/issues/534
[#536]: https://github.com/tj/n/issues/536
[#541]: https://github.com/tj/n/issues/541
[#545]: https://github.com/tj/n/issues/545
[#548]: https://github.com/tj/n/issues/548
[#560]: https://github.com/tj/n/issues/560
[#562]: https://github.com/tj/n/issues/562
[#574]: https://github.com/tj/n/issues/574

<!-- reference links for releases -->

[Unreleased]: https://github.com/tj/n/compare/master...develop
[6.0.1]: https://github.com/tj/n/compare/v6.0.0...v6.0.1
[6.0.0]: https://github.com/tj/n/compare/v5.0.2...v6.0.0
[5.0.2]: https://github.com/tj/n/compare/v5.0.1...v5.0.2
[5.0.1]: https://github.com/tj/n/compare/v5.0.0...v5.0.1
[5.0.0]: https://github.com/tj/n/compare/v4.1.0...v5.0.0
[4.1.0]: https://github.com/tj/n/compare/v4.0.0...v4.1.0
[4.0.0]: https://github.com/tj/n/compare/v3.0.2...v4.0.0
[3.0.2]: https://github.com/tj/n/compare/v3.0.1...v3.0.2
[3.0.1]: https://github.com/tj/n/compare/v3.0.0...v3.0.1
[3.0.0]: https://github.com/tj/n/compare/v2.1.12...v3.0.0
