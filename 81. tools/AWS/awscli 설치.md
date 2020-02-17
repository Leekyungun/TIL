# awscli 설치

aws cil는 yum이나 apt-get으로 설치할 수 있지만 python의 pip으로 설치하는것이 최신버전을 유지하기에 좋다. 



## pip 설치

```shell
[centos@localhost ~]$ curl -O https://bootstrap.pypa.io/get-pip.py
[centos@localhost ~]$ python get-pip.py --user
[centos@localhost ~]$ vi .bash_profile 
  PATH=$PATH:$HOME/.local/bin
  export PATH
[centos@localhost ~]$ source ~/.bash_profile
[centos@localhost ~]$ pip --version
pip 19.2.3 from /home/centos/.local/lib/python2.7/site-packages/pip (python 2.7)
```



## aws cli 설치

```shell
[centos@localhost ~]$ pip install awscli --upgrade --user
DEPRECATION: Python 2.7 will reach the end of its life on January 1st, 2020. Please upgrade your Python as Python 2.7 won't be maintained after that date. A future version of pip will drop support for Python 2.7. More details about Python 2 support in pip, can be found at https://pip.pypa.io/en/latest/development/release-process/#python-2-support
Collecting awscli
  Downloading https://files.pythonhosted.org/packages/9a/cc/ee8d4433d27a854b2a4af4570e94853d38bc603e61fa75ede384a4665f77/awscli-1.16.242-py2.py3-none-any.whl (2.1MB)
     |████████████████████████████████| 2.1MB 559kB/s 
[centos@localhost ~]$ aws --version
aws-cli/1.16.242 Python/2.7.5 Linux/3.10.0-957.el7.x86_64 botocore/1.12.232

```



## aws 환경 설정



```shell
[centos@localhost ~]$ vi ~/aws/config
###
[default]
output = text
region = ap-northeast-1
###

[centos@localhost ~]$ vi ~/.aws/credentials
###
[default]
aws_access_key_id = ACCESS_KEY
aws_secret_access_key = SECRET_KEY
###
```

