---
title: WordPress
addedAt: 2022-06-09
category: server-app
tags: php-runtime
iconSlug: wordpress
permalink: /wordpress
versionCommand: wp core version
releasePolicyLink: https://codex.wordpress.org/Supported_Versions
changelogTemplate: "https://wordpress.org/documentation/wordpress-version/version-{{'__LATEST__'|drop_zero_patch|replace:'.','-'}}/"
eoasColumn: true
eolColumn: Security Support

customFields:
  - name: supportedPHPVersions
    display: after-release-column
    label: Supported PHP
    description: Supported PHP versions range
    link: https://make.wordpress.org/core/handbook/references/php-compatibility-and-wordpress-versions/

# This regex drops '.0' from versions because x.y.0 releases are always referred to as x.y.
# The patch part is like that to handle properly tiny versions, such as 1.5.1.3, are handled properly.
# But note that this regex would not work if WordPress releases an x.y.0.t version.
# That should not be a problem though, such version were only used with 1.5.1.
# See https://github.com/endoflife-date/endoflife.date/pull/2768#issuecomment-1491875624.
auto:
  methods:
    - git: https://github.com/WordPress/wordpress-develop.git
      regex: '^(?P<major>\d+)\.(?P<minor>\d+)\.?(?P<patch>[1-9][0-9.]*)?'

identifiers:
  - repology: wordpress
  - purl: pkg:docker/library/wordpress
  - purl: pkg:docker/bitnami/wordpress
  - purl: pkg:docker/bitnami/wordpress-nginx
  - cpe: cpe:2.3:a:wordpress:wordpress
  - cpe: cpe:/a:wordpress:wordpress

# eoas(x) = releaseDate(x+1)
# eol: 4.7+ still receive security backports, 4.1-4.6 ended July 2025, 3.7-4.0 ended Dec 2022
# Support PHP version can be found on https://make.wordpress.org/core/handbook/references/php-compatibility-and-wordpress-versions/
releases:
  - releaseCycle: "6.9"
    supportedPHPVersions: "7.2 - 8.5"
    releaseDate: 2025-12-02
    eoas: false
    eol: false
    latest: "6.9.4"
    latestReleaseDate: 2026-03-11

  - releaseCycle: "6.8"
    supportedPHPVersions: "7.2 - 8.4"
    releaseDate: 2025-04-15
    eoas: 2025-12-02
    eol: false
    latest: "6.8.5"
    latestReleaseDate: 2026-03-11

  - releaseCycle: "6.7"
    supportedPHPVersions: "7.2 - 8.4"
    releaseDate: 2024-11-12
    eoas: 2025-04-15
    eol: false
    latest: "6.7.5"
    latestReleaseDate: 2026-03-11

  - releaseCycle: "6.6"
    supportedPHPVersions: "7.2 - 8.3"
    releaseDate: 2024-07-16
    eoas: 2024-11-12 # releaseDate(6.7)
    eol: false
    latest: "6.6.5"
    latestReleaseDate: 2026-03-11

  - releaseCycle: "6.5"
    supportedPHPVersions: "7.0 - 8.3"
    releaseDate: 2024-04-02
    eoas: 2024-07-16 # releaseDate(6.6)
    eol: false
    latest: "6.5.8"
    latestReleaseDate: 2026-03-11

  - releaseCycle: "6.4"
    supportedPHPVersions: "7.0 - 8.3"
    releaseDate: 2023-11-07
    eoas: 2024-04-02 # releaseDate(6.5)
    eol: false
    latest: "6.4.8"
    latestReleaseDate: 2026-03-11

  - releaseCycle: "6.3"
    supportedPHPVersions: "7.0 - 8.2"
    releaseDate: 2023-08-08
    eoas: 2023-11-07 # releaseDate(6.4)
    eol: false
    latest: "6.3.8"
    latestReleaseDate: 2026-03-12

  - releaseCycle: "6.2"
    supportedPHPVersions: "5.6 - 8.2"
    releaseDate: 2023-03-29
    eoas: 2023-08-08 # releaseDate(6.3)
    eol: false
    latest: "6.2.9"
    latestReleaseDate: 2026-03-12

  - releaseCycle: "6.1"
    supportedPHPVersions: "5.6 - 8.2"
    releaseDate: 2022-11-02
    eoas: 2023-03-29 # releaseDate(6.2)
    eol: false
    latest: "6.1.10"
    latestReleaseDate: 2026-03-12

  - releaseCycle: "6.0"
    supportedPHPVersions: "5.6 - 8.1"
    releaseDate: 2022-05-24
    eoas: 2022-11-01 # releaseDate(6.1)
    eol: false
    latest: "6.0.11"
    latestReleaseDate: 2025-09-30

  - releaseCycle: "5.9"
    supportedPHPVersions: "5.6 - 8.1"
    releaseDate: 2022-01-25
    eoas: 2022-05-24 # releaseDate(6.0)
    eol: false
    latest: "5.9.13"
    latestReleaseDate: 2026-03-12

  - releaseCycle: "5.8"
    supportedPHPVersions: "5.6 - 8.0"
    releaseDate: 2021-07-20
    eoas: 2022-01-25 # releaseDate(5.9)
    eol: false
    latest: "5.8.13"
    latestReleaseDate: 2026-03-12

  - releaseCycle: "5.7"
    supportedPHPVersions: "5.6 - 8.0"
    releaseDate: 2021-03-09
    eoas: 2021-07-20 # releaseDate(5.8)
    eol: false
    latest: "5.7.15"
    latestReleaseDate: 2026-03-12

  - releaseCycle: "5.6"
    supportedPHPVersions: "5.6 - 8.0"
    releaseDate: 2020-12-08
    eoas: 2021-03-09 # releaseDate(5.7)
    eol: false
    latest: "5.6.17"
    latestReleaseDate: 2026-03-12

  - releaseCycle: "5.5"
    supportedPHPVersions: "5.6 - 7.4"
    releaseDate: 2020-08-11
    eoas: 2020-12-08 # releaseDate(5.6)
    eol: false
    latest: "5.5.18"
    latestReleaseDate: 2026-03-12

  - releaseCycle: "5.4"
    supportedPHPVersions: "5.6 - 7.4"
    releaseDate: 2020-03-31
    eoas: 2020-08-11 # releaseDate(5.5)
    eol: false
    latest: "5.4.19"
    latestReleaseDate: 2026-03-12

  - releaseCycle: "5.3"
    supportedPHPVersions: "5.6 - 7.4"
    releaseDate: 2019-11-12
    eoas: 2020-03-31 # releaseDate(5.4)
    eol: false
    latest: "5.3.21"
    latestReleaseDate: 2026-03-12

  - releaseCycle: "5.2"
    supportedPHPVersions: "5.6 - 7.3"
    releaseDate: 2019-05-07
    eoas: 2019-11-12 # releaseDate(5.3)
    eol: false
    latest: "5.2.24"
    latestReleaseDate: 2026-03-13

  - releaseCycle: "5.1"
    supportedPHPVersions: "5.2 - 7.3"
    releaseDate: 2019-02-21
    eoas: 2019-05-07 # releaseDate(5.2)
    eol: false
    latest: "5.1.22"
    latestReleaseDate: 2026-03-13

  - releaseCycle: "5.0"
    supportedPHPVersions: "5.2 - 7.3"
    releaseDate: 2018-12-06
    eoas: 2019-02-21 # releaseDate(5.1)
    eol: false
    latest: "5.0.25"
    latestReleaseDate: 2026-03-13

  - releaseCycle: "4.9"
    supportedPHPVersions: "5.2 - 7.2"
    releaseDate: 2017-11-16
    eoas: 2018-12-06 # releaseDate(5.0)
    eol: false
    latest: "4.9.29"
    latestReleaseDate: 2026-03-13

  - releaseCycle: "4.8"
    supportedPHPVersions: "5.2 - 7.1"
    releaseDate: 2017-06-08
    eoas: 2017-11-16 # releaseDate(4.9)
    eol: false
    latest: "4.8.28"
    latestReleaseDate: 2026-03-13

  - releaseCycle: "4.7"
    supportedPHPVersions: "5.2 - 7.1"
    releaseDate: 2016-12-06
    eoas: 2017-06-08 # releaseDate(4.8)
    eol: false
    latest: "4.7.33"
    latestReleaseDate: 2026-03-27

  - releaseCycle: "4.6"
    supportedPHPVersions: "5.2 - 7.0"
    releaseDate: 2016-08-16
    eoas: 2016-12-06 # releaseDate(4.7)
    eol: 2025-07-15 # https://make.wordpress.org/security/2025/06/18/security-updates-will-cease-for-wordpress-versions-4-1-through-4-6/
    latest: "4.6.30"
    latestReleaseDate: 2025-07-15
    link: https://wordpress.org/news/2025/07/wordpress-6-8-2-maintenance-release/ # https://github.com/endoflife-date/endoflife.date/pull/7935

  - releaseCycle: "4.5"
    supportedPHPVersions: "5.2 - 7.0"
    releaseDate: 2016-04-12
    eoas: 2016-08-16 # releaseDate(4.6)
    eol: 2025-07-15 # https://make.wordpress.org/security/2025/06/18/security-updates-will-cease-for-wordpress-versions-4-1-through-4-6/
    latest: "4.5.33"
    latestReleaseDate: 2025-07-15

  - releaseCycle: "4.4"
    supportedPHPVersions: "5.2 - 7.0"
    releaseDate: 2015-12-09
    eoas: 2016-04-12 # releaseDate(4.5)
    eol: 2025-07-15 # https://make.wordpress.org/security/2025/06/18/security-updates-will-cease-for-wordpress-versions-4-1-through-4-6/
    latest: "4.4.34"
    latestReleaseDate: 2025-07-15

  - releaseCycle: "4.3"
    supportedPHPVersions: "5.2 - 5.6"
    releaseDate: 2015-08-18
    eoas: 2015-12-08 # releaseDate(4.4)
    eol: 2025-07-15 # https://make.wordpress.org/security/2025/06/18/security-updates-will-cease-for-wordpress-versions-4-1-through-4-6/
    latest: "4.3.35"
    latestReleaseDate: 2025-07-15

  - releaseCycle: "4.2"
    supportedPHPVersions: "5.2 - 5.6"
    releaseDate: 2015-04-23
    eoas: 2015-08-18 # releaseDate(4.3)
    eol: 2025-07-15 # https://make.wordpress.org/security/2025/06/18/security-updates-will-cease-for-wordpress-versions-4-1-through-4-6/
    latest: "4.2.39"
    latestReleaseDate: 2025-07-15

  - releaseCycle: "4.1"
    supportedPHPVersions: "5.2 - 5.6"
    releaseDate: 2014-12-18
    eoas: 2015-04-23 # releaseDate(4.2)
    eol: 2025-07-15 # https://make.wordpress.org/security/2025/06/18/security-updates-will-cease-for-wordpress-versions-4-1-through-4-6/
    latest: "4.1.42"
    latestReleaseDate: 2025-07-15

  - releaseCycle: "4.0"
    supportedPHPVersions: "5.2 - 5.5"
    releaseDate: 2014-09-04
    eoas: 2014-12-18 # releaseDate(4.1)
    eol: 2022-12-01 # https://make.wordpress.org/security/2022/09/07/dropping-security-updates-for-wordpress-versions-3-7-through-4-0/
    latest: "4.0.38"
    latestReleaseDate: 2022-11-30

  - releaseCycle: "3.9"
    supportedPHPVersions: "5.2 - 5.5"
    releaseDate: 2014-04-16
    eoas: 2014-09-04 # releaseDate(4.0)
    eol: 2022-12-01 # https://make.wordpress.org/security/2022/09/07/dropping-security-updates-for-wordpress-versions-3-7-through-4-0/
    latest: "3.9.40"
    latestReleaseDate: 2022-11-30

  - releaseCycle: "3.8"
    supportedPHPVersions: "5.2 - 5.5"
    releaseDate: 2013-12-12
    eoas: 2014-04-16 # releaseDate(3.9)
    eol: 2022-12-01 # https://make.wordpress.org/security/2022/09/07/dropping-security-updates-for-wordpress-versions-3-7-through-4-0/
    latest: "3.8.41"
    latestReleaseDate: 2022-11-30

  - releaseCycle: "3.7"
    supportedPHPVersions: "5.2 - 5.5"
    releaseDate: 2013-10-24
    eoas: 2013-12-12 # releaseDate(3.8)
    eol: 2022-12-01 # https://make.wordpress.org/security/2022/09/07/dropping-security-updates-for-wordpress-versions-3-7-through-4-0/
    latest: "3.7.41"
    latestReleaseDate: 2022-11-30

  - releaseCycle: "3.6"
    releaseDate: 2013-08-01
    eoas: 2013-10-24 # releaseDate(3.7)
    eol: 2013-10-24 # releaseDate(3.7), no security backports
    latest: "3.6.1"
    latestReleaseDate: 2013-09-11

---

> [WordPress](https://wordpress.org/) is a free and open-source content management system (CMS)
> written in PHP and paired with a MySQL or MariaDB database. Features include a plugin architecture
> and a template system, referred to within WordPress as "Themes".

The only officially supported and actively maintained version of WordPress is the latest one.

Security updates are backported to older releases when possible, but the WordPress team offers no
guarantee and no timeframe. Versions 4.7 and above still receive security backports. Versions 4.1
through 4.6 [received their last security update in July
2025](https://make.wordpress.org/security/2025/06/18/security-updates-will-cease-for-wordpress-versions-4-1-through-4-6/),
and versions 3.7 through 4.0 [received their last security update on December 1,
2022](https://make.wordpress.org/security/2022/09/07/dropping-security-updates-for-wordpress-versions-3-7-through-4-0/).
Versions below 3.7 do not receive security backports.
