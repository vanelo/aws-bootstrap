# Configure cli
aws configure --profile devVane
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-east-1
Default output format [None]: json

# Test cli
aws ec2 describe-instances --profile devVane

# Let deploy script executable
chmod +x deploy-infra.sh

# Github access token

    NOTE: Before we run the code, we will require a Github access token so you don’t need to put in your username and password whenever you access Github through the terminal widget. To generate an access token, go to https://github.com/settings/tokens/new and click Generate new token. Give it repo and admin:repo_hook permissions, and click Generate token.

    NOTE: You just have to put your Github token ONCE in the terminal widget, it will persist that information in all the other terminal widgets automatically.

# Run and push the code

    NOTE: It will automatically push the code to your Github too.

    NOTE: In deploy-infra.sh file, on Line #1 (which is also highlighted in the code), another file by the name of aws_credentials is getting executed to set your AWS credentials but you can’t see it. Similarly in github.sh, on Line #1, github_credentials.sh is getting executed to set your Github credentials. We have hidden these two files so your main focus is on the code, not to set up the credentials.

# Github accessToken generation (Replace <username> with your GitHub username and Replace <token> with your GitHub access token)
```
mkdir -p ~/.github
echo "aws-bootstrap" > ~/.github/aws-bootstrap-repo
echo "<username>" > ~/.github/aws-bootstrap-owner
echo "<token>" > ~/.github/aws-bootstrap-access-token
```

## After create the code papeline
we can deploy our infrastructure updates. But first, we need to delete our stack from the CloudFormation console, because the changes we’ve made will not trigger CloudFormation to tear down our EC2 instance and start a new one. So, let’s delete our stack, and recreate it by running the deploy-infra.sh script.

`./deploy-infra.sh`


