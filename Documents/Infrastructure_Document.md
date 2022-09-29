# Infrastructure
Table contents:
1. AWS RDS
2. AWS Elastic Beanstalk
3. AWS S3
4. GitHub
5. CircleCI

## AWS RDS
- DB identifier: database-1
- HOST: database-1.c0vpqovd9sta.us-east-1.rds.amazonaws.com
- Engine: PostgreSQL
- Region & AZ: Region & AZ
- Publicly accessible: Yes

## AWS Elastic Beanstalk
- Application: udagram-api
- Environment: udagram-api
- Version: app-220927_100731554154
- URL: `http://udagram-api.us-east-1.elasticbeanstalk.com/`
- Environment properties: AWS_BUCKET, AWS_PROFILE, AWS_REGION, ENV, JWT_SECRET, PORT, POSTGRES_DB, POSTGRES_HOST, POSTGRES_PASSWORD, POSTGRES_USERNAME

## AWS S3
- Bucket: elasticbeanstalk-us-east-1-466850583282
- Static website hosting: Enable
- Index document: index.html
- Website: `http://elasticbeanstalk-us-east-1-466850583282.s3-website-us-east-1.amazonaws.com`
- Bucket policy:
```
{
    "Version": "2008-10-17",
    "Statement": [
        {
            "Sid": "eb-ad78f54a-f239-4c90-adda-49e5f56cb51e",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::466850583282:role/aws-elasticbeanstalk-ec2-role"
            },
            "Action": "s3:PutObject",
            "Resource": "arn:aws:s3:::elasticbeanstalk-us-east-1-466850583282/resources/environments/logs/*"
        },
        {
            "Sid": "eb-af163bf3-d27b-4712-b795-d1e33e331ca4",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::466850583282:role/aws-elasticbeanstalk-ec2-role"
            },
            "Action": [
                "s3:ListBucket",
                "s3:ListBucketVersions",
                "s3:GetObject",
                "s3:GetObjectVersion"
            ],
            "Resource": [
                "arn:aws:s3:::elasticbeanstalk-us-east-1-466850583282",
                "arn:aws:s3:::elasticbeanstalk-us-east-1-466850583282/resources/environments/*"
            ]
        },
        {
            "Sid": "eb-58950a8c-feb6-11e2-89e0-0800277d041b",
            "Effect": "Deny",
            "Principal": {
                "AWS": "*"
            },
            "Action": "s3:DeleteBucket",
            "Resource": "arn:aws:s3:::elasticbeanstalk-us-east-1-466850583282"
        }
    ]
}
```

## GitHub
- Repo: `https://github.com/anhdung237/udacityfinalproject.git`

## CircleCI
- Project: udacityfinalproject
- Environment variables: AWS_ACCESS_KEY_ID, AWS_DEFAULT_REGION, AWS_SECRET_ACCESS_KEY, AWS_BUCKET, AWS_PROFILE, AWS_REGION, ENV, JWT_SECRET, PORT, POSTGRES_DB, POSTGRES_HOST, POSTGRES_PASSWORD, POSTGRES_USERNAME