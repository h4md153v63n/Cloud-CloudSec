# Challenge 5

**Challenge 5:** https://bigiamchallenge.com/challenge/5

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/d845a952-6fee-43c8-a298-b192a1edee4b)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/ab739629-f041-446f-aa59-16d35b18c4ac)



```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "mobileanalytics:PutEvents",
                "cognito-sync:*"
            ],
            "Resource": "*"
        },
        {
            "Sid": "VisualEditor1",
            "Effect": "Allow",
            "Action": [
                "s3:GetObject",
                "s3:ListBucket"
            ],
            "Resource": [
                "arn:aws:s3:::wiz-privatefiles",
                "arn:aws:s3:::wiz-privatefiles/*"
            ]
        }
    ]
}
```




