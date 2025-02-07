# awesome-service-control-policies

Awesome AWS service control policies (SCPs), resource control policies (RCPs), and organizational policies in general (service control, resource control, declarative, ai opt out, backup, tagging)

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

- [aws_iam_policy_document](https://registry.terraform.io/providers/hashicorp/aws/5.63.1/docs/data-sources/iam_policy_document#minified_json) - Useful terraform data source to build a policy and minify it using attribute `minified_json`
- [phzietsman/terraform-aws-policy-packer](https://github.com/phzietsman/terraform-aws-policy-packer) - reduce size of IAM policy

## policy stores

- [primeharbor/aws-service-control-policies](https://github.com/primeharbor/aws-service-control-policies)
- https://asecure.cloud/l/scp/
- https://github.com/aws-samples/resource-control-policy-examples
- https://github.com/aws-samples/service-control-policy-examples

## reference architecture

- [aws-samples/aws-scps-with-terraform](https://github.com/aws-samples/aws-scps-with-terraform)

## blogs

- [AWS security blog tag: service control policies](https://aws.amazon.com/blogs/security/tag/service-control-policies/)
- [Oct 9 2023 - What is AWS SCP (Service Control Policy) and How does it Help with Permissions?](https://www.stormit.cloud/blog/aws-scp-service-control-policy)
- [Jul 29 2023 - What are AWS Service Control Policies (SCPs)](https://towardsthecloud.com/aws-scp-service-control-policies)
- [Jun 17 2022 - More about AWS Service Control Policies (SCP)](https://medium.com/gft-engineering/more-about-aws-service-control-policies-scp-1588ff9bc814)
- [Mar 25 2020 - AWS SCP Best Practices](https://summitroute.com/blog/2020/03/25/aws_scp_best_practices/#creating-scps-without-breaking-things)

## Limits

- Policies do not affect users or roles in the management/root account. They affect only the member accounts in your organization.
- Policies have a maximum of 5 policies that can be attached to root/ou/account. [^1]
- Policies have a maximum character limit of `5120` characters. [^1]
- Policies do not affect service linked roles.
- member accounts cannot query which policies are applied to them [^2]
- Denied actions show that it was blocked by a service control policy but will not show which one in the error or in cloudtrail. [^2]
- No audit or evaluation mode for SCPs and other policies. [^2]

## related projects

- https://ramimac.github.io/wiki/scps/
- https://summitroute.com/blog/2020/03/25/aws_scp_best_practices/#aws-wishlist

## references

- [List of expensive actions](https://gist.github.com/iann0036/b473bbb3097c5f4c656ed3d07b4d2222)
- [ACM SCPs](https://docs.aws.amazon.com/acm/latest/userguide/acm-conditions.html)
- [AWS Service Control Policy Examples](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_examples.html)
- [Service control policies (SCPs)](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)
- [Terraform and OpenTofu registry search for scp](https://library.tf/modules?query=scp)

[^1]: [Quotas and service limits for AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_reference_limits.html#min-max-values)
[^2]: [SummitRoute's SCP Best Practices AWS Wishlist](https://summitroute.com/blog/2020/03/25/aws_scp_best_practices/#aws-wishlist)
