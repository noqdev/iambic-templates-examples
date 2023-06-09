# iambic-templates-examples

This is an example IAMbic templates repository. When you use [IAMbic](https://github.com/noqdev/iambic) to track your multi-cloud IAM assets, you can store the assets into a repository like this one. This repository is public for documentation purposes. You will not have to make your IAMbic templates repository public, espeically if you are worry about PII (personal identitifable information due to email or username). 

# Directory Layout

IAMbic has a convention to import assets into `resources/<plugin-name>/<resource-type>` convention. However, you can re-arrange the directory layout to fit your needs. IAMbic will transverse the whole templates repository when it accounts for cloud assets. 

# Plugin Demonstration

## Amazon Web Services

* [IAM Role](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/aws/iam/role/all_accounts/iambicspokerole.yaml)
* [IAM Managed Policy](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/aws/iam/managed_policy/iambic_test_spoke_account_1/update-role-description.yaml)
* [IAM User](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/aws/iam/user/iambic_test_org_account/admin.yaml)
* [IAM Group](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/aws/iam/group/all_accounts/engineering.yaml)
* [Identity Center Permission Set](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/aws/identity_center/permission_set/design.yaml)

## Azure Active Directory

* [Group](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/azure_ad/group/iambic/engineering.yaml)
* [User](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/azure_ad/user/iambic/alice%40iambicorg.onmicrosoft.com.yaml)

## Google Workspace

* [Group](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/google_workspace/group/iambic.org/testgroup.yaml)

## Okta

* [Application](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/okta/app/development/test_application.yaml)
* [Group](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/okta/group/development/product.yaml)
* [User](https://github.com/noqdev/iambic-templates-examples/blob/main/resources/okta/user/development/curtis%40noq.dev.yaml)

# Automation

## Periodic Import

This Github [workflow](https://github.com/noqdev/iambic-templates-examples/blob/main/.github/workflows/iambic-import.yml) runs the `iambic import` flow via IAMbic bundled Github integration. This make sure any out-of-band resources are imported back into IAMBIC templates git repository.

# GitHub Pull Request Workflow

We want to delegate the ask of making PR to obtain IAM request to developer, so IAMbic comes with a Github Pull Request workflow. Checkout this [PR](https://github.com/noqdev/iambic-templates-examples/pull/3) Someone made the request to modify the role definition, and IAMbic Github Integration automatically runs `iambic plan` and comment the effect of this change within the PR.
