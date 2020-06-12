# Introduction

This sample uses kustomize + flux HelmReleases to manage different configurations for prod and dev environments. This sample referenced as a tenant in the soft multi-tenancy sample using Arc for K8s for gitops enablement found here: [arc-demo-multi-tenancy](https://github.com/Azure-Samples/arc-demo-multi-tenancy)

## Branches

- `master` intended to be locked down, this is the source of truth for all cluster deployment
- `dev` contains working changes to be tested.

## Contents

- base - base manifests: HelmRelease to release charts
- charts - helm charts
- dev - use base, but path to deploy dev branch. This makes it so you can test changes from any branch in the dev environment.
- prod - use base as is

## POC Workflow

1. Commit change to dev branch.
1. Observe change in dev environment and not prod
1. Pull request into master
1. Approve pull request
1. Observe changes in prod environment
