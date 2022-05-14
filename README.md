<!-- BEGIN_TF_DOCS -->
# AWS Bastion

AWS Bastion with multiple SSH Key support.

## Usage

``` sh
ssh-keygen -t rsa
```

``` sh
module "bastion" {
  source = "github.com/opszero/terraform-aws-bastion"

  ssh_keys = [ "ssh-rsa ..." ]
  ec2_connect_installed = true
}
```
## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | 4.13.0 |
| <a name="provider_template"></a> [template](#provider\_template) | 2.2.0 |
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_bastion_name"></a> [bastion\_name](#input\_bastion\_name) | n/a | `any` | n/a | yes |
| <a name="input_ec2_connect_installed"></a> [ec2\_connect\_installed](#input\_ec2\_connect\_installed) | n/a | `bool` | `true` | no |
| <a name="input_ingress_cidrs"></a> [ingress\_cidrs](#input\_ingress\_cidrs) | n/a | `any` | n/a | yes |
| <a name="input_instance_type"></a> [instance\_type](#input\_instance\_type) | n/a | `string` | `"t3.micro"` | no |
| <a name="input_security_group_ids"></a> [security\_group\_ids](#input\_security\_group\_ids) | n/a | `list` | `[]` | no |
| <a name="input_ssh_keys"></a> [ssh\_key](#input\_ssh\_key) | SSH public key to add to the image | `List` | `[]` | no |
| <a name="input_subnet_id"></a> [subnet\_id](#input\_subnet\_id) | n/a | `any` | n/a | yes |
| <a name="input_tags"></a> [tags](#input\_tags) | n/a | `map` | `{}` | no |
| <a name="input_ubuntu_version"></a> [ubuntu\_version](#input\_ubuntu\_version) | n/a | `string` | `"20.04"` | no |
| <a name="input_user_data"></a> [user\_data](#input\_user\_data) | n/a | `string` | `""` | no |
| <a name="input_userdata"></a> [userdata](#input\_userdata) | n/a | `string` | `""` | no |
| <a name="input_volume_size"></a> [volume\_size](#input\_volume\_size) | n/a | `number` | `20` | no |
| <a name="input_vpc_id"></a> [vpc\_id](#input\_vpc\_id) | n/a | `any` | n/a | yes |
## Resources

| Name | Type |
|------|------|
| [aws_cloudwatch_metric_alarm.aws_bastion_cpu_threshold](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_metric_alarm) | resource |
| [aws_eip.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/eip) | resource |
| [aws_instance.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance) | resource |
| [aws_security_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group) | resource |
| [aws_security_group_rule.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule) | resource |
| [aws_ssm_parameter.ubuntu](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/ssm_parameter) | data source |
| [template_cloudinit_config.config](https://registry.terraform.io/providers/hashicorp/template/2.2.0/docs/data-sources/cloudinit_config) | data source |
| [template_file.ec2_connect](https://registry.terraform.io/providers/hashicorp/template/2.2.0/docs/data-sources/file) | data source |
| [template_file.keys](https://registry.terraform.io/providers/hashicorp/template/2.2.0/docs/data-sources/file) | data source |
## Outputs

| Name | Description |
|------|-------------|
| <a name="output_public_ip"></a> [public\_ip](#output\_public\_ip) | n/a |
<!-- END_TF_DOCS -->
