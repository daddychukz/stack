The web-service is similar to the `service` module, but the
it provides a __public__ ELB instead.

Usage:

     module "auth_service" {
       source    = "github.com/segmentio/stack/service"
       name      = "auth-service"
       image     = "auth-service"
       cluster   = "default"
     }



## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| cluster | The cluster name or ARN | string | - | yes |
| command | The raw json of the task command | string | `[]` | no |
| container_port | The container port | string | `3000` | no |
| cpu | The number of cpu units to reserve for the container | string | `512` | no |
| deployment_maximum_percent | upper limit (% of desired_count) of # of running tasks during a deployment | string | `200` | no |
| deployment_minimum_healthy_percent | lower limit (% of desired_count) of # of running tasks during a deployment | string | `100` | no |
| desired_count | The desired count | string | `2` | no |
| env_vars | The raw json of the task env vars | string | `[]` | no |
| environment | Environment tag, e.g prod | string | - | yes |
| external_dns_name | The subdomain under which the ELB is exposed externally, defaults to the task name | string | `` | no |
| external_zone_id | The zone ID to create the record in | string | - | yes |
| healthcheck | Path to a healthcheck endpoint | string | `/` | no |
| iam_role | IAM Role ARN to use | string | - | yes |
| image | The docker image name, e.g nginx | string | - | yes |
| internal_dns_name | The subdomain under which the ELB is exposed internally, defaults to the task name | string | `` | no |
| internal_zone_id | The zone ID to create the record in | string | - | yes |
| log_bucket | The S3 bucket ID to use for the ELB | string | - | yes |
| memory | The number of MiB of memory to reserve for the container | string | `512` | no |
| name | The service name, if empty the service name is defaulted to the image name | string | `` | no |
| port | The container host port | string | - | yes |
| security_groups | Comma separated list of security group IDs that will be passed to the ELB module | string | - | yes |
| ssl_certificate_id | SSL Certificate ID to use | string | - | yes |
| subnet_ids | Comma separated list of subnet IDs that will be passed to the ELB module | string | - | yes |
| version | The docker image version | string | `latest` | no |

## Outputs

| Name | Description |
|------|-------------|
| dns | The DNS name of the ELB |
| elb | The id of the ELB |
| external_fqdn | FQDN built using the zone domain and name (external) |
| internal_fqdn | FQDN built using the zone domain and name (internal) |
| name | The name of the ELB |
| zone_id | The zone id of the ELB |

