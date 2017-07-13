# `drupal-spike`
> :microscope: Automate Drupal testing, coverage, Git commit message validation, CHANGELOG generation, semantic version updates, and source code inspection with CLI tools for continuous integration.

[![Build Status](https://travis-ci.org/gregswindle/drupal-spike.svg)](https://travis-ci.org/gregswindle/drupal-spike)

## 1. Table of contents
<!-- TOC depthFrom:2 depthTo:3 withLinks:1 updateOnSave:1 orderedList:0 -->

- [1. Table of contents](#1-table-of-contents)
- [2. Installation](#2-installation)
- [3. Features](#3-features)
	- [3.1. Semantic version and CHANGELOG automation](#31-semantic-version-and-changelog-automation)
	- [3.2. Coding standards](#32-coding-standards)
	- [3.3. Unit test with either `PHPUnit` or `phpspec`](#33-unit-test-with-either-phpunit-or-phpspec)
	- [3.4. E2E test with Behat (functional and integration)](#34-e2e-test-with-behat-functional-and-integration)
	- [3.5. Drush command-line shell](#35-drush-command-line-shell)
- [4. Contributing](#4-contributing)
- [5. References](#5-references)
- [6. License](#6-license)

<!-- /TOC -->

## 2. Installation
> #### :warning: Prerequisite software
>
> You need [Drush][drush-url], [Node.js with `npm`][nodejs-url] (or [Yarn][yarnpkg-url]), and [Composer][composer-url] installed, first.

Open a Terminal (or shell) and `cd` to your Drupal site's root directory and run

```sh

$ composer install

```

This executes custom [Composer scripts][composer-scripts-url] that install PHP and Node.js packages that automate:

* Semantic versioning and CHANGELOG generation
* Drupal coding standards compliance
* Unit test execution and code coverage reports

> #### :construction: [`geerlingguy/drupal-vm`][drupal-vm-url] for Apipee Developer Portal development
>
> We're exploring [`Drupal VM`][drupal-vm-url] as an alternative to installing resources on a workstation's host OS. Please see the [`Drupal VM docs`][drupa-vm-docs-url] if you're interested in spiking this alternative.

## 3. Features

### 3.1. Semantic version and CHANGELOG automation

`drupal-spike` includes

* **[`commitplease`][commitplease-url]**, a [`conventional commit message`][conventional-commit-url] validation pre-commit hook
* **[`standard-version`][standard-version-url]** to automate CHANGELOG generation and [semantic version][semver-url] updates.

### 3.2. Coding standards

`drupal-spike` lints (or "sniffs") PHP for code that doesn't smell like `Drupal` or `DrupalPractice` standards with [PHP_CodeSniffer][php-codesniffer-url].

### 3.3. Unit test with either `PHPUnit` or `phpspec`

Use either

* Either [`PHPUnit`][phpunit-url] with its built-in [code coverage analysis][phpunit-code-coverage-url],
* [`phpspec`][phpspec-url] with [`phpspec-code-coverage`][phpspec-code-coverage-url], or
* Both.

As long as your unit testing framework of choice produces clover.xml and [`lcov`][lcov-url] code coverage reports, you're "covered" (so to speak :mask:).


#### 3.3.1. :newspaper: Drupal 7 unit testing with coverage requires either `PHPUnit` or `phpspec`

Drupal 7 ships with the SimpleTest module, but [`SimpleTest`][simpletest-drupal-url] isn't a true unit testing framework. According to the (official) Drupal.org site's article [Testing with SimpleTest][testing-simpletest],

> :speech_balloon: Drupal testing focuses on functional testing rather than unit testing. Functional tests check the interface as a whole rather than individual functions or finite pieces of code. This approach is more effective for the way Drupal is written.
>
> Testing with SimpleTest. (2016, September 21). Retrieved July 12, 2017, from https://www.drupal.org/docs/7/creating-custom-modules/testing-with-simpletest

To add insult to injury:

> 💬  While doing functional tests, Drupal's simpletest module creates separate environment and database tables for each test and doesn't use the existing site configuration. In addition to being slow, this approach requires that before each functional test, you configure the site in code to replicate the existing site that is in production. This is nuts!!!!
>
> Red Crackle. (n.d.). Retrieved July 12, 2017, from http://redcrackle.com/blog/drupal-testing-methodologies-are-broken-heres-why

#### 3.3.2. Test framework matrix

| Framework  | Test Scope | Supports coverage? |
|:-----------|:-----------|:------------------:|
| Behat      | Functional | No                 |
| phpspec    | Unit       | Yes                |
| PHPUnit    | Unit       | Yes                |
| SimpleTest | Functional | No                 |


### 3.4. E2E test with Behat (functional and integration)

For functional and integration tests, `drupal-spike` uses [Behat][behat-url], a Behavior-Driven Development (BDD) framework for writing tests.


### 3.5. Drush command-line shell
> #### :slot_machine: This step is OPTIONAL.

[Install Drush 7 and 8 Side-by-Side and Automatically Switch Versions Based on Each Project](https://github.com/leanphp/behat-code-coverage#Configuration https://modulesunraveled.com/blog/install-drush-7-and-8-and-automatically-switch-versions-based-project).


## 4. Contributing
:family: We warmly welcome contributors. Check out the guidelines for [Contributing to `drupal-spike`][contributing-url] and our [Contributor Covenant Code of Conduct][code-of-conduct-url].

Contributions are stories with a beginning, a middle, and an end, all told through issues and pull requests.
 * [Peruse open issues][issues-url] or
 * [Open a new pull request (PR)][pr-url]

## 5. References

 * [Installing Coder Sniffer](https://www.drupal.org/node/1419988)
 * [Code Sniffer Command Line Usage](https://www.drupal.org/node/1587138)

## 6. License

[Apache-2.0][license-url] :copyright: [Greg Swindle][author-info].



[author-info]: https://github.com/gregswindle
[behat-code-coverage-url]: https://github.com/leanphp/behat-code-coverage
[behat-url]: https://github.com/Behat/Behat
[behat-url]: https://github.com/Behat/Behat
[codacy-image]: https://api.codacy.com/project/badge/Grade/b03a8de3c56d485f86a14102fce6dd10
[codacy-url]: https://www.codacy.com/app/greg_7/drupal-spike?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=gregswindle/drupal-spike&amp;utm_campaign=Badge_Grade
[code-of-conduct-url]: ./.github/CODE_OF_CONDUCT.md
[commitizen-add-commit-image]: ./.assets/img/commitizen-add-commit.png
[commitizen-url]: https://github.com/commitizen/cz-cli
[commitplease-url]: https://www.npmjs.com/package/commitplease
[composer-scripts-url]: https://getcomposer.org/doc/articles/scripts.md
[composer-url]: https://getcomposer.org
[contributing-url]: ./.github/CONTRIBUTING.md
[conventional-commit-url]: https://conventionalcommits.org/
[coveralls-image]: https://coveralls.io/repos/gregswindle/drupal-spike/badge.svg
[coveralls-url]: https://coveralls.io/r/gregswindle/drupal-spike
[daviddm-image]: https://david-dm.org/gregswindle/drupal-spike.svg?theme=shields.io
[daviddm-url]: https://david-dm.org/gregswindle/drupal-spike
[drupa-vm-docs-url]: http://docs.drupalvm.com/en/latest/
[drupal-vm-url]: https://github.com/geerlingguy/drupal-vm
[drush-url]: https://github.com/drush-ops/drush
[git-commit-guidelines-url]: https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#commit
[git-feat-branch-url]: https://www.atlassian.com/git/tutorials/comparing-workflows#feature-branch-workflow
[gitflow-url]: https://www.atlassian.com/git/tutorials/comparing-workflows#gitflow-workflow
[greenkeeper-image]: https://badges.greenkeeper.io/gregswindle/drupal-spike.svg
[greenkeeper-url]: https://greenkeeper.io/
[issues-url]: https://github.com/gregswindle/drupal-spike/issues
[lcov-url]: https://github.com/linux-test-project/lcov
[lcov-url]: https://github.com/linux-test-project/lcov
[license-image]: https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=flat-square
[license-url]: ./LICENSE
[license-url]: LICENSE
[nodejs-url]: https://nodejs.org/
[npm-image]: https://badge.fury.io/js/drupal-spike.svg
[npm-url]: https://npmjs.org/package/drupal-spike
[nsp-image]: https://nodesecurity.io/orgs/gregswindle/projects/d0b019ea-5391-4b3c-ba8c-464a24bf8a8c/badge
[nsp-url]: https://nodesecurity.io/orgs/gregswindle/projects/d0b019ea-5391-4b3c-ba8c-464a24bf8a8c
[php-codesniffer-url]: https://github.com/squizlabs/PHP_CodeSniffer
[phpcov-url]: https://github.com/sebastianbergmann/phpcov
[phpcov-url]: https://github.com/sebastianbergmann/phpcov
[phpspec-code-coverage-url]: https://github.com/leanphp/phpspec-code-coverage
[phpspec-url]: http://www.phpspec.net/en/stable/
[phpspec-url]: http://www.phpspec.net/en/stable/
[phpunit-code-coverage-url]: https://phpunit.de/manual/current/en/code-coverage-analysis.html
[phpunit-url]: https://phpunit.de/
[phpunit-url]: https://phpunit.de/
[pr-url]: https://github.com/gregswindle/drupal-spike/pulls
[readme-image]: http://readme-score-api.herokuapp.com/score.svg?url=https%3A%2F%2Fgithub.com%2Fgregswindle%2Fdrupal-spike
[readme-url]: http://clayallsopp.github.io/readme-score?url=https%3A%2F%2Fgithub.com%2Fgregswindle%2Fdrupal-spike
[semantic-release-url]: https://github.com/semantic-release/semantic-release
[semver-url]: http://semver.org/
[simpletest-drupal-url]: https://www.drupal.org/docs/7/testing
[standard-version-url]: https://github.com/conventional-changelog/standard-version
[testing-simpletest]: https://www.drupal.org/docs/7/creating-custom-modules/testing-with-simpletest
[travis-image]: https://travis-ci.org/gregswindle/drupal-spike.svg?branch=master
[travis-url]: https://travis-ci.org/gregswindle/drupal-spike
[yarnpkg-url]: https://yarnpkg.com
