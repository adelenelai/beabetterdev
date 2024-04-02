# Setting up AWS Account
https://www.youtube.com/watch?v=SGMl2hOl9zM

* sign up for [Amazon Free Tier](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all&awsf.Free%20Tier%20Categories=*all), including:
    * 750 hours on EC2
    * 5GB on S3
    * 50GB ECR for Docker images
    * 2 months Sagemaker etc.

* some are Always Free

* make sure to manage resources - check what is in Free Tier or face charges

* create user account (IAM), use root account only for user management or resource allocation; set up 2FA
  * Not providing Console Access to user account, otherwise best practice is to enable IAM Identity Center and create user otherwise

* set up AWS CLI (for user account, not root)
  * get access and secret access keys
  * install CLI from pkg ([MacOS](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html))
  * various authentication methods; created IAM Identity Center (successor to AWS SSO) workforce users short-term credentials
    * Enable IAM Identity Center > Enable with AWS Organizations (allows for multi-account permissions management); accidentally configured in N. Virginia region - stick to that for now but confusion between creating a new AWS account via AWS Organizations, and the IAM account I already created...
    * seems with IAM Identity Center succeeding AWS SSO, a lot of instructions have not been updated, not easy to follow
    * creating AWS Account under AWS Organizations...? Not sure I want to do this, and this all seems more complicated than necessary
  * trying different authentication type: IAM user short-term credentials? But this expires every 12 hours. Again, not what I want.
  * simply followed verbal instructions in Youtube video and typed ```aws configure```, entered access and secret access keys from IAM user, region, and preferred output format.
  * Overall seemed to have taken a detour into more sophisticated CLI settings including managing for multiple accounts and users, might revisit later!

  * [avoiding surprise bills]https://aws.amazon.com/getting-started/hands-on/control-your-costs-free-tier-budgets/ for Free Tier
    * activated AWS Free Tier alerts and CloudWatch billing alerts under Billing Preferences
    * also setting up a Cost Budget (1 euro) as extra measure: Billing and Cost Management > Budgets and Planning > Budgets > Create budget > ZeroSpend Budget

  * enable Cost-Usage Widget (already done in Console Home)
