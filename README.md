# terraform-aws-label
The Terraform Amazon Web Services (AWS) Label module generates consistent label names and tags for Terraform resources.

## Module input variables

```region``` - AWS Region used to host Terraform resources.

```namespace``` - Namespace, generally your organization or department name (for example, ```AWS```).

```env``` - Environment name (for example, ```sit```, ```uat```, or ```prod```).

```account``` - Account, which could be an AWS account name or number.

```name``` - Stack name.

```delimiter``` - which could be used between name, namespace and env to form the resource name

```attributes``` - which could be used for additional attributes

```tags``` - which could be used for additional tags

## Usage

module "label" {

    source = "git@github.com:aws-quickstart/terraform-aws-label.git"

    region = "us-east-1"

    namespace = "it-digial"

    env = "sit"

    account = "aws-account-name"

    name = "stackname"

    delimiter = "-"

    tags = "${map("key","name","value","${var.name}","propogate_at_launch","true","terraform","true")}"

}


## Outputs

```tags``` - list of tags

```id``` - id of the tag delimited with "-"

```name``` - stack name

```namespace``` - namespace

```account``` - AWS Account

```env``` - environment name

```attributes``` - list of additional attributes

