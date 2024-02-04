# Source of Truth
This repo is used for source of truth for the image deployment and Terraform variables.

Switch branch to see the values of HELM and variables for Terraform

## Working Theory
### HELM values.yaml

When there is a new image is built using a pipeline after pushing the Image with new tag to the image-repository the new tag gets updated by the Image Build pipeline to this repository. 
After the image tag gets updated in this repository a webhook is triggered and automated deployment/upgrade of pods are done by the deployment pipeline.

![Deployment_automation][logo1]

[logo1]: https://github.com/dineshnatarajan111/ST-Mediawiki/blob/main/img/Deployment_automation.png "Deployment_automation"

### Terraform variables

To create a new Environment duplicate the available tfstate file and pdate the changes which are Environment specific and commit the changes to the branch. Trigger a pipeline job responsible to Create/Destroy 
the Enironment.

![Environment Creation][logo2]

[logo2]: https://github.com/dineshnatarajan111/ST-Mediawiki/blob/main/img/Terraform_statefile.png "Environment Creation"