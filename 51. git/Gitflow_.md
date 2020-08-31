# Gitflow

Gitflow 란 git을 사용할때 workflow design인 중 하나로서 처음 공개되었고  [Vincent Driessen at nvie](http://nvie.com/posts/a-successful-git-branching-model/)  라는 사람이 만들었다. 

5가지 종류의 브랜치를 사용하며 크게 메인브랜치(master, develop)와 보조 브랜치(feature, release, hotfix)로 나눌 수 있다.

- master: 실제 서비스되는 운영서버의 브랜치
- develop: 개발 브랜치
- feature: 기능 개발 브랜치
- release: 운영 서버 배포전 테스트 단계 브랜치
- hotfix: 운영서버에서 발생한 버그를 수정하는 브랜치

 ![img](images/git%20flow/git-model@2x.png) 



master 브랜치에서 develop 브랜치를 생성한다. master 브랜치는 운영 서버에 배포되는 브랜치로 Tag를 달아준다. 



## Customflow
Fork를 사용해 개발을 진행
Upstream repo 에는 master, develop 브랜치만 존재
개발자는 upstream repo을 fork하여 개발을 진행하고 develop 브랜치에 pull request를 요청
pull request시에는 

- master: 실제 서비스되는 운영서버의 브랜치
- develop: 개발 브랜치
- feature: 기능 개발 브랜치
- release: 운영 서버 배포전 테스트 단계 브랜치
- hotfix: 운영서버에서 발생한 버그를 수정하는 브랜치



<확실한 부분>

- master는 운영서버에서 사용
- develop 브랜치에 merge할떄는 fork repo에서 pull request를 통해 진행
  - merge 방식은 일반으로 추후 commit관리가 안된다고 판단되면 squash merge 로 변경
  - 이슈가 있으면 develop 브랜치를 pull받고 브랜치를 생성 개발이 완료되면 pull request 후 merge 되면 브랜치는 삭제
  
  

<불확실한 부분>

- commit의 범위
- issue 어떻게 사용할 것인지?
  - 범위? API 단위? 기능 단위?
  - 이슈가 있으면 develop 브랜치를 pull받고 브랜치를 생성 개발이 완료되면 pull request 후 merge 되면 브랜치는 삭제
  
    

<최소한의 룰>
각 개발자는 프로젝트를 fork함
클론 받음
개발은 브랜치를 생성하여 진행하고 완료되면 develop 브랜치에 합침
pull request를 통하여 코드 리뷰 진행

<최대>
각 개발자는 프로젝트를 fork함
클론 받음
이슈에 어사이니로 등록되면 해당 이슈 확인 후 
fork repo의 develop 브랜치 upstream 기준으로 pull 하고 fork repo에 브랜치 생성
개발이 끝나면 fork repo의 develop 브랜치에 merge
pull request 이때 commit rule 적용 코드리뷰도 실시




참고 문헌

-  https://woowabros.github.io/experience/2017/10/30/baemin-mobile-git-branch-strategy.html 

-  https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow 