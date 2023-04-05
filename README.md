# Terraform

### Terraform guidance link:

#### [link to Terraform documentation](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
#### [link to Terraform AWS Installation guide](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli) - Linux/Amazon Linux
#### [link to Terraform tutorial I recommended](https://www.youtube.com/watch?v=c1_CFb7kkVA&ab_channel=TheCloudBootcamp-English)

--------------------------------------------------------------------------------------

### CloudShell commands & important notes:

#### * Terraform init -> To initialize Terraform inside CloudShell after following the AWS Installation guide
#### * Terraform plan -> To see what Terraform will plan to do from reading the main.tf
#### * Terraform apply -> To apply the plan
#### * Terraform destroy -> To destroy the bucket inside main.tf. Bucket must be empty before destroying it. CANNOT BE UNDONE!
#### * Terraform reads the contents inside main.tf file that is uploaded into CloudShell

--------------------------------------------------------------------------------------

### Terraform keywords & important notes:

#### * terraform {required providers {aws = {source = "hashicorp/aws" /nversion = "~> 4.16"}} required_version = ">= 1.2.0"} -> typical boilerplate needed to connect to AWS, can be found in Terraform documentation
#### * provider "aws" needed to be in the right region. Hint: Region can be found at the tab of CloudShell
#### * resource "aws_s3_bucket" "name" {} is to create a bucket in your s3. Inside the scope, you need to type bucket = "name-of-bucket-must-be-unique-and-no-caps"
#### * resource "aws_s3_bucket_public_access_block" "name" {} is to give restricted access to your bucket. Inside the scope, you need to type bucket = no-quotation-mark-but-type-aws_s3_bucket.name.id (this refers to the resource bucket name you created above)
#### * Still inside the same scope, use the following:
####    * block_public_acls = true
####    * block_public_policy = true
####    * ignore_public_acls = true
####    * restrict_public_buckets = true
####    It will create restrictions to your bucket based on what you put restrictions on
