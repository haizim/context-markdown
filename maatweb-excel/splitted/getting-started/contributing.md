[#](#contributing) Contributing
===============================

*   [Important Links](#important-links)
*   [Etiquette](#etiquette)
*   [Viability](#viability)
*   [How to submit changes?](#how-to-submit-changes)
*   [How to report a bug?](#how-to-report-a-bug)
*   [PR Requirements](#pr-requirements)

Please read and understand the contribution guide before creating an issue or pull request.

[#](#important-links) Important Links
-------------------------------------

*   [Docs (opens new window)](https://docs.laravel-excel.com/)
*   [Issue tracker (opens new window)](https://github.com/SpartnerNL/Laravel-Excel/issues)
*   [Support](/3.1/getting-started/support.html)

[#](#etiquette) Etiquette
-------------------------

This project is an open source project, and as such, the maintainers use their free time to build and maintain it. The code is freely available and can be used, forked and modified.

Please be considerate towards maintainers when raising issues or presenting pull requests.

It's the duty of the maintainer to ensure that all submissions to the project are of sufficient quality to benefit the project. Many developers have different skill sets, strengths, and weaknesses. Respect the maintainer's decision, and do not be upset or abusive if your submission is not used.

[#](#viability) Viability
-------------------------

When requesting or submitting new features, first consider whether it might be useful to others. Open source projects are used by many developers, who may have entirely different needs to your own. Think about whether or not your feature is likely to be used by other users of the project.

[#](#how-to-submit-changes) How to submit changes?
--------------------------------------------------

*   Check the codebase to ensure that your feature doesn't already exist.
*   Check the pull requests to ensure that another person hasn't already submitted the feature or fix.
*   Use the [pull request template (opens new window)](https://github.com/SpartnerNL/Laravel-Excel/blob/3.1/.github/PULL_REQUEST_TEMPLATE.md).

[#](#how-to-report-a-bug) How to report a bug?
----------------------------------------------

*   Attempt to replicate the problem, to ensure that it wasn't a coincidental incident.
*   Check to make sure your bug report isn't already present within the project.
*   Check the pull requests tab to ensure that the bug doesn't have a fix in progress.
*   Check the pull requests tab to ensure that the feature isn't already in progress.
*   Use the [issue template (opens new window)](https://github.com/SpartnerNL/Laravel-Excel/blob/3.1/.github/ISSUE_TEMPLATE.md).

[#](#pr-requirements) PR Requirements
-------------------------------------

*   The PR **must** apply to [PSR-2 Coding Standard (opens new window)](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md). StyleCI help you detect code style issues.
*   The PR **must** be as clean as possible. Try to remove all inline TODOs and unneeded comments. They are noise and distraction for the reviewer. Use Github's (inline) comment system to start a discussion about a change.
*   The existing tests **must** not fail after your changes. This would indicate that existing functionality is broken and should be addressed before a review is started. You can run the test by running `vendor/bin/phpunit`
*   The changes **must** be backed-up with tests.
*   The PR **must** only have one feature. Split up multiple features in multiple PRs, so they can be individually reviewed and merged.
*   The PR **must** be accompanied by a PR to the docs in case of new features. Documentation is located in the [https://github.com/SpartnerNL/laravel-excel-docs (opens new window)](https://github.com/SpartnerNL/laravel-excel-docs) repository.
*   The PR should contain meaningful commit messages.