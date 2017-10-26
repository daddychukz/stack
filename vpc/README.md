
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| availability_zones | List of availability zones | list | - | yes |
| cidr | The CIDR block for the VPC. | string | - | yes |
| environment | Environment tag, e.g prod | string | - | yes |
| external_subnets | List of external subnets | list | - | yes |
| internal_subnets | List of internal subnets | list | - | yes |
| name | Name tag, e.g stack | string | `stack` | no |

## Outputs

| Name | Description |
|------|-------------|
| availability_zones | The list of availability zones of the VPC. |
| external_rtb_id | The external route table ID. |
| external_subnets | A comma-separated list of subnet IDs. |
| id | The VPC ID |
| internal_nat_ips | The list of EIPs associated with the internal subnets. |
| internal_rtb_id | The internal route table ID. |
| internal_subnets | A list of subnet IDs. |
| security_group | The default VPC security group ID. |

