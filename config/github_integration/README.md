== Last deployed version

`iambic-core` `0.9.6`

== Github Integration

Github Integration today relies on lambda function deployment and is currently automated via terraform.
Since terraform users tend to vary its deployment method, we keep our example usage to a minimum and
simply keep a copy of tf state inside this directory as an example.

Before invoking the following commands, we assume you are in the `deployment/github_app` directory
of iambic source tree. In addition, your `iambic` source tree and `iambic-templates-examples` source
tree reside at the same directory level.

If I list the directory of my checkout of the source trees:

```
$ ls
iambic iambic-templates-examples
```

To preview changes of the deployment:

```
terraform plan -var "aws_region=us-east-1" -state=../../../iambic-templates-examples/config/github_integration/terraform.tfstate
```

To apply changes of the deployment:

```
terraform apply -var "aws_region=us-east-1" -state=../../../iambic-templates-examples/config/github_integration/terraform.tfstate
```
