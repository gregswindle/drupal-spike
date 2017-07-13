# `reports/` directory

> **📂  Parent directory for `PHP_Testability`, `PHP_CodeSniffer`, `ESLint`, functional test, integration test, unit test, and code coverage reports.**

```sh
# Example directory structure
reports
├── README.md
├── e2e
│   └── default.xml
└── php-testability
    ├── features
    │   ├── bootstrap
    │   │   ├── FeatureContext.php.html
    │   │   └── index.html
    │   └── index.html
    ├── index.html
    └── sites
        ├── example.sites.php.html
        └── index.html
```

---

## Quality assurance dashboard
[![Quality Gate][sonar-gate-img]][sonar-gate-url]

> 🔬  Assess code quality, security vulnerabilities, code smells, test coverage, duplications, technical debt, reliability, maintainability, complexity, and blocking issues.
>
> 📊 Select the badges below for detailed SonarQube reports.

| Measure             | Scores                                                             |
|:--------------------|:-------------------------------------------------------------------|
| **Complexity**      | [![Complexity][sonar-complexity-img]][sonar-complexity-url] [![Cognitive complexity][sonar-cognitive-img]][sonar-cognitive-url] |
| **Coverage**        | [![Sonar coverage][sonar-coverage-img]][sonar-coverage-url]        |
| **Duplications**    | [![Duplications][sonar-duplications-img]][sonar-duplications-url]  |
| **Issues**          | [![Issues][sonar-issues-img]][sonar-issues-url]                    |
| **Maintainability** | [![Code smells][sonar-code-smells-img]][sonar-code-smells-url]  [![Maintainability][sonar-maintainability-img]][sonar-maintainability-url] [![Technical debt][sonar-tech-debt-img]][sonar-tech-debt-url] |
| **Reliability**     | [![Reliability][sonar-reliability-img]][sonar-reliability-url]     |
| **Security**        | [![Security][sonar-security-img]][sonar-security-url]              |

---

[Apache-2.0][license-url] © [Greg Swindle][gregswindle-url]


[gregswindle-url]: https://github.com/gregswindle
[inch-ci-img]: http://inch-ci.org/github/gregswindle/drupal-spike.svg?branch=master
[inch-ci-url]: http://inch-ci.org/github/gregswindle/drupal-spike
[license-url]: https://www.apache.org/licenses/LICENSE-2.0
[sonar-code-smells-img]: http://sonarcloud.io/api/badges/measure?key=gregswindle-drupal-spike&metric=code_smells
[sonar-code-smells-url]: https://sonarcloud.io/component_measures/metric/code_smells/list?id=gregswindle-drupal-spike
[sonar-cognitive-img]: http://sonarcloud.io/api/badges/measure?key=gregswindle-drupal-spike&metric=cognitive_complexity
[sonar-cognitive-url]: https://sonarcloud.io/component_measures/metric/cognitive_complexity/list?id=gregswindle-drupal-spike
[sonar-complexity-img]: http://sonarcloud.io/api/badges/measure?key=gregswindle-drupal-spike&metric=function_complexity
[sonar-complexity-url]: https://sonarcloud.io/component_measures/domain/Complexity?id=gregswindle-drupal-spike
[sonar-coverage-img]: http://sonarcloud.io/api/badges/measure?key=gregswindle-drupal-spike&metric=coverage
[sonar-coverage-url]: https://sonarcloud.io/component_measures/domain/Coverage?id=gregswindle-drupal-spike
[sonar-duplications-img]: http://sonarcloud.io/api/badges/measure?key=gregswindle-drupal-spike&metric=duplicated_line_density
[sonar-duplications-url]: https://sonarcloud.io/component_measures/domain/Duplications?id=gregswindle-drupal-spike
[sonar-gate-img]: http://sonarcloud.io/api/badges/gate?key=gregswindle-drupal-spike
[sonar-gate-url]: http://sonarcloud.io/dashboard/index/gregswindle-drupal-spike
[sonar-issues-img]: http://sonarcloud.io/api/badges/measure?key=gregswindle-drupal-spike&metric=blocker_violations
[sonar-issues-url]: https://sonarcloud.io/component_measures/domain/Issues?id=gregswindle-drupal-spike
[sonar-maintainability-img]: http://sonarcloud.io/api/badges/measure?key=gregswindle-drupal-spike&metric=new_maintainability_rating
[sonar-maintainability-url]: https://sonarcloud.io/component_measures/domain/Maintainability?id=gregswindle-drupal-spike
[sonar-reliability-img]: http://sonarcloud.io/api/badges/measure?key=gregswindle-drupal-spike&metric=new_reliability_rating
[sonar-reliability-url]: https://sonarcloud.io/component_measures/domain/Reliability?id=gregswindle-drupal-spike
[sonar-security-img]: http://sonarcloud.io/api/badges/measure?key=gregswindle-drupal-spike&metric=vulnerabilities
[sonar-security-url]: https://sonarcloud.io/component_measures/domain/Security?id=gregswindle-drupal-spike
[sonar-tech-debt-img]:  https://sonarcloud.io/api/badges/measure?key=gregswindle-drupal-spike&metric=sqale_debt_ratio
[sonar-tech-debt-url]: https://sonarcloud.io/component_measures/metric/sqale_index/list?id=gregswindle-drupal-spike
