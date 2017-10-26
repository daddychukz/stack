The worker module creates an ECS service that has no ELB attached.

Usage:

    module "my_worker" {
      source       = "github.com/segmentio/stack"
      environment  = "prod"
      name         = "worker"
      image        = "worker"
      cluster      = "default"
    }



## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| cluster | The cluster name or ARN | string | - | yes |
| command | The raw json of the task command | string | `[]` | no |
| cpu | The number of cpu units to reserve for the container | string | `512` | no |
| deployment_maximum_percent | upper limit (% of desired_count) of # of running tasks during a deployment | string | `200` | no |
| deployment_minimum_healthy_percent | lower limit (% of desired_count) of # of running tasks during a deployment | string | `100` | no |
| desired_count | The desired count | string | `1` | no |
| env_vars | The raw json of the task env vars | string | `[]` | no |
| environment | Environment tag, e.g prod | string | - | yes |
| image | The docker image name, e.g nginx | string | - | yes |
| memory | The number of MiB of memory to reserve for the container | string | `512` | no |
| name | The worker name, if empty the service name is defaulted to the image name | string | `` | no |
| version | The docker image version | string | `latest` | no |

