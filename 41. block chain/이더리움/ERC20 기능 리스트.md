# ERC20 기능 리스트

> Open Zeppelin를 베이스로 사용하고
> 권한은 Owner 하나의 주소만 사용하는것으로 변경
> 추가로 USDT의 blacklist 기능을 추가



## ERC20 발행 방법

- ERC20 표준을 만족하는 코드를 작성
  - https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md
- 토큰 발행 프레임워크 사용
  - [Open Zeppelin](https://github.com/ConsenSys/Token-Factory/blob/master/contracts/StandardToken.sol)
  - [Token factory](https://github.com/OpenZeppelin/zeppelin-solidity)
  - [web site](https://vittominacori.github.io/erc20-generator/)

> ERC20은 자체 개발보다는 검증이 완료된 오픈소스를 기본으로 사용하고
> 필요한 기능을 추가하는 방식으로 개발할 예정
>
> Open Zeppelin 을 기본으로 사용





## Open Zeppelin 기능

> 전송기능, 일시 정지기능, 발행량 증가 기능, 소각기능(자신의 토큰만)



- write
  - base
    - transfer(address recipient, uint256 amount)
    - transferFrom(address sender, address recipient, uint256 amount)
    - approve(address spender, uint256 amount)
    - decreaseAllowance(address spender, uint256 subtractedValue)
    - increaseAllowance(address spender, uint256 addedValue)
  - bunable
    - burn(uint256 amount)
    - burnFrom(address account, uint256 amount)
  - mintable
    - addMinter(address account)
    - renounceMinter()
    - mint(address account, uint256 amount)
  - pausable
    - addPauser(address account)
    - renoncePauser()
    - pause()
    - unpause()
- read
  - base
    - name
    - sysbol
    - totalSupply
    - decimals
    - allowance
    - balanceOf
  - mintable
    - isMinter
  - pausable
    - isPauser
    - paused



### base

#### transfer(address recipient, uint256 amount)

자신의 토큰을 recipient에게 amount 만큼 전송

#### transferFrom(address sender, address recipient, uint256 amount)

sender의 토큰을 recipient에게 amount 만큼 전송
approve가 선행되야함

approve : A -> B (100)
transferFrom : A -> C(100)  B가 실행

#### approve(address spender, uint256 amount)

자신의 토큰을 spender가 amount 만큼 사용 가능하게 변경, 
burnfrom과 transferFrom을 사용하기 위함

#### decreaseAllowance(address spender, uint256 subtractedValue)

자신이 spender 에게 부여해준 allowance를 subtractedValue 만큼 감소시킨다.

#### increaseAllowance(address spender, uint256 addedValue)

자신이 spender 에게 부여해준 allowance를 addedValue 만큼 증가시킨다.



### bunable

#### burn(uint256 amount)

자신의 토큰을 소각


#### burnFrom(address account, uint256 amount)

account의 토큰을 소각함, 소각을 진행하는 주체에게 approve를 원하는 양만큼 설정해주어야함

approve : A -> B (100)
burnFrom: B가 실행 account:A, amount: 100



### mintable

#### addMinter(address account)
account 에게 mint 권한을 부여, 토큰을 최소 생성하는 자는 자동으로 mint 권한을 부여받는다.

#### renounceMinter()
자신의 mint 권한을 반납
토큰을 최소 생성하고 생성한 주소로 해당 메소드를 호출하면 해당 토큰의 minter는 등록될 수 없음

#### mint(address account, uint256 amount)
account 에게 amount 만큼을 토큰을 생성




### pausable

#### addPauser(address account)

account에게 pausa 권한을 부여, , 토큰을 최소 생성하는 자는 자동으로 pausa 권한을 부여받는다.

#### renoncePauser()

자신의 pausa 권한을 반납
토큰을 최소 생성하고 생성한 주소로 해당 메소드를 호출하면 해당 토큰의 pauser 는 등록될 수 없음

#### pause()

transfer, transferFrom, approve, increaseAllowance, decreaseAllowance 기능을 막는다.
mint 는 동작 가능

#### unpause()

transfer, transferFrom, approve, increaseAllowance, decreaseAllowance 기능을 푼다.



## 기존 코인에 구현된 기능

- Tether USD (USDT)
  - **deprecate**
  - addBlackList - 블랙리스트 추가
  - removeBlackList - 블랙리스트 제거
  - destroyBlackFunds - 블랙리스트 주소 잔액 0만들기
  - setParams - newBasisPoints와 newMaxFee를 변경하는데 이것들이 무엇으르 하는지는 찾을 수 없음
  - issue - 토큰 전체량 증가
  - redeem - 토큰 소각
  - transferOwnership - 토큰 주인 변경
- BNB (BNB)
  - withdrawEther - ??
- Bitfinex LEO Token (LEO)
  - changeController - 토큰 주인 변경
  - createCloneToken - ??
  - generateTokens - 토큰 전체량 증가
  - **approveAndCall - ??**
  - destroyTokens - 토큰 소각
  - enableTransfer - 토큰 거래를 시작함(pasuse와 비슷)
- ChainLink Token (LINK)
  - **transferAndCall - ??**
- HuobiToken (HT)



> - 토큰을 관리하는 주소를 하나로만 만들어서 Owner로 사용하던지
>   오픈소스에 나오는것같이 권한별로 주소를 관리할 수 있게 사용할지 선택해야함

