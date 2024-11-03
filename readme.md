# TestReleaseGitAction

The purpose of the repository is to develop and test and automated release process to the public darwin-eu organisaton using github actions.

The Action can be used in the following workflows:

1) Manual Dispatch
- The package needs to be fully tested and ready to be released
- The description files is updated with an new version number (higher than the previous version)
- The Action is manually started on Main,

2) On Pull request from develop to Main for this repositories that have been setup using GitFlow strategy.
- The package needs to be fully tested and ready to be released on the develop branch
- The description files is updated with an new version number (higher than the previous version
- The Action is automatically executed on the push to Main (note not on the pull request because then the older version is released)

The Action performs the following steps:

1) it gets the current version from DESCRIPTION
2) it gets the name of the packagw from the DESCRIPTION
3) it creates a release in the darwin-eu-dev with body referring to NEWS.md
4) it pulls the new release into the darwin-eu repository with the same name.
5) it creates a release in the darwin-eu repository.

The Action can be copied to any repository without changes.
