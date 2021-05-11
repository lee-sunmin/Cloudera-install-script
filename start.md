
https://docs.cloudera.com/documentation/enterprise/6/6.3/topics/cm_ig_reqs_space.html#concept_tjd_4yc_gr

1. AWS EC2 생성

CM01 | NM01 | DN01 | DN02 | DN03

환경 : Ubuntu
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

3. 
a. 리눅스 계정, 유저그룹 생성 [all node]

training/training
~~~
# 계정 생성
sudo useradd training
sudo usermod -u 3800 training
sudo passwd training

sudo groupadd skcc
cat /etc/passwd | grep training
sudo usermod -aG skcc training

# 계정 수도권한추가
sudo usermod -aG root training
~~~

b. Configure Network Names [all node]
~~~
sudo hostnamectl set-hostname [node name].com
ex) sudo hostnamectl set-hostname cm01.com

sudo vi /etc/hosts

// x.x.x.x means public ip
1.1.1.1 cm01.com cm01
2.2.2.2 mn01.com mn01
3.3.3.3 dn01.com dn01
4.4.4.4 dn02.com dn02
5.5.5.5 dn03.com dn03
~~~

c. Enable an NTP Service

~~~
sudo apt-get install ntp

// 아래 에러 발생 시 
// $ sudo apt-get update 
ubuntu@ip-172-31-44-9:~$ sudo apt-get install ntp
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Package ntp is not available, but is referred to by another package.
This may mean that the package is missing, has been obsoleted, or
is only available from another source

E: Package 'ntp' has no installation candidate
//
~~~


