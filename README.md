# `drupal-spike`
> :microscope: Automate Drupal testing, coverage, Git commit message validation, CHANGELOG generation, semantic version updates, and source code inspection with CLI tools for continuous integration.

## 1. Table of contents
<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [1. Table of contents](#1-table-of-contents)
- [2. Installation](#2-installation)
	- [2.1. Semantic version and CHANGELOG automation](#21-semantic-version-and-changelog-automation)
	- [2.2. PHP_CodeSniffer and Behat (with code coverage)](#22-phpcodesniffer-and-behat-with-code-coverage)
	- [2.3. `Drupal` and `DrupalPractice` code sniffers](#23-drupal-and-drupalpractice-code-sniffers)
	- [2.4. Drush command-line shell](#24-drush-command-line-shell)
- [3. Usage](#3-usage)
	- [3.1. Git commit message validation](#31-git-commit-message-validation)
	- [3.2. Source code quality analysis and reports](#32-source-code-quality-analysis-and-reports)
	- [3.3. Behavior-Driven Developer (BDD) and code coverage](#33-behavior-driven-developer-bdd-and-code-coverage)
	- [3.4. `CHANGELOG` and semantic version automation](#34-changelog-and-semantic-version-automation)
- [4. Contributing](#4-contributing)
- [5. References](#5-references)
- [6. License](#6-license)

<!-- /TOC -->

## 2. Installation
> **:warning: Prerequisite software**
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

### 2.1. Semantic version and CHANGELOG automation

`drupal-spike` includes

* **[`commitplease`][commitplease-url]**, a [`conventional commit message`][conventional-commit-url] validation pre-commit hook
* **[`standard-version`][standard-version-url]** to automate CHANGELOG generation and [semantic version][semver-url] updates.

### 2.2. Coding standards

`drupal-spike` lints (or "sniffs") PHP for code that doesn't smell like `Drupal` or `DrupalPractice` standards with [PHP_CodeSniffer][php-codesniffer-url].

### 2.3. Testing

`drupal-spike` uses:

* [Behat][behat-url], a Behavior-Driven Development (BDD) framework for writing (unit) tests
*  [`leanphp/behat-code-coverage`][behat-code-coverage-url] to ensure custom PHP source code is covered by specs (née, unit tests).


### 2.4. Drush command-line shell

[Install Drush 7 and 8 Side-by-Side and Automatically Switch Versions Based on Each Project](https://github.com/leanphp/behat-code-coverage#Configuration https://modulesunraveled.com/blog/install-drush-7-and-8-and-automatically-switch-versions-based-project).

## 3. Usage

`drupal-spike` is an attempt to automate testing, coverage, Git commit message validation, `CHANGELOG` generation, semantic version updates, and source code inspection.

### 3.1. Git commit message validation

[Step 2.1.](#21-semantic-version-and-changelog-automation) installs [`commitplease`][commitplease-url], which applies a pre-commit hook with configuration defined in `package.json`.

```sh

<type>(<scope>): <subject>
<BLANK LINE>
<[body]>
<BLANK LINE>
<footer>

```

### 3.2. Source code quality analysis and reports

[Step 2.2.](#22-phpcodesniffer-and-behat-with-code-coverage) enables PHP source code linting with [PHP_CodeSniffer][php-codesniffer-url] using the [Drupal Coder Sniffer](https://www.drupal.org/node/1419988).

The `.travis.yml` has the command to inspect PHP source code compliance with Drupal coding standards.

```yaml

script:
  - vendor/bin/phpcs --standard=Drupal --extensions=php,module,inc,install,test,profile,theme,css,info,txt,md /file/to/drupal/example_module

```

### 3.3. Behavior-Driven Developer (BDD) and code coverage

The `.travis.yml` executes specs.

[Step 2.2.](#22-phpcodesniffer-and-behat-with-code-coverage) also enables BDD and code coverage with [`Behat`][behat-url],  [`leanphp/behat-code-coverage`][behat-code-coverage-url], and sends coverage reports to [`coveralls`][coveralls-url].

```yaml

script:
  - vendor/bin/behat
after_script: 'cat ./coverage/lcov.info | coveralls'

```

### 3.4. `CHANGELOG` and semantic version automation

[Step 2.1.](#21-semantic-version-and-changelog-automation) enables `CHANGELOG` generation and semantic versioning with [`standard-version`][standard-version-url].

```sh

$ npm run release -- --dry-run

```


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

---

[author-info]: https://github.com/gregswindle
[behat-code-coverage-url]: https://github.com/leanphp/behat-code-coverage
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
[drush-url]: https://github.com/drush-ops/drush
[git-commit-guidelines-url]: https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#commit
[git-feat-branch-url]: https://www.atlassian.com/git/tutorials/comparing-workflows#feature-branch-workflow
[gitflow-url]: https://www.atlassian.com/git/tutorials/comparing-workflows#gitflow-workflow
[greenkeeper-image]: https://badges.greenkeeper.io/gregswindle/drupal-spike.svg
[greenkeeper-url]: https://greenkeeper.io/
[issues-url]: https://github.com/gregswindle/drupal-spike/issues
[license-image]: https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=flat-square
[license-url]: ./LICENSE
[license-url]: LICENSE
[nodejs-url]: https://nodejs.org/
[npm-image]: https://badge.fury.io/js/drupal-spike.svg
[npm-url]: https://npmjs.org/package/drupal-spike
[nsp-image]: https://nodesecurity.io/orgs/gregswindle/projects/d0b019ea-5391-4b3c-ba8c-464a24bf8a8c/badge
[nsp-url]: https://nodesecurity.io/orgs/gregswindle/projects/d0b019ea-5391-4b3c-ba8c-464a24bf8a8c
[php-codesniffer-url]: https://github.com/squizlabs/PHP_CodeSniffer
[pr-url]: https://github.com/gregswindle/drupal-spike/pulls
[readme-image]: http://readme-score-api.herokuapp.com/score.svg?url=https%3A%2F%2Fgithub.com%2Fgregswindle%2Fdrupal-spike
[readme-url]: http://clayallsopp.github.io/readme-score?url=https%3A%2F%2Fgithub.com%2Fgregswindle%2Fdrupal-spike
[semantic-release-url]: https://github.com/semantic-release/semantic-release
[semver-url]: http://semver.org/
[standard-version-url]: https://github.com/conventional-changelog/standard-version
[travis-image]: https://travis-ci.org/gregswindle/drupal-spike.svg?branch=master
[travis-url]: https://travis-ci.org/gregswindle/drupal-spike
[yarnpkg-url]: https://yarnpkg.com
