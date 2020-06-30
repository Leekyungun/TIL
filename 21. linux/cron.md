# cron

특정한 시간에 특정한 작업을 수행하게 해주는 스케줄링 역할

cron table을 줄여서 crontab 이라고 부른다.



## 기본 명령어

- 등록 및 수정
  ```
  crontab -e
  ```

- 조회
  ```
  crontab -l
  ```

- 삭제
  ```
  crontab -d
  ```



## 로그

```
* * * * * /home/script/test.sh >> /home/script/test.sh.log 2>&1
```



```
* * * * * /home/script/test.sh > /dev/null 2>&1
```



## 백업

```
50 23 * * * crontab -l > /home/centos/crontab_bak.txt
```



> /dev/null 2>&1 는 에러메시지를 화면에 표시하지 않는것이다. 하지만 이걸로는 조금 부족하다. 
> 리눅스의 파일디스크립터, 표준 입력/ 표준 출력/ 표준 에러에 대해 알아보자

