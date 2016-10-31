GitHubWebHook (GWH) Infrastructure As Code Base
--------------------------------------------
Use this repo as a base for anything that should be deployed by 'GWHInfAsCodeDeployer'

 1. Update deploy.sh to do everything needed to deploy this product to aws:
    - download terraform inputs.tfvars and .tfstate file from s3
    - run packer to create new ami with all the latest changes
    - record the old ami value from inputs.tfvars
    - update inputs.tfvars with the latest ami value
    - run terraform to update any infrastructure changes    
    - once the old ami is no longer in use: delete the old ami.
    - upload inputs.tfvars and .tfstate to s3
