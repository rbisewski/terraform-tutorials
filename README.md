# Terraform tutorials

Various files, derived from content [here](https://learn.hashicorp.com/tutorials/terraform/aws-build?in=terraform/aws-get-started).

Mostly exists to document a quick start to using Terraform.

### Getting started

Begin with initializing a folder with the needed terraform plugins and providers:

```bash
terraform init
```

This will create a .terraform folder with needed libraries, as well as a lockfile.

Afterwards, do a quick format of the terraform scripts via:

```bash
terraform fmt
```

Terraform also offers

```bash
terraform validate
```

If successful, the following will appear:

```
Success! The configuration is valid.
```

To apply the configuration to production, do the following:

```bash
terraform apply
```

If that worked, then take a quick look at live:

```bash
terraform show
```

Assuming all the infra changes were made, then.

### Advanced commands

List the current state of this configuration:

```bash
terraform state list
```

Remove all resources and components associated with this configuration:

```bash
terraform destroy
```

Once you have infrastructure provisioned, you can query the outputs of those like so:

```bash
terraform output
```

### Other useful tips

Variables for your scripts can used, if needed.

Add something like the following to your script, setting a safe default:

```
variable "instance_name" {
  description = "Value of the Name tag for the EC2 instance"
  type        = string
  default     = "TerraformTutorial"
}
```

Afterwards, the variable can be set at the commandline like so:

```bash
terraform apply -var "instance_name=BrandNewInstance"
```

### Terraform Cloud

To login to Terraform Cloud, type the following:

```bash
terraform login
```

Terraform will then request an API token for app.terraform.io using your browser.
