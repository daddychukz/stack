The module creates an IAM user.

Usage:

   module "my_user" {
     name = "user"
     policy = <<EOF
     {}
   EOF
   }



## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| name | The user name, e.g my-user | string | - | yes |
| policy | The raw json policy | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| access_key | The aws access key id. |
| arn | The user ARN |
| secret_key | The aws secret access key. |

