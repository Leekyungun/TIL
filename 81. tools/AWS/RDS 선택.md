

# 엔진 선택

- Amazon Aurora
- Postgre SQL
- MySQL
- MariaDB

=> 시스템을 마이그레이션 하는것이 아니면 Aurora로 시작하는것이 좋을것이라 판단됨



Amazon Aurora

> Amazon Aurora는 고성능 상용 데이터베이스의 성능과 가용성에 오픈 소스 데이터베이스의 간편성과 비용 효율성을 결합하였으며 클라우드를 위해 구축된 MySQL 및 PostgreSQL 호환 [관계형 데이터베이스](https://aws.amazon.com/ko/relational-database/)입니다.
>
> Amazon Aurora는 표준 [MySQL](https://aws.amazon.com/ko/rds/mysql/what-is-mysql/) 데이터베이스보다 최대 5배 빠르고 표준 PostgreSQL 데이터베이스보다 3배 빠릅니다. 또한, 1/10의 비용으로 상용 데이터베이스의 보안, 가용성 및 안정성을 제공합니다. 하드웨어 프로비저닝, 데이터베이스 설정, 패치 및 백업과 같은 시간 소모적인 관리 작업을 자동화하는 [Amazon Relational Database Service(RDS)](https://aws.amazon.com/ko/rds/)에서 Amazon Aurora의 모든 것을 관리합니다.
>
> Amazon Aurora는 내결함성을 갖춘 자가 복구 분산 스토리지 시스템으로, 데이터베이스 인스턴스당 최대 64TB까지 자동으로 확장됩니다. 지연 시간이 짧은 읽기 전용 복제본 최대 15개, 특정 시점으로 복구, Amazon S3로 지속적 백업, 3개의 가용 영역(AZ)에 걸친 복제를 통해 뛰어난 성능과 가용성을 제공합니다.
>
> [Amazon RDS 관리 콘솔](https://console.aws.amazon.com/rds/home)로 이동하여 첫 번째 Aurora 데이터베이스 인스턴스를 생성하고 MySQL 및 PostgreSQL 데이터베이스를 마이그레이션하기 시작하십시오.



Postgre SQL

> [PostgreSQL](https://aws.amazon.com/ko/rds/postgresql/what-is-postgresql/)은 많은 엔터프라이즈 개발자 및 스타트업이 선호하는 [오픈 소스](https://aws.amazon.com/ko/products/databases/open-source-databases/) 관계형 데이터베이스가 되었으며 주요 비즈니스 및 모바일 애플리케이션을 실행하는 데 사용되고 있습니다. Amazon RDS를 사용하면 [클라우드](https://aws.amazon.com/ko/what-is-cloud-computing/)에서 PostgreSQL 배포를 손쉽게 설정, 운영 및 확장할 수 있습니다. Amazon RDS에서는 비용 효율적이고 크기 조정 가능한 하드웨어 용량을 갖춘 확장 가능한 PostgreSQL을 몇 분 만에 배포할 수 있습니다. Amazon RDS에서는 PostgreSQL 소프트웨어 설치 및 업그레이드, 스토리지 관리, 고가용성 및 읽기 처리량을 위한 복제, 재해 복구용 백업 등 복잡하고 시간 소모적인 관리 작업을 관리합니다.
>
> Amazon RDS for PostgreSQL을 사용하면 익숙한 PostgreSQL 데이터베이스 엔진의 기능에 액세스할 수 있습니다. 즉, 현재 기존 데이터베이스에서 이미 사용하고 있는 코드, 애플리케이션 및 도구를 Amazon RDS에서 사용할 수 있습니다. Amazon RDS는 다양한 성능 개선 사항, 견고함, 트랜잭션 관리, 쿼리 병렬 처리 등을 포함하는 [PostgreSQL 메이저 버전 11](https://aws.amazon.com/ko/rds/postgresql/why-postgresql-11/)을 지원합니다.



MySQL

> [MySQL](https://aws.amazon.com/ko/rds/mysql/what-is-mysql/)은 전 세계에서 가장 널리 사용되는 [오픈 소스](https://aws.amazon.com/ko/products/databases/open-source-databases/) 관계형 데이터베이스이며 Amazon RDS를 사용하면 [클라우드](https://aws.amazon.com/ko/what-is-cloud-computing/)에서 MySQL 배포를 손쉽게 설정, 운영 및 확장할 수 있습니다. Amazon RDS에서는 비용 효율적이고 크기 조정 가능한 하드웨어 용량을 갖춘 확장 가능한 MySQL 서버를 몇 분 만에 배포할 수 있습니다.
>
> Amazon RDS for MySQL에서 백업, 소프트웨어 패치, 모니터링, 확장 및 축소, 복제 같은 시간 소모적인 데이터베이스 관리 업무를 관리하므로 고객은 애플리케이션 개발에만 집중할 수 있습니다.
>
> Amazon RDS는 MySQL Community Edition 버전 5.5, 5.6, 5.7 및 8.0을 지원하므로 현재 사용 중인 코드, 애플리케이션, 도구에서 Amazon RDS를 사용할 수 있습니다.



MariaDB

> MariaDB는 MySQL을 개발한 개발자가 만든 인기 있는 오픈 소스 [관계형 데이터베이스](https://aws.amazon.com/ko/relational-database/)입니다. Amazon RDS를 사용하면 [클라우드](https://aws.amazon.com/ko/what-is-cloud-computing/)에서 MariaDB 서버 배포를 손쉽게 설정, 운영 및 확장할 수 있습니다. Amazon RDS에서는 비용 효율적이며 크기 조정이 가능한 하드웨어 용량을 갖춘 확장 가능한 MariaDB 클라우드 데이터베이스를 몇 분 만에 배포할 수 있습니다.
>
> 또한, 백업, 소프트웨어 패치, 모니터링, 확장, 복제 같은 시간 소모적인 데이터베이스 관리 업무를 대신 처리해 주므로 고객은 애플리케이션 개발에만 집중할 수 있습니다.
>
> Amazon RDS는 MariaDB Server 버전 10.0, 10.1, 10.2 및 10.3을 지원하므로 현재 사용 중인 코드, 애플리케이션 및 도구를 Amazon RDS에서 사용할 수 있습니다.





참고

- https://aws.amazon.com/ko/rds/