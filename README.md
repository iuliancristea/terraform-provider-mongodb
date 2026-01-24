# Terraform Provider Mongodb
![GitHub go.mod Go version](https://img.shields.io/github/go-mod/go-version/iwoca/terraform-provider-mongodb?logo=go&style=flat-square)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/iwoca/terraform-provider-mongodb?logo=git&style=flat-square)
![GitHub](https://img.shields.io/github/license/iwoca/terraform-provider-mongodb?color=yellow&style=flat-square)
![GitHub Workflow Status](https://img.shields.io/github/workflow/status/iwoca/terraform-provider-mongodb/golangci?logo=github&style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/iwoca/terraform-provider-mongodb?logo=github&style=flat-square)


This repository is a Terraform Mongodb for [Terraform](https://www.terraform.io).

### Requirements

- [Terraform](https://www.terraform.io/downloads.html) >= 0.13
- [Go](https://golang.org/doc/install) >= 1.19

### Installation

1. Clone the repository
1. Enter the repository directory
1. Build the provider using the `make install` command:

````bash
git clone https://github.com/iwoca/terraform-provider-mongodb
cd terraform-provider-mongodb
make install
````

### To test locally

**1: Start MongoDB**

````bash
docker-compose -f docker/docker-compose.yml up -d mongo
````

**2: Run acceptance tests**

````bash
export MONGODB_HOST=localhost
export MONGODB_PORT=27017
export MONGODB_USERNAME=root
export MONGODB_PASSWORD=root
export TF_ACC=1

go test -v ./mongodb/ -run TestAcc
````

**3: Build and use the provider**

````bash
make install
cd examples
terraform init
terraform plan
````
