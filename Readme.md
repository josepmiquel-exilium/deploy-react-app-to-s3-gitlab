## CD/CI with Gitlab / AWS S3 / Create-React-App

1. Create S3 bucket with the following policy, enable public read and ACL:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Stmt1380877761162",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*"
            },
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::<<Enter Your Bucket Name>>/*"
        }
    ]
}
```

[More detailed information here](https://www.cloudthat.com/resources/blog/step-by-step-guide-to-deploy-reactjs-app-on-aws-s3/)

2. Configure your bucket to serve a host static web.
   [More detailed information here](https://www.cloudthat.com/resources/blog/step-by-step-guide-to-deploy-reactjs-app-on-aws-s3/)
3. Modify the S3_BUCKET variable with the name of the bucket in the .yml file.
4. Go to Identity and Access Management (IAM) in AWS and create new access keys.
5. Modify the variables AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY in the .yml file.
6. Commit and put your changes to the branch master.
7. It's done! Your site is deployed!
