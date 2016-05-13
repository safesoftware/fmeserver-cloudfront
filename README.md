# fmeserver-cloudfront (BETA)

CloudFormation template to deploy AWS CloudFront on top of FME Server.

**NOTE**: This template is currently in BETA and we are still working on it. You should be aware that using FME Server
and CloudFront could cause unexpected behaviour on FME Server side.

## Requirements
* AWS account
* Running FME Server with a public hostname

## Setup
1. Login to the AWS console and open the CloudFormation page
2. Create a new stack
3. Select _Upload a template to Amazon S3_ and choose `fmeserver-cloudfront.template`
4. Enter all parameters
5. Wait until stack status is **CREATE_COMPLETE**
6. Optional: If an alternate domain name was setup, create a CNAME entry in your DNS management console and point it to
the CloudFront URL (see CloudFormation Outputs)

## Data Download caching setup
1. Set CloudFormation _EnableDataDownloadCaching_ parameter to true
2. Login to your FME Server
3. Change the data download service URL to your CloudFront URL. This can either be the alternate domain name or
the CloudFront URL.