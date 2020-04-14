merge에는 세가지 종류가 있다. 

- --ff
- --no-ff
- --squash



--ff

머지 대상의 브랜치와 fast-forward의 관계인 경우 merge commit은 만들어지지 않고 브랜치의 참조만 변경된다. (fast-forward 관계가 아닌경우 merge commit이 만들어진다.)

--no-ff

fast-forward의 관계라도 반드시 merge commit을 만든다.

