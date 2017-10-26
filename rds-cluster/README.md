
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| availability_zones | A list of availability zones | list | - | yes |
| backup_retention_period | The backup retention period | string | `5` | no |
| database_name | The database name | string | - | yes |
| dns_name | Route53 record name for the RDS database, defaults to the database name if not set | string | `` | no |
| environment | The environment tag, e.g prod | string | - | yes |
| instance_count | How many instances will be provisioned in the RDS cluster | string | `1` | no |
| instance_type | The type of instances that the RDS cluster will be running on | string | `db.r3.large` | no |
| master_password | The master user password | string | - | yes |
| master_username | The master user username | string | - | yes |
| name | The name will be used to prefix and tag the resources, e.g mydb | string | - | yes |
| port | The port at which the database listens for incoming connections | string | `3306` | no |
| preferred_backup_window | The time window on which backups will be made (HH:mm-HH:mm) | string | `07:00-09:00` | no |
| publicly_accessible | When set to true the RDS cluster can be reached from outside the VPC | string | `false` | no |
| security_groups | A list of security group IDs | list | - | yes |
| skip_final_snapshot | When set to false deletion will be delayed to take a snapshot from which the database can be recovered | string | `true` | no |
| subnet_ids | A list of subnet IDs | list | - | yes |
| vpc_id | The VPC ID to use | string | - | yes |
| zone_id | The Route53 Zone ID where the DNS record will be created | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| endpoint |  |
| fqdn |  |
| id | The cluster identifier. |
| port |  |

