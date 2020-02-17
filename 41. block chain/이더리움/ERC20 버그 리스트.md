# ERC20 버그 리스트

> 이더리움 자체의 버그보다는 스마트컨트렉트에서 버그가 발생하는 경우가 종종 존재한다.
> 그러한 사례들을 찾아보고 사전에 방지하고자 지금까지 나온 버그를 조사함



## 사례

### 아이콘 토큰

- 관리자를 제외하고 입출금 금지를 설정할 수 있음
- https://etherscan.io/address/0xb5a5f22694352c15b00323844ad545abb2b11028#code
- ![1575550043923](images/ERC20%20%EB%B2%84%EA%B7%B8%20%EB%A6%AC%EC%8A%A4%ED%8A%B8/1575550043923.png)



### 마이 이더월렛

- https://www.coinpress.co.kr/2018/04/26/4101/
- 마이 이더 월렛의 구조적인 취약점으로 오케이엑스 거래소에서 ERC20 토큰 입금을 중지함



### SmartMesh(SMT)

- [https://medium.com/haechi-audit-kr/smartmesh-erc20-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%BB%A8%ED%8A%B8%EB%9E%99%ED%8A%B8-%EC%B7%A8%EC%95%BD%EC%A0%90-%EB%B6%84%EC%84%9D-b84006c05dc9](https://medium.com/haechi-audit-kr/smartmesh-erc20-스마트-컨트랙트-취약점-분석-b84006c05dc9)

- uint256 덧셈에 대한 overflow 
- zeppelin 사에서 만든 safeMath.sol을 사용하지 않고 자체 라이브러리를 사용하였는데 거기서 에러가 발생함

