# Serverless Contact Us Form

The template: [cloudformation.yml](cloudformation.yml)

Quickly deploy an endpoint to handle your `contact us` form on your static website.  We don't want to have servers running just to handle our `contact us` form which rarely gets invoked.  Oh, and we also need Captcha because we don't have time in our lives for spam.

<a href="https://console.aws.amazon.com/cloudformation/home?templateURL=https://s3.amazonaws.com/thestackshack/serverless-contact-us-form/cloudformation.yml"><img src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png"/></a>


## What AWS resources does this template use?
* Lambda (API Function)
* API Gateway (HTTP proxy to Lambda)
* S3 (Lambda files)
* SES (Send us the email)
* CodeCommit (GIT repo)
* CloudFormation (Infrastructure as Code)
* IAM (AWS permissions & users)