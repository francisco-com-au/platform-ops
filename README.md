# platform-ops

Ops side of the platform

This repo is meant to be used by:
- Platform Engineers
- SRE
- DevOps
- Operators

In this repo we define what is installed in the cluster and what is offered to developers.

## ArgoCD apps
Apps installed in every cluster. These are ops apps, that is, helpers. A great example is certmanager: is not really an app that we work on but it is something that we need in every cluster.
There is an ApplicationSet watching this folder. Applications will be installed following the `./apps/{APP_NAME}/overlays/(dev|prod)` pattern.

## `[deprecated]` Foundations
Foundational resources for the organisation such as folders and policies. Mostly GCP related.

## `[deprecated]` Crossplane (will be replaced with something else)
Used to define high level abstractions offered to the rest of the company to make their lives easier.