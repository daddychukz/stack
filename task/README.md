The task module creates an ECS task definition.

Usage:

    module "nginx" {
      source = "github.com/segmentio/stack/task"
      name   = "nginx"
      image  = "nginx"
    }



## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| command | The raw json of the task command | string | `[]` | no |
| cpu | The number of cpu units to reserve for the container | string | `512` | no |
| entry_point | The docker container entry point | string | `[]` | no |
| env_vars | The raw json of the task env vars | string | `[]` | no |
| image | The docker image name, e.g nginx | string | - | yes |
| image_version | The docker image version | string | `latest` | no |
| log_driver | The log driver to use use for the container | string | `journald` | no |
| memory | The number of MiB of memory to reserve for the container | string | `512` | no |
| name | The worker name, if empty the service name is defaulted to the image name | string | - | yes |
| ports | The docker container ports | string | `[]` | no |
| role | The IAM Role to assign to the Container | string | `` | no |

## Outputs

| Name | Description |
|------|-------------|
| arn | The created task definition ARN |
| name | The created task definition name |
| revision | The revision number of the task definition |

