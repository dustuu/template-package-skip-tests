* [template-package-skip-tests](https://github.com/dustuu/template-package-skip-tests) shows what happens when only the `PACKAGE_NAME` variable is set, but none of the variables or secrets needed for running Unit Tests are. This is how workflows will run for users who don't opt-in to the new automatic Unit Tests feature, which is likely to be most users.
  * The `Build Release` workflow will skip the `test` job because it is missing the necessary configuration, but will run the `build` job and make a release:
  * ![image](https://github.com/vrchat-community/template-package/assets/101824882/b29be3cb-7667-488f-916b-33d89259c206)
  * The `Build Repo Listing` workflow will be trigged to run and will succeed.

The VPM Badge will work because we had a successful release, but the Code Coverage badge is broken because we did not generate a Code Coverage Report:

[![VPM Package Version](https://img.shields.io/vpm/v/com.vrchat.demo-template?repository_url=https%3A%2F%2Fdustuu.github.io%2Ftemplate-package-skip-tests%2Findex.json)](https://dustuu.github.io/template-package-skip-tests)

[![Code Coverage](https://dustuu.github.io/template-package-unconfigured/coverage/badge_linecoverage.svg)](https://dustuu.github.io/template-package-skip-tests/coverage)
