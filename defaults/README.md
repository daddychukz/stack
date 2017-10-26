This module is used to set configuration defaults for the AWS infrastructure.
It doesn't provide much value when used on its own because terraform makes it
hard to do dynamic generations of things like subnets, for now it's used as
a helper module for the stack.

Usage:

    module "defaults" {
      source = "github.com/segmentio/stack/defaults"
      region = "us-east-1"
      cidr   = "10.0.0.0/16"
    }



## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| cidr | The CIDR block to provision for the VPC | string | - | yes |
| default_ecs_ami |  | string | `<map>` | no |
| default_log_account_ids | http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/enable-access-logs.html#attach-bucket-policy | string | `<map>` | no |
| region | The AWS region | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| domain_name_servers |  |
| ecs_ami |  |
| s3_logs_account_id |  |

