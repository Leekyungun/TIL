# git cache 삭제



.gitignore 파일에 
git에서 관리하지 않을 파일을 추가하여도 
이미 commit을 했던 파일이라면 해당 파일이 staging 상태이기때문에
변경사항이 계속 추적된다. 



```
git rm -r --cached <file_name>
git add <file_name>
git commit -m "clear cache"
```

