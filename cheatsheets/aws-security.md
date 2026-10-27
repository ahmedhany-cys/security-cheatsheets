# AWS Security (CLI)

## Identity
```bash
aws sts get-caller-identity                      # who am I?
aws iam list-users
aws iam list-attached-user-policies --user-name alice
aws iam list-access-keys --user-name alice
aws iam generate-credential-report && aws iam get-credential-report
```

## Logging and detection
```bash
aws cloudtrail describe-trails
aws cloudtrail lookup-events --lookup-attributes AttributeKey=EventName,AttributeValue=ConsoleLogin
aws guardduty list-detectors
aws guardduty list-findings --detector-id <id>
```

## Storage
```bash
aws s3api get-public-access-block --bucket my-bucket
aws s3api get-bucket-policy --bucket my-bucket
aws s3api get-bucket-encryption --bucket my-bucket
```

## Network
```bash
aws ec2 describe-security-groups \
  --filters Name=ip-permission.cidr,Values=0.0.0.0/0   # open to the world
```

## Baseline checklist
- MFA on root, no root access keys
- Least-privilege IAM; prefer roles over long-lived keys
- CloudTrail on in all regions; GuardDuty enabled
- S3 Block Public Access at the account level
- Encrypt EBS, S3, RDS by default
