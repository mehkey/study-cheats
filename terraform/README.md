https://skillcertpro.com/wp-content/uploads/2020/09/Hashicorp-Terraform-Associate-Master-Cheat-Sheet.pdf

https://zerotomastery.io/cheatsheets/terraform-cheat-sheet/




State is a necessary requirement for Terraform to function


Terraform is available for macOS, FreeBSD, OpenBSD, Linux, Solaris, and Windows. 


The user can execute the following command to create a fourth workspace named stage:

$ terraform workspace new stage



Import the existing resources: Harry can use the terraform import command to import the existing resources into Terraform. The terraform import command allows you to import existing infrastructure into Terraform, creating a Terraform state file for the resources.



Modify the Terraform configuration: After importing the resources, Harry can modify the Terraform configuration to reflect the desired state of the resources. This will allow him to manage the resources using Terraform just like any other Terraform-managed resource



Test the changes: Before applying the changes, Harry can use the terraform plan command to preview the changes that will be made to the resources. This will allow him to verify that the changes will not negatively impact the availability of the resources.



Apply the changes: If the changes are correct, Harry can use the terraform apply command to apply the changes to the resources.



terraform {
  required_providers {
    aws = "~> 1.2.0"
  }
}

In a required_version parameter in Terraform, the tilde (~) symbol followed by the greater than symbol (>) specifies a "compatible with" version constraint.

For example, if your Terraform configuration specifies required_version = "~> 1.12.0", Terraform will accept any version of Terraform 1.12 that is greater than or equal to version 1.12.0 and less than 1.13.0. In other words, Terraform will accept any version of Terraform 1.12 that is considered compatible with version 1.12.0.

The terraform force-unlock command can be used to remove the lock on the Terraform state for the current configuration. Another option is to use the "terraform state rm" command followed by the "terraform state push" command to forcibly overwrite the state on the remote backend,

provider, terraform, output, data, and resource.


HashiCorp, the creator of Terraform, recommends using two spaces for indentation when writing Terraform code. This is a convention that helps to improve readability and consistency across Terraform configurations.

Terraform Cloud supports the following VCS providers as of February 2023:

  - GitHub

  - GitHub.com (OAuth)

  - GitHub Enterprise

  - GitLab.com

  - GitLab EE and CE

  - Bitbucket Cloud

  - Bitbucket Server

  - Azure DevOps Server

  - Azure DevOps Services


Notice how the equal (=) signs are aligned, even though the arguments are of different lengths.
ami           = "abc123"
instance_type = "t2.micro"
subnet_id     = "subnet-a6b9cc2d59cc"




Terraform can be expressed using two syntaxes: HashiCorp Configuration Language (HCL), which is the primary syntax for Terraform, and JSON.

