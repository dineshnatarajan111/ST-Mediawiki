# Source of Truth
This repo is used for source of truth for the image deployment and Terraform variables.

Switch branch to see the values of HELM and variables for Terraform

## Working Theory
### HELM values.yaml

When there is a new image is built using a pipeline after pushing the Image with new tag to the image-repository the new tag gets updated by the Image Build pipeline to this repository. 
After the image tag gets updated in this repository a webhook is triggered and automated deployment/upgrade of pods are done by the deployment pipeline.

![Deployment_automation][logo]

[logo]: https://github.com/dineshnatarajan111/ST-Mediawiki/blob/main/img/Deployment_automation.png "Deployment_automation"