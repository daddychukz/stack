The ELB module creates an ELB, security group
a route53 record and a service healthcheck.
It is used by the service module.


## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| dns_name | Route53 record name | string | - | yes |
| environment | Environment tag, e.g prod | string | - | yes |
| healthcheck | Healthcheck path | string | - | yes |
| log_bucket | S3 bucket name to write ELB logs into | string | - | yes |
| name | ELB name, e.g cdn | string | - | yes |
| port | Instance port | string | - | yes |
| protocol | Protocol to use, HTTP or TCP | string | - | yes |
| security_groups | Comma separated list of security group IDs | string | - | yes |
| subnet_ids | Comma separated list of subnet IDs | string | - | yes |
| zone_id | Route53 zone ID to use for dns_name | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| dns | The ELB dns_name. |
| fqdn | FQDN built using the zone domain and name |
| id | The ELB ID. |
| name | The ELB name. |
| zone_id | The zone id of the ELB |

