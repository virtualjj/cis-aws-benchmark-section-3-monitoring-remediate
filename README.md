# AUTOMATE CIS AWS FOUNDATIONS BENCHMARK CONTROLS WITH CLOUDFORMATION

## STRANGER, DANGER!!!
I'm still actively working on this project so it is not ready for production use! I will be adding very detailed information and documentation so stay tuned!

Here is what is working:

* Email for SNS Topic.
* Setup CloudTrail for all regions using custom LogGroup name.
* Metric filters and alarms for the following CIS controls:
	* 3.14
	* 3.13
	* 3.12
	* 3.11
	* 3.10
	* 3.9
	* 3.8
	* 3.7

Note that for resource **TrailBucket** the DeletionPolicy is set to **Delete** since I'm still testing. Also, when you delete the stack, make sure to empty out the S3 bucket that this template creates **FIRST** since even with a DeletionPolicy of Delete, CloudFormation will fail since the bucket is not empty.

    "DeletionPolicy":"Delete",
    
Here is what I will be adding this week:

* Custom KMS key for CloudTrail encrypting.
* The rest of the metric filters and alarms.

## PURPOSE
The purpose of this project is to automate as many of the [CIS AWS Foundations Benchmark](https://d0.awsstatic.com/whitepapers/compliance/AWS_CIS_Foundations_Benchmark.pdf) controls as possible using AWS CloudFormation.  

## BACKGROUND
I got the idea to start this project after using the really awesome tool [Prowler: AWS CIS Benchmark Tool](https://github.com/Alfresco/aws-cis-security-benchmark) which automates all of the checks for the CIS AWS Foundation Benchmark. As I started the process of piece mealing my own templates, I found a cloudonaut.io [CloudTrail across all regions](https://cloudonaut.io/security-templates-for-aws-cloudformation/) template that helped get me started on this journey.
