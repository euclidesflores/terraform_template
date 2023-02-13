# A Terraform template

This is a Terraform template inspired by a document published by Google on [Best  practices for using Terraform](https://view.hashicorp.com/ODQ1LVpMRi0xOTEAAAGJY_TfoRHc-D8qY7FGbrLfviHK8DgFD7RraldwA5rWcLZ-Epmk9ffVwXH-TqyUsvT9nzO9p8JnSA0ZZdE=)


The initial structure of a root module is quite simple and is cloud agnostic:

``` bash
.
├── .github
│   └── CODEOWNERS
├── .gitignore
├── .terraform.lock.hcl 
├── README.md
├── data.tf
├── files
├── helpers
├── main.tf
├── outputs.tf
├── scripts
├── terraform.tfvars
├── variables.tf
└── versions.tf


```

## .github/CODEOWNERS

Specifies who is responsible for the module



## .gitignore
Use the .gitignore file to prevent committing files containing sensitive information, such as development state and tfvars files.



## .terraform.lock.hcl
This is the dependency lock file and Terraform automatically creates and updates this file. This file should be ckecked into source control.



## README.md
A README.me file includes basic documentation of the module.



## files/
Place static files that Terraform references but doesn't execute (such as startup scripts loaded onto AWS EC2 and Google Compute engine instances).



## helpers/
Put helper scripts that aren't called by Terraform in this directory. Document helper scripts in the README.md file.



## scripts/
Avoid using custom scripts, if you need create custom scripts that are going to be called or referenced by Terraform place them in the scripts/ directory.



## data.tf
Use a dedicated data.tf file if the number of data sources becomes large.



## main.tf
Every module should start with a main.tf file. Place your resources in this file.



## outputs.tf
Organize all outputs in this file.



## terraforms.tfvars
Use this file to store variables. Don't check this file into the source control.



## variable.tf
Declare all variables in this file.



## versions.tf
This is the versions file. Use this file to declare each provider and its version.


## Naming convention
For all configuration objects use underscores to delimit multiple words:

``` bash
# Azure Virtual Machine
resource "azurerm_virtual_machine" "web_server" {}

# AWS EC2
resource "aws_instance" "proxy_server" {}

``` 

## Built-in formatting
Use ``` terraform fmt ``` 





