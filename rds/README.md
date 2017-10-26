
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| allocated_storage | Disk size, in GB | string | `10` | no |
| apply_immediately | If false, apply changes during maintenance window | string | `true` | no |
| backup_retention_period | Backup retention, in days | string | `5` | no |
| backup_window | Time window for backups. | string | `00:00-01:00` | no |
| database | The database name for the RDS instance (if not specified, `var.name` will be used) | string | `` | no |
| engine | Database engine: mysql, postgres, etc. | string | `postgres` | no |
| engine_version | Database version | string | `9.6.1` | no |
| ingress_allow_cidr_blocks | A list of CIDR blocks to allow traffic from | list | `<list>` | no |
| ingress_allow_security_groups | A list of security group IDs to allow traffic from | list | `<list>` | no |
| instance_class | Underlying instance type | string | `db.t2.micro` | no |
| maintenance_window | Time window for maintenance. | string | `Mon:01:00-Mon:02:00` | no |
| monitoring_interval | Seconds between enhanced monitoring metric collection. 0 disables enhanced monitoring. | string | `0` | no |
| monitoring_role_arn | The ARN for the IAM role that permits RDS to send enhanced monitoring metrics to CloudWatch Logs. Required if monitoring_interval > 0. | string | `` | no |
| multi_az | If true, database will be placed in multiple AZs for HA | string | `false` | no |
| name | RDS instance name | string | - | yes |
| password | Postgres user password | string | - | yes |
| port | Port for database to listen on | string | `5432` | no |
| publicly_accessible | If true, the RDS instance will be open to the internet | string | `false` | no |
| storage_type | Storage type: standard, gp2, or io1 | string | `gp2` | no |
| subnet_ids | A list of subnet IDs | list | - | yes |
| username | The username for the RDS instance (if not specified, `var.name` will be used) | string | `` | no |
| vpc_id | The VPC ID to use | string | - | yes |

## Outputs

| Name | Description |
|------|-------------|
| addr |  |
| url |  |

