<!-- markdownlint-disable -->

# Terraform Template
Provides a template to start with when you're ready to create a Terraform project.


## Usage

```hcl
module "subnets" {
  source = "cloudposse/dynamic-subnets/aws"
  # Cloud Posse recommends pinning every module to a specific version
  # version = "x.x.x"
  namespace           = "eg"
  stage               = "prod"
  name                = "app"
  vpc_id              = "vpc-XXXXXXXX"
  igw_id              = "igw-XXXXXXXX"
  cidr_block          = "10.0.0.0/16"
  availability_zones  = ["us-east-1a", "us-east-1b"]
}
```

## Requirements

| Name                                                                     | Version   |
| ------------------------------------------------------------------------ | --------- |
| <a name="requirement_terraform"></a> [terraform](#requirement_terraform) | >= 0.13.0 |
| <a name="requirement_aws"></a> [aws](#requirement_aws)                   | >= 3.62.0 |

## Providers

| Name                                             | Version   |
| ------------------------------------------------ | --------- |
| <a name="provider_aws"></a> [aws](#provider_aws) | >= 3.62.0 |

## Modules

| Name                                                                                      | Source                | Version |
| ----------------------------------------------------------------------------------------- | --------------------- | ------- |
| <a name="module_nat_instance_label"></a> [nat_instance_label](#module_nat_instance_label) | cloudposse/label/null | 0.25.0  |

## Resources

| Name                                                                                               | Type     |
| -------------------------------------------------------------------------------------------------- | -------- |
| [aws_eip.default](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/eip) | resource |

## Inputs

| Name                                                                                    | Description                                                                                                                                                                                                                                                                        | Type          | Default | Required |
| --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ------- | :------: |
| <a name="input_additional_tag_map"></a> [additional_tag_map](#input_additional_tag_map) | Additional key-value pairs to add to each map in `tags_as_list_of_maps`. Not added to `tags` or `id`.<br>This is for some rare cases where resources want additional configuration of tags<br>and therefore take a list of maps with tag key, value, and additional configuration. | `map(string)` | `{}`    |    no    |


## Outputs

| Name                                                                                      | Description                                           |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| <a name="output_availability_zones"></a> [availability_zones](#output_availability_zones) | List of Availability Zones where subnets were created |
