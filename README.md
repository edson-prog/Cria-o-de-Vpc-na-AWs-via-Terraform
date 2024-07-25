# Criar-Vpc-na-AWs-via-Terraform

Crie o arquivo main.tf:

Copiar código
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}

Crie o arquivo resources.tf:


Copiar código
# Criar uma VPC na AWS
resource "aws_vpc" "example" {
  cidr_block = "10.0.0.0/16"
}

# Criar um arquivo local chamado notes.txt
resource "local_file" "notes" {
  filename = "Notes.txt"
  content  = "This is a file created with Terraform"
}

# Criar uma string aleatória
resource "random_string" "random" {
  length  = 10
  special = false
}
Execute os comandos do Terraform:

Copiar código
terraform init
terraform plan
terraform apply
Para destruir os recursos criados:

Copiar código
terraform destroy
