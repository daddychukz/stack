The ELB module creates an ELB, security group
a route53 record and a service healthcheck.
It is used by the service module.


## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| environment | Environment tag, e.g prod | string | - | yes |
| external_dns_name | The subdomain under which the ELB is exposed externally, defaults to the task name | string | - | yes |
| external_zone_id | The zone ID to create the record in | string | - | yes |
| healthcheck | Healthcheck path | string | - | yes |
| internal_dns_name | The subdomain under which the ELB is exposed internally, defaults to the task name | string | - | yes |
| internal_zone_id | The zone ID to create the record in | string | - | yes |
| log_bucket | S3 bucket name to write ELB logs into | string | - | yes |
| name | ELB name, e.g cdn | string | - | yes |
| port | Instance port | string | - | yes |
| security_groups | Comma separated list of security group IDs | string | - | yes |
| ssl_certificate_id |  | string | - | yes |
| subnet_ids | Comma separated list of subnet IDs | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| dns | The ELB dns_name. |
| external_fqdn | FQDN built using the zone domain and name (external) |
| id | The ELB ID. |
| internal_fqdn | FQDN built using the zone domain and name (internal) |
| name | The ELB name. |
| zone_id | The zone id of the ELB |

