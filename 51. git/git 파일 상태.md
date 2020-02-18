# git 파일 상태

파일은 크게 Tracked(관리대상)와 Untracked(관리대상아님)으로 나눈다.
처음 파일을 생성하면 Untracked 상태이고 add 하면 Tracked 상태가되고
rm 명령어 후 커밋으로 파일을 Untracked 상태로 변경할 수 있다.

Tracked 상태는 Unmodified, Modified, Staged 3가지 상태로 나눌 수 있다.

- Unmodified: commit으로 저장된 상태
- Modified : Unmodified상태였던 파일들을 수정하였을 때 상태
- Staged : 최소 파일 생성 후 add를 하거나 modified 상태의 파일을 add, rm 하였을 때 상태

![img](images/git%20%ED%8C%8C%EC%9D%BC%20%EC%83%81%ED%83%9C/git_file_status.png)