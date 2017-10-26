ECS Cluster creates a cluster with the following features:

 - Autoscaling groups
 - Instance tags for filtering
 - EBS volume for docker resources


Usage:

     module "cdn" {
       source               = "github.com/segmentio/stack/ecs-cluster"
       environment          = "prod"
       name                 = "cdn"
       vpc_id               = "vpc-id"
       image_id             = "ami-id"
       subnet_ids           = ["1" ,"2"]
       key_name             = "ssh-key"
       security_groups      = "1,2"
       iam_instance_profile = "id"
       region               = "us-west-2"
       availability_zones   = ["a", "b"]
       instance_type        = "t2.small"
     }



## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| associate_public_ip_address | Should created instances be publicly accessible (if the SG allows) | string | `false` | no |
| availability_zones | List of AZs | list | - | yes |
| desired_capacity | Desired instance count | string | `3` | no |
| docker_auth_data | A JSON object providing the docker auth data, see https://godoc.org/github.com/aws/amazon-ecs-agent/agent/engine/dockerauth for the supported formats | string | `` | no |
| docker_auth_type | The docker auth type, see https://godoc.org/github.com/aws/amazon-ecs-agent/agent/engine/dockerauth for the possible values | string | `` | no |
| docker_volume_size | Attached EBS volume size in GB | string | `25` | no |
| environment | Environment tag, e.g prod | string | - | yes |
| extra_cloud_config_content | Extra cloud config content | string | `` | no |
| extra_cloud_config_type | Extra cloud config type | string | `text/cloud-config` | no |
| iam_instance_profile | Instance profile ARN to use in the launch configuration | string | - | yes |
| image_id | AMI Image ID | string | - | yes |
| instance_ebs_optimized | When set to true the instance will be launched with EBS optimized turned on | string | `true` | no |
| instance_type | The instance type to use, e.g t2.small | string | - | yes |
| key_name | SSH key name to use | string | - | yes |
| max_size | Maxmimum instance count | string | `100` | no |
| min_size | Minimum instance count | string | `3` | no |
| name | The cluster name, e.g cdn | string | - | yes |
| region | AWS Region | string | - | yes |
| root_volume_size | Root volume size in GB | string | `25` | no |
| security_groups | Comma separated list of security groups | string | - | yes |
| subnet_ids | List of subnet IDs | list | - | yes |
| vpc_id | VPC ID | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| name | The cluster name, e.g cdn |
| security_group_id | The cluster security group ID. |

