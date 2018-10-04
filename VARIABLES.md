# Variables

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| apiary_customer_accounts | AWS account IDs for clients of this Metastore. | list | - | yes |
| apiary_database_name | Database name to create in RDS for Apiary. | string | `apiary` | no |
| apiary_domain_name | Apiary domain name for Route 53. | string | `` | no |
| apiary_log_bucket | Bucket for Apiary logs. | string | - | yes |
| apiary_log_prefix | Prefix for Apiary logs. | string | `` | no |
| apiary_managed_schemas | Schema names from which S3 bucket names will be derived, corresponding S3 bucket will be named as apiary_instance-aws_account-aws_region-schema_name. | list | `<list>` | no |
| apiary_producer_iamroles | AWS IAM roles allowed write access to managed Apiary S3 buckets. | map | `<map>` | no |
| apiary_rds_additional_sg | Comma-separated string containing additional security groups to attach to RDS. | list | `<list>` | no |
| apiary_tags | Common tags that get put on all resources. | map | - | yes |
| aws_region | AWS region. | string | - | yes |
| db_backup_retention | The number of days to retain backups for the RDS Metastore DB. | string | - | yes |
| db_backup_window | Preferred backup window for the RDS Metastore DB in UTC. | string | `02:00-03:00` | no |
| db_instance_class | Instance type for the RDS Metastore DB. | string | - | yes |
| db_instance_count | Desired count of database cluster instances. | string | `2` | no |
| db_maintenance_window | Preferred maintenance window for the RDS Metastore DB in UTC. | string | `wed:03:00-wed:04:00` | no |
| disable_database_management | Disable creating and dropping databases from Hive CLI. | string | `` | no |
| ecs_domain_name | Domain name to use for hosted zone created by ECS service discovery. | string | `lcl` | no |
| elb_timeout | Idle timeout for Apiary ELB. | string | `1800` | no |
| enable_data_events | Enable managed buckets S3 event notifications. | string | `` | no |
| enable_gluesync | Enable metadata sync from Hive to the Glue catalog. | string | `` | no |
| enable_metadata_events | Enable Hive Metastore SNS listener. | string | `` | no |
| external_data_buckets | Buckets that are not managed by Apiary but added to Hive Metastore IAM role access. | list | `<list>` | no |
| external_database_host | External Metastore database host to support legacy installations, MySQL database won't be created by Apiary when this option is specified. | string | `` | no |
| hms_docker_image | Docker image ID for the Hive Metastore. | string | - | yes |
| hms_docker_version | Version of the Docker image for the Hive Metastore. | string | - | yes |
| hms_log_level | Log level for the Hive Metastore. | string | `INFO` | no |
| hms_nofile_ulimit | Ulimit for the Hive Metastore container. | string | `32768` | no |
| hms_readonly_instance_count | Desired instance count of the read only Hive Metastore service. | string | `2` | no |
| hms_readwrite_instance_count | Desired instance count of the read/write Hive Metastore service. | string | `2` | no |
| hms_ro_cpu | CPU for the read only Hive Metastore ECS task. Valid values can be 256, 512, 1024, 2048 and 4096. Reference: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-cpu-memory-error.html | string | `512` | no |
| hms_ro_heapsize | Heapsize for the read only Hive Metastore. Valid values: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-cpu-memory-error.html | string | - | yes |
| hms_rw_cpu | CPU for the read/write Hive Metastore ECS task. Valid values can be 256, 512, 1024, 2048 and 4096. Reference: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-cpu-memory-error.html | string | `512` | no |
| hms_rw_heapsize | Heapsize for the read/write Hive Metastore. Valid values: https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-cpu-memory-error.html | string | - | yes |
| ingress_cidr | Generally allowed ingress CIDR list. | list | - | yes |
| instance_name | Apiary instance name to identify resources in multi-instance deployments. | string | `` | no |
| ldap_base | Active directory LDAP base DN to search users and groups. | string | `` | no |
| ldap_url | Active directory LDAP URL to configure Hadoop LDAP group mapping. | string | `` | no |
| private_subnets | Private subnets. | list | - | yes |
| ranger_audit_db_url | Ranger DB audit provider configuration. | string | `` | no |
| ranger_audit_solr_url | Ranger Solr audit provider configuration. | string | `` | no |
| ranger_policy_mgr_url | Ranger admin URL to synchronize policies. | string | `` | no |
| vault_addr | Address of Vault server for secrets. | string | - | yes |
| vault_internal_addr | Internal address of Vault server for secrets. | string | - | yes |
| vault_login_path | Remote path in Vault where the auth method is enabled. More details: https://www.vaultproject.io/docs/commands/login.html | string | `` | no |
| vault_path | Path to Apiary secrets in Vault. | string | `` | no |
| vpc_id | VPC ID. | string | - | yes |