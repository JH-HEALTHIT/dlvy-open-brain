# Building and Deploying OpenBrain to the HIT AKS Clusters

This repository is set up to deploy via Azure DevOps to the HIT Platform AKS prod cluster. The relevant code for a deployment can be found in [kubernetes-deployment](./integrations/kubernetes-deployment/).

## Building Docker Container

First, you will need to ensure the Docker container exists in our ACR. You can build a new version of the container by tagging the latest commit with `build/vX.Y.Z-DATE`, where `X.Y.Z` is the version number of the image to build (e.g. `1.0.1`) and `DATE` is the current date (e.g. `20260707`). This will build in the [Azure DevOps pipeline](https://dev.azure.com/JH-HealthIT/DELIVERY/_build?definitionId=288) and push the image to our ACR once complete.

## Deploying to AKS

After the Docker container has been pushed to the ACR, it can be deployed into AKS. Tag the latest commit with `deploy/vX.Y.Z-DATE`, where `X.Y.Z` is the version number of a built image (e.g. `1.0.1`) and `DATE` is the current date (e.g. `20260707`). This will deploy in the [Azure DevOps pipeline](https://dev.azure.com/JH-HealthIT/DELIVERY/_build?definitionId=289) and be available at <https://openbrain.hit.jh.edu/> once complete.
