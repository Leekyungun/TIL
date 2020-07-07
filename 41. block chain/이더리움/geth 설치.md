# Geth 설치

 설치할 서버 사양

- OS: CentOS 7.8(Linux version 3.10.0-1127.10.1.el7.x86_64)
- CPU: Intel(R) Xeon(R) CPU E3-1231 v3 @ 3.40GHz (8 core)
- RAM: 32G
- DISK: 700GB SSD(/data 500 GB)



## 설치
CentOS 최소 설치 버전으로 설치를 진행하였으며, golang 언어는 yum을 이용하여 설치하기위해 epel 먼저 설치

```shell
sudo yum -y install wget
wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
sudo yum install epel-release-latest-7.noarch.rpm
```



```shell
sudo yum -y update
sudo yum -y install gmp-devel
sudo yum -y install git
sudo yum install -y golang
```



```shell
git clone https://github.com/ethereum/go-ethereum
cd go-ethereum/
make all
```



/data/go-ethereum/build/bin/geth --syncmode full --datadir /data/ethereum/mainnet/



## 에러

```shell
[centos@ip-10-112-11-85 go-ethereum]$ make all
env GO111MODULE=on go run build/ci.go install
go: github.com/golang/snappy@v0.0.2-0.20190904063534-ff6b7dc882cf: invalid pseudo-version: git fetch --unshallow -f origin in /home/centos/go/pkg/mod/cache/vcs/bd5478a77a28a7d755c9e7a8b339db5eab8981ed54642194facc07ec0db93053: exit status 128:
	fatal: git fetch-pack: expected shallow list
make: *** [all] Error 1
```

git 버전이 낮음 버전 업그레이드 해야함

```shell
[centos@ip-10-112-11-85 go-ethereum]$ sudo yum install http://opensource.wandisco.com/centos/7/git/x86_64/wandisco-git-release-7-2.noarch.rpm
[centos@ip-10-112-11-85 go-ethereum]$ sudo yum install git
[centos@ip-10-112-11-85 go-ethereum]$ make all
```



https://dl.fedoraproject.org/pub/epel/

[https://zetawiki.com/wiki/Yum_%EC%A0%80%EC%9E%A5%EC%86%8C_%ED%99%95%EC%9D%B8](https://zetawiki.com/wiki/Yum_저장소_확인)

https://www.cyberciti.biz/faq/installing-rhel-epel-repo-on-centos-redhat-7-x/