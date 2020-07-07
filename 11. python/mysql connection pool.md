mysql 패키지 
flask_mysqldb
pymysql
MySQL-python 1.2.5
SQLAlchemy
python-mysql-pool
mysql-connector-python

이중 커넥션 풀을 제공해주는건 
SQLAlchemy
python-mysql-pool
mysql-connector-python

SQLAlchemy의 경우 pool 갯수 이상의 connection을 요구 할 경우 대기하는데 나머지는 에러를 발생시킨다고함
SQLAlchemy 에서는 쿼리 요청이 없더라도 일정 주기로 갱신하는 pool_recycle을 사용하여 해결한다. pool_recycle의 주기가 wait_timeout 시간보다 작아야 한다.