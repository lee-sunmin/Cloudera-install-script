


1. AWS EC2 생성

CM01 | NM01 | DN01 | DN02 | DN03


2. 접속

2.1 pem permission 공개 범위가 넓어서 생긴 문제로 chmod 700으로 permission 범위 변경
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

