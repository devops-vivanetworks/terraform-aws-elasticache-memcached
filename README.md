# terraform-aws-elasticache-memcached


[![Terraform Version](https://img.shields.io/badge/Terraform%20Version->=0.13.0,_<0.14.0-blue.svg)](https://releases.hashicorp.com/terraform/)
[![Release](https://img.shields.io/github/v/release/traveloka/terraform-aws-elasticache-memcached.svg)](https://github.com/traveloka/terraform-aws-elasticache-memcached/releases)
[![Last Commit](https://img.shields.io/github/last-commit/traveloka/terraform-aws-elasticache-memcached.svg)](https://github.com/traveloka/terraform-aws-elasticache-memcached/commits/master)
[![Issues](https://img.shields.io/github/issues/traveloka/terraform-aws-elasticache-memcached.svg)](https://github.com/traveloka/terraform-aws-elasticache-memcached/issues)
[![Pull Requests](https://img.shields.io/github/issues-pr/traveloka/terraform-aws-elasticache-memcached.svg)](https://github.com/traveloka/terraform-aws-elasticache-memcached/pulls)
[![License](https://img.shields.io/github/license/traveloka/terraform-aws-elasticache-memcached.svg)](https://github.com/traveloka/terraform-aws-elasticache-memcached/blob/master/LICENSE)
![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.png?v=103)

## Description

Terraform module to create AWS ElastiCache cluster for Memcached engine.

## Table of Content

- [Description](#Description)
- [Prerequisites](#Prerequisites)
- [Dependencies](#Dependencies)
- [Terraform Versions](#Terraform%20Versions)
- [Terraform Providers](#Terraform%20Providers)
- [Getting Started](#Getting_Started)
- [Inputs](#Inputs)
- [Outputs](#Outputs)
- [Contributing](#Contributing)
- [License](#License)
- [Acknowledgments](#Acknowledgments)

## Prerequisites

In order to provision this module, it is require some information from an existing resources as input parameter, those resources are:

- ElastiCache Parameter Group, input variable that require the information from this resource are, `parameter_group_name` 
- Security Group,  input variable that require the information from this resource are, `security_group_ids` 
- ElastiCache Subnet Group,  input variable that require the information from this resource are, `subnet_group_name`
- (optional) SNS Topic, input variable that require the information from this resource are, `notification_topic_arn`

Please note that some of the above resources may be optional it depends on the parameter you filled in the module input

## Dependencies

Doesn't have any dependencies to any other Terraform module

## Terraform Versions

Updated and tested using Terraform version `0.13.7`

## Getting Started

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 0.13 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | n/a |
| <a name="provider_random"></a> [random](#provider\_random) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_elasticache_cluster.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_cluster) | resource |
| [random_id.cluster_id](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/id) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_additional_tags"></a> [additional\_tags](#input\_additional\_tags) | Common additional tags | `map(string)` | `{}` | no |
| <a name="input_apply_immediately"></a> [apply\_immediately](#input\_apply\_immediately) | Whether to apply cluster changes immediately, or during maintenance window | `string` | n/a | yes |
| <a name="input_az_mode"></a> [az\_mode](#input\_az\_mode) | Whether to provision in single-az or cross-az | `string` | n/a | yes |
| <a name="input_description"></a> [description](#input\_description) | Description of what this memcached used for | `string` | `""` | no |
| <a name="input_engine_version"></a> [engine\_version](#input\_engine\_version) | Version of memcached engine for this cluster | `string` | `""` | no |
| <a name="input_environment"></a> [environment](#input\_environment) | Environment of this memcached resides in | `string` | n/a | yes |
| <a name="input_maintenance_window"></a> [maintenance\_window](#input\_maintenance\_window) | Preferred maintenance window for this memcached | `string` | n/a | yes |
| <a name="input_node_type"></a> [node\_type](#input\_node\_type) | Node type for this memcached | `string` | n/a | yes |
| <a name="input_notification_topic_arn"></a> [notification\_topic\_arn](#input\_notification\_topic\_arn) | ARN of the SNS topic that should receive notification about this memcached cluster | `string` | `""` | no |
| <a name="input_num_cache_nodes"></a> [num\_cache\_nodes](#input\_num\_cache\_nodes) | Number of cache nodes for this memcached | `string` | n/a | yes |
| <a name="input_parameter_group_name"></a> [parameter\_group\_name](#input\_parameter\_group\_name) | Name of the parameter group used by this memcached cluster | `string` | n/a | yes |
| <a name="input_port"></a> [port](#input\_port) | Port used for this memcached | `string` | `"11211"` | no |
| <a name="input_product_domain"></a> [product\_domain](#input\_product\_domain) | Product domain abbreviation this memcached belongs to | `string` | n/a | yes |
| <a name="input_security_group_ids"></a> [security\_group\_ids](#input\_security\_group\_ids) | IDs of security groups to be attached to this memcached cluster | `list(string)` | n/a | yes |
| <a name="input_service_name"></a> [service\_name](#input\_service\_name) | Name of the service this memcached belongs to | `string` | n/a | yes |
| <a name="input_subnet_group_name"></a> [subnet\_group\_name](#input\_subnet\_group\_name) | Name of the subnet group this cluster resides in | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_az_mode"></a> [az\_mode](#output\_az\_mode) | The provisioning mode of this memcached |
| <a name="output_cluster_id"></a> [cluster\_id](#output\_cluster\_id) | The cluster identifier of this memcached |
| <a name="output_configuration_endpoint"></a> [configuration\_endpoint](#output\_configuration\_endpoint) | The configuration endpoint of this memcached |
| <a name="output_endpoint"></a> [endpoint](#output\_endpoint) | The endpoint of this memcached |
| <a name="output_parameter_group_name"></a> [parameter\_group\_name](#output\_parameter\_group\_name) | The parameter group used by this memcached |
| <a name="output_port"></a> [port](#output\_port) | Port used for this memcached |
| <a name="output_security_group_ids"></a> [security\_group\_ids](#output\_security\_group\_ids) | The security groups attached to this memcached |
| <a name="output_subnet_group_name"></a> [subnet\_group\_name](#output\_subnet\_group\_name) | The subnet group name where this memcached resides in |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Contributing

This module accepting or open for any contributions from anyone, please see the [CONTRIBUTING.md](https://github.com/traveloka/terraform-aws-elasticache-memcached/blob/master/CONTRIBUTING.md) for more detail about how to contribute to this module.

## License

This module is under Apache License 2.0 - see the [LICENSE](https://github.com/traveloka/terraform-aws-elasticache-memcached/blob/master/LICENSE) file for details.
