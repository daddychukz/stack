The service module creates an ecs service, task definition
elb and a route53 record under the local service zone (see the dns module).

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
| dns_name | The DNS name to use, e.g nginx | string | - | yes |
| env_vars | The raw json of the task env vars | string | `[]` | no |
| environment | Environment tag, e.g prod | string | - | yes |
| healthcheck | Path to a healthcheck endpoint | string | `/` | no |
| iam_role | IAM Role ARN to use | string | - | yes |
| image | The docker image name, e.g nginx | string | - | yes |
| log_bucket | The S3 bucket ID to use for the ELB | string | - | yes |
| memory | The number of MiB of memory to reserve for the container | string | `512` | no |
| name | The service name, if empty the service name is defaulted to the image name | string | `` | no |
| port | The container host port | string | - | yes |
| protocol | The ELB protocol, HTTP or TCP | string | `HTTP` | no |
| security_groups | Comma separated list of security group IDs that will be passed to the ELB module | string | - | yes |
| subnet_ids | Comma separated list of subnet IDs that will be passed to the ELB module | string | - | yes |
| version | The docker image version | string | `latest` | no |
| zone_id | The zone ID to create the record in | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| dns | The DNS name of the ELB |
| elb | The id of the ELB |
| fqdn | FQDN built using the zone domain and name |
| name | The name of the ELB |
| zone_id | The zone id of the ELB |

