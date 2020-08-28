# Quarkus Lab ![OCP](https://img.shields.io/badge/OCP-4.4.3-green)

## Table of Contents
 * Introduction
 * Environment Prerequisites
 * Setup

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

1. Clone this repository into your local directory

2. Copy the stack.imagestream.yaml file fom the `stack` branch into your (now cloned) project directory

3. Log on to your OpenShift console as a cluster admin from your terminal (recommended). You will occasionally require your UI console in later steps.

4. Create a project called `codeready`
```
$ oc new-project codeready
```

5. Ensure that you are on `Administrator` view on your browser console.

6. [Install CodeReady Workspaces and navigate to the CodeReady Workspaces URL](https://access.redhat.com/documentation/en-us/red_hat_codeready_workspaces/2.0/html/installation_guide/installing-codeready-workspaces-on-ocp-4_crw) (Skip step 1.1.1, though - you created a project already!)

7. Enter the following commands to import the quarkus stack image

```
$ oc create -n openshift -f stack.imagestream.yaml
$ oc import-image --all quarkus-stack -n openshift
```

8. Switch to `Developer` view on your UI console, to check that the codeready workspace operator has been deployed.

9. Once deployed, open the 'Codeready' URL.

10. Register if you have not already, and log in.

11. You will now create a Quarkus workspace for you to use. Select the `Custom Workspace` tab.

12. In the `Workspace Name` field, enter `quarkus-lab` as the workspace name.

13. In the `devfile` section, select the 'URL of devfile' field and enter the following devfile URL:

https://raw.githubusercontent.com/akouao/quarkus-lab/devfile/devfile.yaml

14. Hit the `Load devfile` button to ensure that the configuration is loaded.

15. Your configuration is all set. Wait for 2-3 minutes for your workspace to load, and look forward to Quarkus wow-ing you!