# sudo 권한 부여

sudo 권한을 부여하는 파일은 `/etc/sudoers` 파일이다.

기본적으로 읽기 권한만있는 파일이기 때문에 쓰기권한을 부여하고 내용을 추가한 다음 다시 쓰기 권한을 빼준다.



## 작업 기록

- `/etc/sudoers` 파일의 권한(440) 확인 

```shell
[root@localhost ~]# ll /etc/sudoers
-r--r-----. 1 root root 4328 Nov 28  2019 /etc/sudoers
```



- 쓰기 권한을 추가한 다음
  파일의 권한(640) 확인

```shell
[root@localhost ~]# chmod +w /etc/sudoers
[root@localhost ~]# ll /etc/sudoers
-rw-r-----. 1 root root 4328 Nov 28  2019 /etc/sudoers
```



- `/etc/sudoers` 파일 내용 추가

```shell
[root@localhost ~]# vi /etc/sudoers
```

```shell
...
## Next comes the main part: which users can run what software on
## which machines (the sudoers file can be shared between multiple
## systems).
## Syntax:
##
##      user    MACHINE=COMMANDS
##
## The COMMANDS section may have other options added to it.
##
## Allow root to run any commands anywhere
root    ALL=(ALL)       ALL
centos  ALL=(ALL)       ALL

## Allows members of the 'sys' group to run networking, software,
## service management apps and more.
# %sys ALL = NETWORKING, SOFTWARE, SERVICES, STORAGE, DELEGATING, PROCESSES, LOCATE, DRIVERS
...
```



- 쓰기 권한 빼고 
  파일 권한(440) 확인 및 수정한 시간 확인

```shell
[root@localhost ~]# chmod -w /etc/sudoers
[root@localhost ~]# ll /etc/sudoers
-r--r----- 1 root root 4356 Jun 17 21:55 /etc/sudoers
```

