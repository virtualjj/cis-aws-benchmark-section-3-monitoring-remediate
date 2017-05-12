# What is the purpose of this project?

The purpose of this project is to automate fixes for Section 3 Monitoring of the [CIS (Center for Internet Security) AWS Foundations Benchmark](https://d0.awsstatic.com/whitepapers/compliance/AWS_CIS_Foundations_Benchmark.pdf).

This AWS CloudFormation template let's you register an email that will receive alarms for the following controls:

- 3.1 Ensure a log metric filter and alarm exist for unauthorized API calls 
- 3.2 Ensure a log metric filter and alarm exist for Management Console sign-in without MFA (Scored)
- 3.3 Ensure a log metric filter and alarm exist for usage of "root" account (Scored)
- 3.4 Ensure a log metric filter and alarm exist for IAM policy changes (Scored)
- 3.5 Ensure a log metric filter and alarm exist for CloudTrail configuration changes (Scored)
- 3.6 Ensure a log metric filter and alarm exist for AWS Management Console authentication failures (Scored)
- 3.7 Ensure a log metric filter and alarm exist for disabling or scheduled deletion of customer created CMKs (Scored)
- 3.8 Ensure a log metric filter and alarm exist for S3 bucket policy changes (Scored)
- 3.9 Ensure a log metric filter and alarm exist for AWS Config configuration changes (Scored)
- 3.10 Ensure a log metric filter and alarm exist for security group changes (Scored)
- 3.11 Ensure a log metric filter and alarm exist for changes to Network Access Control Lists (NACL) (Scored)
- 3.12 Ensure a log metric filter and alarm exist for changes to network gateways (Scored)
- 3.13 Ensure a log metric filter and alarm exist for route table changes (Scored)
- 3.14 Ensure a log metric filter and alarm exist for VPC changes (Scored)

# Why would I want to use this AWS CloudFormation template?

In addition to quickly remediating Section 3 Monitoring of the CIS AWS Foundations Benchmark, this AWS CloudFormation template let's you customize your own names for the following:

- Alarm and CloudTrail Topic Name
- Alarm and CloudTrail Display Name
- CloudTrail S3 Bucket
- CloudTrail Log Group
- CloudTrail Role Name
- Metric Name Space
- Metric Filter Names

The advantage of custom naming is that you can more easily align resource names with your organization's naming conventions.

This template is also non-destructive so you should be able to deploy and remove without interfering with existing resources. However, always do your own tests just in case!

# Which AWS regions does this template support?

The main dependency is on SNS. Available SNS regions can be reference at the FAQ [Q: Is Amazon SNS available in all regions where AWS services are available?](https://aws.amazon.com/sns/faqs/) which currently lists:

- US East (Northern Virginia)
- US West (Oregon)
- US West (Northern California)
- EU (Ireland)
- EU (Frankfurt)
- Asia Pacific (Singapore)
- Asia Pacific (Tokyo)
- Asia Pacific (Sydney)
- South America (Sao Paulo)

# How do I deploy this template?

1. Login to your AWS account and select the region that you want to deploy template.

![alt text](https://github.com/virtualjj/cis-aws-benchmark-section-3-monitoring-remediate/blob/master/images/readme/cis-bench-sec-3-choose-region.jpg "Example logging into AWS console and selecting a region.")

2. Click the **Launch Stack** button below to go directly to the CloudFormation service in the selected region of your AWS account.

[![Launch CloudFormation Stack](https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png
)](https://console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/new?stackName=cis-benchmark-3-monitoring-remediate&templateURL=https://s3-us-west-2.amazonaws.com/github.cis-aws-benchmark-section-3-monitoring-remediate/cis-aws-benchmark-section-3-monitoring-remediate.yml)
