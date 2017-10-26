The bastion host acts as the "jump point" for the rest of the infrastructure.
Since most of our instances aren't exposed to the external internet, the bastion acts as the gatekeeper for any direct SSH access.
The bastion is provisioned using the key name that you pass to the stack (and hopefully have stored somewhere).
If you ever need to access an instance directly, you can do it by "jumping through" the bastion.

   $ terraform output # print the bastion ip
   $ ssh -i <path/to/key> ubuntu@<bastion-ip> ssh ubuntu@<internal-ip>

Usage:

   module "bastion" {
     source            = "github.com/segmentio/stack/bastion"
     region            = "us-west-2"
     security_groups   = "sg-1,sg-2"
     vpc_id            = "vpc-12"
     key_name          = "ssh-key"
     subnet_id         = "pub-1"
     environment       = "prod"
   }



## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| environment | Environment tag, e.g prod | string | - | yes |
| instance_type | Instance type, see a list at: https://aws.amazon.com/ec2/instance-types/ | string | `t2.micro` | no |
| key_name | The SSH key pair, key name | string | - | yes |
| region | AWS Region, e.g us-west-2 | string | - | yes |
| security_groups | a comma separated lists of security group IDs | string | - | yes |
| subnet_id | A external subnet id | string | - | yes |
| vpc_id | VPC ID | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| external_ip | Bastion external IP address. |

