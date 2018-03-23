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


Resource Variables

security_groups
  name
  exported: True
  ingress:
  - ip_proto: 'tcp'
    from_port: '0'
    to_port: '65535'
    self: True

iam_roles
- name
  assume_role_policy
  policies

instance_profiles
- name
  role

common
  ami: "{{pxy_ami}}"
  instance_profile: "{{iam_stack.stack_outputs.InstanceProfile}}"
  instance_type: "{{pxy_instance}}"
  tags:
    SwitchOff: "false"
    Hours: "24x7"
    Role: "proxy"
  key_name: 'f5-prod'
  userdata: proxy_user_data
  nic:
  - name: eth0
    subnet: "sn-svc-id"
    private_ip: '10.241.5.96'
    sg: 'traffic'
  disk:
  - size: 30
    type: "gp2"

vms
- name
  az: "b"
  tags
