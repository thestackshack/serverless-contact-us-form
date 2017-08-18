# Serverless Contact Us Form

The template: [cloudformation.yml](cloudformation.yml)

Quickly deploy an endpoint to handle your `contact us` form on your static website.  We don't want to have servers running just to handle our `contact us` form which rarely gets invoked.  Oh, and we also need Captcha because we don't have time in our lives for spam.

<a href="https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=&templateURL=https://s3.amazonaws.com/thestackshack/serverless-contact-us-form/cloudformation.yml"><img src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png"/></a>

## What AWS resources does this template use?
* Lambda (API Function)
* API Gateway (HTTP proxy to Lambda)
* S3 (Lambda files)
* SES (Send us the email)
* CodeCommit (GIT repo)
* CloudFormation (Infrastructure as Code)
* IAM (AWS permissions & users)

## HTML Form
```
<form action="https://3lvxa9akr5.execute-api.us-east-1.amazonaws.com/prod/api" method="POST" id="contact-us-form">
    <div class="form-group">
        <label for="nameInputEmail1">Name</label>
        <input type="text" class="form-control" id="nameInputEmail1" name="name" placeholder="Full name">
    </div>
    <div class="form-group">
        <label for="exampleInputEmail1">Email address</label>
        <input type="email" class="form-control" id="exampleInputEmail1" name="email"
               placeholder="Enter email">
    </div>
    <div class="form-group">
        <label for="phoneInputEmail1">Phone number</label>
        <input type="text" class="form-control" id="phoneInputEmail1" name="phone"
               placeholder="Enter phone">
    </div>
    <div class="form-group">
        <label for="messageInputEmail1">Message</label>
        <textarea type="textarea" class="form-control" id="messageInputEmail1" name="message"
                  placeholder="Enter message"></textarea>
    </div>
    <p class="thanks">Thanks!  We'll contact you soon.</p>
    <button type="submit" class="btn btn-primary g-recaptcha"
      data-sitekey="6LdrWS0UAAAAAPAokGKpRhrObJkaaCX0EMsEiofN"
      data-callback="onContctUsSubmit" data-badge="inline" >Submit</button>
</form>
```
JQuery example...
```
$.post($("#contact-us-form").attr('action'), JSON.stringify({
    name: $("#contact-us-form input[name='name']").val(),
    email: $("#contact-us-form input[name='email']").val(),
    phone: $("#contact-us-form input[name='phone']").val(),
    message: $("#contact-us-form textarea[name='message']").val(),
    'g-recaptcha-response': $("#contact-us-form textarea[name='g-recaptcha-response']").val()
}), function (data) {
    $(".thanks").show();
    $("#contact-us-form button").hide();
}, 'json');
```