Creates basic security groups to be used by instances and ELBs.


## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| cidr | The cidr block to use for internal security groups | string | - | yes |
| environment | The environment, used for tagging, e.g prod | string | - | yes |
| name | The name of the security groups serves as a prefix, e.g stack | string | - | yes |
| vpc_id | The VPC ID | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| external_elb | External ELB allows traffic from the world. |
| external_ssh | External SSH allows ssh connections on port 22 from the world. |
| internal_elb | Internal ELB allows internal traffic. |
| internal_ssh | Internal SSH allows ssh connections from the external ssh security group. |

