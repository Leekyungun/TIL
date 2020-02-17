# git status 한글 깨지는 현상



## 현상

git status 할 때 한글이 깨짐

![1567662909594](images/git%20status%20%ED%95%9C%EA%B8%80%20%EA%B9%A8%EC%A7%80%EB%8A%94%20%ED%98%84%EC%83%81/1567662909594.png)

.


## 해결 방법

git config 수정

> git config --global core.quotepath false

![1567662915148](images/git%20status%20%ED%95%9C%EA%B8%80%20%EA%B9%A8%EC%A7%80%EB%8A%94%20%ED%98%84%EC%83%81/1567662915148.png)
