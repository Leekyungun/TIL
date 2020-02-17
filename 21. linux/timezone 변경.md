





```
ubuntu@ethereum:/data/ethereum/data/ropsten/geth/chaindata$ date
Tue Oct 29 11:13:18 UTC 2019
ubuntu@ethereum:/data/ethereum/data/ropsten/geth/chaindata$ sudo ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime
[sudo] password for ubuntu: 
ubuntu@ethereum:/data/ethereum/data/ropsten/geth/chaindata$ date
Tue Oct 29 20:14:09 KST 2019
```



![1572347767150](images/%EC%8B%9C%EA%B0%84%EB%8C%80%20%EB%B3%80%EA%B2%BD/1572347767150.png)





#### [리눅스] CentOS 7 타임존 변경



CentOS 7 에서 타임존 변경 방법입니다.

사용가능한 타임존

```
# timedatectl list-timezones | grep Seoul
Asia/Seoul
```

타임존 변경

```
# sudo timedatectl set-timezone Asia/Seoul
```

수동으로 변경해야 할 경우는 기존의 /etc/localtime 파일을 삭제 후

```
# sudo ln -s /usr/share/zoneinfo/Asia/Seoul /etc/localtime
```

타임존 확인

```
# date
2016. 01. 18. (월) 21:12:30 KST
```