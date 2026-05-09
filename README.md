# Awesome AWS Control Policies and Guard Rails

Awesome AWS service control policies (SCPs), resource control policies (RCPs), and organizational policies in general (service control, resource control, declarative, ai opt out, backup, tagging, budgets, etc)

Inspired by many other awesome lists!

## terraform modules

### service control policies

- [ScaleSec/terraform_aws_scp](https://github.com/ScaleSec/terraform_aws_scp)
- [trussworks/terraform-aws-ou-scp](https://github.com/trussworks/terraform-aws-ou-scp)
- [cloudposse/terraform-aws-service-control-policies](https://github.com/cloudposse/terraform-aws-service-control-policies)
- [Appsilon/terraform-aws-ou-scp](https://github.com/Appsilon/terraform-aws-ou-scp)
- [timurgaleev/terraform-aws-organization-scp](https://github.com/timurgaleev/terraform-aws-organization-scp)
- [welldone-cloud/aws-scps-for-sandbox-and-training-accounts](https://github.com/welldone-cloud/aws-scps-for-sandbox-and-training-accounts/)
- [latacora/latacora-service-control-policies](https://github.com/latacora/latacora-service-control-policies/tree/master/policy-groups)

### IAM helpers

- [aws_iam_policy_document](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document#minified_json) - Useful terraform data source to build a policy and minify it using attribute `minified_json`. For example `data.aws_iam_policy_document.default.minified_json`.
- [phzietsman/terraform-aws-policy-packer](https://github.com/phzietsman/terraform-aws-policy-packer) - reduce size of IAM policy

## policy stores

- https://www.cloudguardrails.com
- [primeharbor/aws-service-control-policies](https://github.com/primeharbor/aws-service-control-policies)
- https://asecure.cloud/l/scp/
- https://github.com/aws-samples/resource-control-policy-examples
- https://github.com/aws-samples/service-control-policy-examples

## reference architecture

- [aws-samples/aws-scps-with-terraform](https://github.com/aws-samples/aws-scps-with-terraform)

## blogs

- [AWS security blog tag: service control policies](https://aws.amazon.com/blogs/security/tag/service-control-policies/)
- [Dec 1 2024 - Simplify governance with declarative policies](https://aws.amazon.com/blogs/aws/simplify-governance-with-declarative-policies/)
- [Nov 13 2024 - Introducing resource control policies (RCPs), a new type of authorization policy in AWS Organizations](https://aws.amazon.com/blogs/aws/introducing-resource-control-policies-rcps-a-new-authorization-policy/)
- [Oct 9 2023 - What is AWS SCP (Service Control Policy) and How does it Help with Permissions?](https://www.stormit.cloud/blog/aws-scp-service-control-policy)
- [Jul 29 2023 - What are AWS Service Control Policies (SCPs)](https://towardsthecloud.com/aws-scp-service-control-policies)
- [Jun 17 2022 - More about AWS Service Control Policies (SCP)](https://medium.com/gft-engineering/more-about-aws-service-control-policies-scp-1588ff9bc814)
- [Mar 25 2020 - AWS SCP Best Practices](https://summitroute.com/blog/2020/03/25/aws_scp_best_practices/#creating-scps-without-breaking-things)

## Limits

- SCPs do not affect users or roles in the management account. They affect member accounts in the organization. [^1]
- You can directly attach up to 5 SCPs to a root, OU, or account. [^2]
- SCPs have a maximum character limit of `5120` characters. [^2]
- SCPs do not affect service-linked roles. [^1]
- By default, policy visibility and `ListPoliciesForTarget` operations are managed from the management account with Organizations permissions. [^3]
- Access denied errors indicate an explicit SCP deny, but the error does not identify the exact SCP document; use SCP troubleshooting steps to trace the blocking statement. [^4]

## related projects

- https://ramimac.github.io/wiki/scps/
- https://summitroute.com/blog/2020/03/25/aws_scp_best_practices/#aws-wishlist
- [discocrayon/Headroom](https://github.com/discocrayon/Headroom) - Audit mode for AWS SCPs and RCPs - Analyze your AWS Organization, identify policy violations, and auto-generate enforcement policies that won't disrupt operations.

## references

- [List of expensive actions](https://gist.github.com/iann0036/b473bbb3097c5f4c656ed3d07b4d2222)
- [ACM SCPs](https://docs.aws.amazon.com/acm/latest/userguide/acm-conditions.html)
- [AWS Service Control Policy Examples](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_examples.html)
- [Service control policies (SCPs)](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)
- [Terraform and OpenTofu registry search for scp](https://library.tf/modules?query=scp)

[^1]: [Service control policies (SCPs) - AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)
[^2]: [Quotas and service limits for AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_reference_limits.html#min-max-values)
[^3]: [Getting information about your organization's policies - AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_info-operations.html)
[^4]: [Troubleshooting SCPs - AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_troubleshoot.html)
