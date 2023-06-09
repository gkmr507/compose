# Release Process
## Prerequisites
The environment variables `PYPI_USERNAME` and `PYPI_PASSWORD` must be already set in the repository as secrets. To add these variables, go to Secrets in the Settings of the repository.

## Create Release Branch
1. Branch off of main and name the branch the release version number (e.g. `release_v0.1.2`)
2. Bump version number in `composeml/version.py`, and `composeml/tests/test_version.py`.

## Create Release PR
A release PR should have the version number as the title and the changelog updates as the PR body text. The contributors line is not necessary.

## Create GitHub Release
After the release pull request has been merged into the main branch, it is time draft the github release.
* The target should be the main branch
* The tag should be the version number with a v prefix (e.g. v0.1.2)
* Release title is the same as the tag
* Release description should be the full changelog updates for the release, including the line thanking contributors.

## Release on PyPI
After publishing the release on GitHub, a GitHub Action will automatically upload the package to PyPI.