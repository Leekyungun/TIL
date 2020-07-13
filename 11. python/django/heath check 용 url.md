# heath check용

AWS 대상그룹에서 특정 시간동안 heath check를 날린다. 
heath check용으로 view를 만들기 싫어 url 매핑해주는 부분에서 바로 return을 할 수 있게 하였다.



```python
from django.conf.urls import url
from django.http.response import HttpResponse

urlpatterns = [
    url('', lambda request: HttpResponse()),
]
```

