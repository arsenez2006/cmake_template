# CMake project template
Contains usefull configurations and workflows for a CMake based project

## Repository structure
- `master` branch contains only releases
- `dev` branch for developing the project

## How to use
### Commiting
The correct way to develop a project based on this template is to make all your commits and PR's to the `dev` branch. When the `dev` branch is ready to release, just merge it into `master` and a new release will be created automatically.

### Repository variables
- `RELEASE_NAME` - contains common release title. e.g. `RELEASE_NAME` = "Awesome project" will produce releases with title `Awesome project v1.2.3`
- `CMAKE_BUILD_RELEASE` - contains new-line separated list of files/binaries from `CMAKE_INSTALL_PREFIX` which will be attached to release

## Workflows
### .github/workflows/main.yml (Main workflow)
- `Build CMake project (build)` - builds the project and stores it as an artifact
- `Create version (version)` - creates new version tags on each commit. See https://github.com/codacy/git-version#versioning-model
- `Create release (release)` - creates new release when pushed into `master` branch
### .github/workflows/security.yml (Security check)
- `Code security scan (security_scan)` - runs static analysis with GitHub code scanning integration
