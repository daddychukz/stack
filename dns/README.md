The dns module creates a local route53 zone that serves
as a service discovery utility. For example a service
resource with the name `auth` and a dns module
with the name `stack.local`, the service address will be `auth.stack.local`.

Usage:

   module "dns" {
     source = "github.com/segment/stack"
     name   = "stack.local"
   }



## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| name | Zone name, e.g stack.local | string | - | yes |
| vpc_id | The VPC ID (omit to create a public zone) | string | `` | no |

## Outputs

| Name | Description |
|------|-------------|
| name | The domain name. |
| name_servers | A comma separated list of the zone name servers. |
| zone_id | The zone ID. |

