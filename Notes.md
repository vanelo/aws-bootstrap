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