This role can be used to generate Terraform files

Variables:

region: region for the cloud Provider
aws_account_id: numeric ID of the AWS account
profile: optional profile name to use for authentication with the cloud
         (see .aws/config)

Terraform Variables
import_state: array of remote states to reference in your terraform
- key:
  name:
  region: (optional)
  account_id:(optional)
  profile:   (optional)


YNAP Variables

env: environment
project: project
app: application
