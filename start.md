
https://docs.cloudera.com/documentation/enterprise/6/6.3/topics/cm_ig_reqs_space.html#concept_tjd_4yc_gr

1. AWS EC2 생성

CM01 | NM01 | DN01 | DN02 | DN03

https://velog.io/@inyong_pang/AWS-EC2-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-3ck513o2af


2. 접속

2.1 pem permission 공개 범위가 넓어서 생긴 문제로 chmod 600으로 permission 범위 변경
~~~
iseonmin-ui-MacBookPro:Desktop iseonmin$ ssh -i /경로/lsm-test.pem ubuntu@[public ip]
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0733 for 'lsm-test.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "lsm-test.pem": bad permissions
ubuntu@[public ip]: Permission denied (publickey).
~~~

~~~
iseonmin-ui-MacBookPro:pem iseonmin$ ssh -i /경로/lsm-test.pem ubuntu@[public ip]
Welcome to Ubuntu 20.04.2 LTS (GNU/Linux 5.4.0-1045-aws x86_64)
~~~

