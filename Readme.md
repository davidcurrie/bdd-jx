# BDD tests for Jenkins X using [ginkgo](https://github.com/onsi/ginkgo)

## Prerequisits

- __golang__ https://golang.org/doc/install#install
- a Jenkins X installation

## Setup

    make bootstrap
will install ginkgo gomega and dep

## Running the BDD tests

If you are running the tests locally you probably want to set:

    export GIT_ORGANISATION="my_cool_github_username"
    
Then to run all the tests in parallel:

    make test-parallel

If you want the sequential version (You may be some time):

    make test

Or you can run an individual spec like this:

    make test-quickstart-golang-http

## Environment variables

* `GIT_PROVIDER_URL` the git provider URL to test against. e.g. your GitHub Enterprise or BitBucket URL
* `JX_DISABLE_CLEAN_DIR` set to `true` to disable cleaning up of the temporary work directories 
* `JX_DISABLE_DELETE_APP` set to `true` to disable deleting of the app from Jenkins X after a test
* `JX_DISABLE_DELETE_REPO` set to `true` to disable deleting of the repo from Jenkins X after a test
* `JX_DISABLE_TEST_PULL_REQUEST` set to `true` to disable testing the PR workflow
* `JX_DISABLE_WAIT_FOR_FIRST_RELEASE` set to `true` to disable waiting for the first release pipeline to complete. Handy if you are testing/debugging the Pull Request flow as it speeds up the test
