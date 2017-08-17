# Serverless Contact Us Form

The template: [cloudformation.json](cloudformation.json)

Quickly deploy an endpoint to handle your `contact us` form on your static website.  We don't want to have servers running just to handle our `contact us` form which rarely gets invoked.  Oh, and we also need Captcha because we don't have time in our lives for spam.

** Coming Soon **


## What AWS resources does this template use?
* Lambda (API Function)
* API Gateway (HTTP proxy to Lambda)
* S3 (Lambda files)
* SES (Send us the email)
* CodeCommit (GIT repo)
* CloudFormation (Infrastructure as Code)
* IAM (AWS permissions & users)
