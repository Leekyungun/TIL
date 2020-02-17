# lambda 계층 생성 - python



## 패키지 파일 생성

계층에 추가하려는 패키지를 python 디렉토리 아래 설치하고
python 디렉토리를 zip 파일로 만든다.



### 패키지 파일 생성

`pip install --target ./python redis`



### zip 파일 생성

`zip -r python.zip python`



### 로그

```
(python3) [centos@ip-172-16-10-145 test]$ pip install --target ./python redis
Collecting redis
  Using cached https://files.pythonhosted.org/packages/32/ae/28613a62eea0d53d3db3147f8715f90da07667e99baeedf1010eb400f8c0/redis-3.3.11-py2.py3-none-any.whl
Installing collected packages: redis
Successfully installed redis-3.3.11
(python3) [centos@ip-172-16-10-145 test]$ tree
.
└── python
    ├── redis
    │   ├── client.py
    │   ├── _compat.py
    │   ├── connection.py
    │   ├── exceptions.py
    │   ├── __init__.py
    │   ├── lock.py
    │   ├── __pycache__
    │   │   ├── client.cpython-37.pyc
    │   │   ├── _compat.cpython-37.pyc
    │   │   ├── connection.cpython-37.pyc
    │   │   ├── exceptions.cpython-37.pyc
    │   │   ├── __init__.cpython-37.pyc
    │   │   ├── lock.cpython-37.pyc
    │   │   ├── sentinel.cpython-37.pyc
    │   │   └── utils.cpython-37.pyc
    │   ├── sentinel.py
    │   └── utils.py
    └── redis-3.3.11.dist-info
        ├── INSTALLER
        ├── LICENSE
        ├── METADATA
        ├── RECORD
        ├── top_level.txt
        └── WHEEL

4 directories, 22 files
(python3) [centos@ip-172-16-10-145 test]$ zip -r python.zip python
  adding: python/ (stored 0%)
  adding: python/redis/ (stored 0%)
  adding: python/redis/__init__.py (deflated 61%)
  adding: python/redis/_compat.py (deflated 69%)
  adding: python/redis/client.py (deflated 78%)
  adding: python/redis/connection.py (deflated 76%)
  adding: python/redis/exceptions.py (deflated 64%)
  adding: python/redis/lock.py (deflated 73%)
  adding: python/redis/sentinel.py (deflated 75%)
  adding: python/redis/utils.py (deflated 46%)
  adding: python/redis/__pycache__/ (stored 0%)
  adding: python/redis/__pycache__/__init__.cpython-37.pyc (deflated 38%)
  adding: python/redis/__pycache__/_compat.cpython-37.pyc (deflated 52%)
  adding: python/redis/__pycache__/client.cpython-37.pyc (deflated 66%)
  adding: python/redis/__pycache__/connection.cpython-37.pyc (deflated 56%)
  adding: python/redis/__pycache__/exceptions.cpython-37.pyc (deflated 68%)
  adding: python/redis/__pycache__/lock.cpython-37.pyc (deflated 59%)
  adding: python/redis/__pycache__/sentinel.cpython-37.pyc (deflated 58%)
  adding: python/redis/__pycache__/utils.cpython-37.pyc (deflated 35%)
  adding: python/redis-3.3.11.dist-info/ (stored 0%)
  adding: python/redis-3.3.11.dist-info/LICENSE (deflated 42%)
  adding: python/redis-3.3.11.dist-info/METADATA (deflated 67%)
  adding: python/redis-3.3.11.dist-info/WHEEL (deflated 14%)
  adding: python/redis-3.3.11.dist-info/top_level.txt (stored 0%)
  adding: python/redis-3.3.11.dist-info/RECORD (deflated 49%)
  adding: python/redis-3.3.11.dist-info/INSTALLER (stored 0%)
(python3) [centos@ip-172-16-10-145 test]$ ls
python  python.zip
(python3) [centos@ip-172-16-10-145 test]$ 
```



## AWS에서 계층 생성

`서비스 > lambda > 계층`
우측 상단 `계층 생성` 클릭

![1573007513916](images/python%20%EA%B3%84%EC%B8%B5/1573007513916.png)



리눅스에서 생성한 python.zip 파일은 윈도우에 옮겨두고
이름과 설명을 기입하고 python.zip 파일을 업로드한다. 
호환 런타임에는 python3.7을 선택한다. 

![1573007733736](images/python%20%EA%B3%84%EC%B8%B5/1573007733736.png)



계층생성 완료 화면

![1573018376755](images/python%20%EA%B3%84%EC%B8%B5/1573018376755.png)



## lambda 함수에서 계층 적용

계층을 추가할 함수에 들어가서
`Designer > Layers` 에서 계층을 추가할 수 있다. 
`Layers`를 클릭하면 아래 탭이 생성된다.

![1573018474489](images/python%20%EA%B3%84%EC%B8%B5/1573018474489.png)



`Add a layer` 버튼을 클릭하여 계층을 추가한다.

![1573018548874](images/python%20%EA%B3%84%EC%B8%B5/1573018548874.png)



위에서 생성한 계층의 이름을 선택하고 버전을 선택한다. 
`Add` 버튼을 통해 계층을 추가할 수 있다. 

![1573018648923](images/python%20%EA%B3%84%EC%B8%B5/1573018648923.png)



`Layers` 에 (1)로 하나가 추가된 것을 확인하고
마지막으로 `Save` 버튼을 클릭하여 변경된 사항을 함수에 적용한다. 

![1573018724066](images/python%20%EA%B3%84%EC%B8%B5/1573018724066.png)