# Quarkus Lab Stack

This Quarkus Stack image allows for the use of GraalVM and other components in CodeReady. No installation required.

1. Log in as cluster admin on your terminal
2. `oc project project-name`
3. `oc create -n openshift -f stack.imagestream.yaml`
4. `oc import-image --all quarkus-stack -n openshift`