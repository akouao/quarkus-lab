# Quarkus Lab ![OCP](https://img.shields.io/badge/OCP-4.4.3-green)

## Table of Contents
 * Introduction
 * Introductory Topics Covered
 * Environment Prerequisites
 * Getting Started

## Introduction

Current maintainer: Ally Kouao <akouao@redhat.com>

Original content can be found at [RedHat-Middleware-Workshop / Quarkus Workshop](https://github.com/RedHat-Middleware-Workshops/quarkus-workshop)

This workshop is an introduction to the capabilities of [Quarkus](https://quarkus.io); supersonic, subatomic container-native Java, and forms part of the Developer Experience (DevEx) workshops. The workshop uses [Red Hat CodeReady Workspaces](https://www.redhat.com/en/technologies/jboss-middleware/codeready-workspaces) to develop a simple Quarkus apps, and covers a few developr topics such as:

* Dependency Injection
* Building Native Quarkus Apps
* Documenting and Testing APIs

## Environment Prequisities

Assumes you have a running OpenShift 4 cluster and have:

- OpenShift 4 CLI `oc` for your environment from https://mirror.openshift.com/pub/openshift-v4/clients/ocp/latest/.

If you not have OCP4 cluster then please proceed to [https://try.openshift.com](try.openshift.com) to get one installed and configured before proceeding to next section.

## Setup

1. Log on to your console as a cluster admin on your terminal (recommended). You will occasionally require your UI console in later steps.

2. Create a project called `quarkus-lab`
```
$ oc new-project quarkus-lab`
```

3. Ensure that you are on `Administrator` view

4. [Install CodeReady Workspaces and navigate to the CodeReady Workspaces URL](https://access.redhat.com/documentation/en-us/red_hat_codeready_workspaces/2.0/html/installation_guide/installing-codeready-workspaces-on-ocp-4_crw) (Skip step 1.1.1, though - you created a project already!)

5. Create and import quarkus-stack image on the `stack` branch
```
$ oc create -n openshift -f stack.imagestream.yaml
$ oc import-image --all quarkus-stack -n openshift
```

6. Switch to `Developer` view on the UI console

7. Once the CodeReady Workspaces instace is ready, open the URL and login

8. Select the option to create a custom Quarkus project. Ensure that the workspace name is `quarkus lab`

9. Manually remove the pre-made project, and add the URL of this [repository](https://github.com/akouao/quarkus-lab).

10. Navigate to the `devfile` tab. Use the raw URL of `devfile.yaml`

11. Click 'Create and open'

12. Look forward to Quarkus' wow-ing you!