# git log

저장소의 히스토리를 조회하는 명령어



`git log` 명령어를 실행하면 아래와 같이 출력된다. 
시간의 역순으로 정렬되며 각 commit의 체크섬, 작성자, 시간, commit message를 보여준다.

```
$ git log
commit c6e273bbd6d2a1e9fc38811ab84739091fd28def (origin/master)
Author: leekyungun <leekyungun91@gmail.com>
Date:   Fri Aug 7 16:27:54 2020 +0900

    [기능] 모니터링 데몬 생성

commit e060bc3f9514de2dff366b018d98a2826c3dc342
Author: leekyungun <leekyungun91@gmail.com>
Date:   Tue Apr 28 20:40:32 2020 +0900

    [기능] telegram bot 추가

commit eb3228374b6dce7256fd8435d56739341a20290b
Author: leekyungun <leekyungun91@gmail.com>
Date:   Fri Apr 24 20:19:32 2020 +0900

    [기능] 특정 디렉토리 log 파일 삭제 기능 추가

```



## 주요 옵션

| 옵션              | 설명                                                         |
| :---------------- | :----------------------------------------------------------- |
| -p              | 각 커밋에 적용된 패치를 보여준다.                            |
| --stat          | 각 커밋에서 수정된 파일의 통계정보를 보여준다.               |
| --shortstat     | --stat 명령의 결과 중에서 수정한 파일, 추가된 라인, 삭제된 라인만 보여준다. |
| --name-only     | 커밋 정보중에서 수정된 파일의 목록만 보여준다.               |
| --name-status   | 수정된 파일의 목록을 보여줄 뿐만 아니라 <br />파일을 추가한 것인지, 수정한 것인지, 삭제한 것인지도 보여준다. |
| --abbrev-commit | 40자 짜리 SHA-1 체크섬을 전부 보여주는 것이 아니라 처음 몇 자만 보여준다. |
| --relative-date | 정확한 시간을 보여주는 것이 아니라 <br />“2 weeks ago” 처럼 상대적인 형식으로 보여준다. |
| --graph         | 브랜치와 머지 히스토리 정보까지 아스키 그래프로 보여준다.    |
| --pretty        | 지정한 형식으로 보여준다. <br />이 옵션에는 oneline, short, full, fuller, format이 있다. <br />format은 원하는 형식으로 출력하고자 할 때 사용한다. |
| --oneline       | --pretty=oneline --abbrev-commit 두 옵션을 함께 사용한 것과 같다. |



## 범위 제한 

- 개수
- 시간
- 파일 경로
- commit message
- 작성자



| 옵션              | 설명                                              |
| ----------------- | ------------------------------------------------- |
| -(n)              | 최근 n 개의 커밋만 조회한다.                      |
| --since, --after  | 명시한 날짜 이후의 커밋만 검색한다.               |
| --until, --before | 명시한 날짜 이전의 커밋만 조회한다.               |
| --author          | 입력한 저자의 커밋만 보여준다.                    |
| --committer       | 입력한 커미터의 커밋만 보여준다.                  |
| --grep            | 커밋 메시지 안의 텍스트를 검색한다.               |
| -S                | 커밋 변경(추가/삭제) 내용 안의 텍스트를 검색한다. |



### 개수

조회 개수는 `-<n>` 이고 n은 최근 n개의 commit이다. 

```
$ git log -3
commit c6e273bbd6d2a1e9fc38811ab84739091fd28def (HEAD -> master, origin/master)
Author: leekyungun <leekyungun91@gmail.com>
Date:   Fri Aug 7 16:27:54 2020 +0900

    [기능] 모니터링 데몬 생성

commit e060bc3f9514de2dff366b018d98a2826c3dc342
Author: leekyungun <leekyungun91@gmail.com>
Date:   Tue Apr 28 20:40:32 2020 +0900

    [기능] telegram bot 추가

commit eb3228374b6dce7256fd8435d56739341a20290b
Author: leekyungun <leekyungun91@gmail.com>
Date:   Fri Apr 24 20:19:32 2020 +0900

    [기능] 특정 디렉토리 log 파일 삭제 기능 추가
```

###  시간



### 파일 경로



###  commit message

```
$ git log --grep bot
commit e060bc3f9514de2dff366b018d98a2826c3dc342
Author: leekyungun <leekyungun91@gmail.com>
Date:   Tue Apr 28 20:40:32 2020 +0900

    [기능] telegram bot 추가

```



###  작성자

```
$ git log --author leekyungun
commit c6e273bbd6d2a1e9fc38811ab84739091fd28def (HEAD -> master, origin/master)
Author: leekyungun <leekyungun91@gmail.com>
Date:   Fri Aug 7 16:27:54 2020 +0900

    [기능] 모니터링 데몬 생성

commit e060bc3f9514de2dff366b018d98a2826c3dc342
Author: leekyungun <leekyungun91@gmail.com>
Date:   Tue Apr 28 20:40:32 2020 +0900

    [기능] telegram bot 추가

commit eb3228374b6dce7256fd8435d56739341a20290b
Author: leekyungun <leekyungun91@gmail.com>
Date:   Fri Apr 24 20:19:32 2020 +0900

    [기능] 특정 디렉토리 log 파일 삭제 기능 추가
```



## `git log --pretty=format` 옵션





## 참고

- [https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%BB%A4%EB%B0%8B-%ED%9E%88%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%A1%B0%ED%9A%8C%ED%95%98%EA%B8%B0](https://git-scm.com/book/ko/v2/Git의-기초-커밋-히스토리-조회하기)

