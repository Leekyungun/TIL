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


참고 문헌

-  https://woowabros.github.io/experience/2017/10/30/baemin-mobile-git-branch-strategy.html 

-  https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow 