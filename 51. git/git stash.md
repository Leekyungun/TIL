# git stash

아직 마무리 하지 않은 작업을 스택에 저장할 수 있도록 하는 명령어이다.

- 명령어 정리([]안에 내용은 생략 가능함)
  - `git stash [push]`: stash 저장
  - `git stash list`: stash list 조회
  - `git stash apply [stash이름]`: stash 적용
  - `git stash pop`: 최근 stash 적용하고 stash 삭제
  - `git stash drop`: stash 삭제
  - `git stash clear`: stash 전체 삭제



### 언제 사용하는가?

- 현재 작업내역이 있는 상태에서 다른 commit으로 HEAD를 이동시켜야 하는 상황(작업 디렉토리를 변경할때)에서 임시 commit 을 사용하고 싶지 않을 때

- 현재 브랜치에서 작업한 내역을 현재 브랜치에 적용하지 않고 다른 브랜치에만 적용하고 싶을 때

- 저장소를 정리할때 git clrea 대신 git stash --all을 사용하면 임시로 저장하면서 변경내용을 삭제할 수 있다. 



### 사용법

#### stash 저장하기

`git stash [push]`  명령어를 통해 저장할 수 있다.

`-u` untracked 파일로 stash
`-a` 모든 파일을 stash
`-m` stash 메시지 수정
`-p` stash 범위 설정

>  git stash 는 pathspec으로 선택하여 stash 하는 옵션이 추가되었는데  `git stash save` 명령이 지원하지 못하는 기능이라 save를 사용하지 않는것을 권장한다. 



#### stash 적용하기

`git stash apply [stash이름]` stash 복구 stash 이름을 명시하지않으면 최신 stash를 적용한다. apply 명령어는 stash list에서 내역을 삭제하지 않으므로 따로 삭제해주어야 한다. 

`git stash pop` 최근 stash 내용을 적용하고 list에서 삭제한다. 



#### stash 삭제

`git stash drop` 사용하지 않는 stash 삭제

`git stash clear` 모든 stash 삭제



### 사용 예시

- 작업한 내용을 임시로 Stash로 저장하고 다른 브랜치로 이동할 때

  ```
  git stash -m "XX작업을 위한 임시 stash"
  git checkout develop
  ```

- 저장소 정리할 때

  ```
  git stash -a -u
  ```

  