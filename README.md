# Platform Ops 🔧

# What is this?
Ops side of the platform

This repo is meant to be used by:
- Platform Engineers
- SRE
- DevOps
- Operators

In this repo we define what is installed in every cluster.

# Components

## [ArgoCD apps](/apps/)
Apps installed in every cluster. These are ops apps, that is, helpers. A great example is certmanager: is not really an app that we work on but it is something that we need in every cluster.

Each cluster has an ApplicationSet watching this folder. Applications will be installed following the `./apps/{APP_NAME}/overlays/(dev|prod)` pattern.
These apps go under the platform-ops ArgoCD project.

## `[deprecated]` [Foundations](/ignore/foundations/)
Foundational resources for the organisation such as folders and policies. Mostly GCP related.

## `[deprecated]` [Crossplane](/ignore/crossplane/) (will be replaced with something else)
Used to define high level abstractions offered to the rest of the company to make their lives easier.

# What's next?
The original idea was to manage abstractions from this repo using the resource-operator model but after loosing all my hair fighting agains the tools *(I'm looking at you `kustomize` and `crossplane`)* I decided to switch to [Pulumi](https://www.pulumi.com/) and unleash the full power of a programing language. Enter the [`Core Pipeline`](https://github.com/francisco-com-au/core-pipeline).

The Core Pipeline handles:
- GCP resources
- Abstractions defined in beautiful strongly typed TypeScript (adiós weird yaml schemas)
- Creation of kube manifests, repos and projects

This effectively means that Crossplane is no longer required.