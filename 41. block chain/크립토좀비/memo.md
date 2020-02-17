## Version Pragma

모든 솔리디티 소스코드는 `version pragma`로 시작됩니다. 이는 해당 코드가 사용하는 솔리디티 버전을 선언하는 것입니다. 소스코드의 버전을 선언하므로서 새로운 컴파일러 버전이 나와도 기존 코드가 에러나지 않도록 예방합니다. 

```
pragma solidity ^0.4.19;

contract HelloWorld{

}
```



## 상태 변수 & 정수

상태변수는 이더리움 블록체인에 기록되어 영구적으로 저장됩니다. 데이터베이스에 데이터를 기록하는것과 동일합니다. 

```
contract Example{
  uint myUnsignedInteger = 100;
}
```



### 부호 없는 정수 : uint

uint 자료형은 부호 없는 정수로, 값이 음수가 될 수 없습니다.(x >= 0)
음수를 사용할 경우 int 자료형을 사용합니다. 

> 솔리디티에서 uint는 uint256과 같습니다. 256 비트 부호 없는 정수형이라는 뜻입니다. uint8, uint16, uint32 등과 같이 uint를 더 적은 비트로 선언할 수도 있습니다. 특수한 경우를 제외하면 보통 uint를 사용합니다. 



## 수학 연산

솔리디티의 수학연산은 대부분의 프로그래밍 언어의 수학 연산과 동일합니다. 

- 덧셈 : x + y
- 뺼셈 : x - y
- 곱셈 : x * y
- 나눗셈 : x / y
- 나머지 : x % y
- 지수연산 : x ** y



## 구조체

여러 특성을 가진, 좀더 복잡한 자료형을 사용할 경우 구조체를 사용합니다.

```
struct Person{
  uint age;
  string name;
}
```

>  string 자료형 
> 임의의 길이를 가진 UTF-8 데이터를 저장합니다. ex) string greeting = "Hello world!"



## 배열

어떤 것의 모음집이 필요할 때 배열을 사용합니다. 

- 정적 배열
  - 원소를 담을 수 있는 크기를 미리 설정한 배열입니다. 
  - ```
    uint[2] fixedArray;
    ```
- 동적 배열
  - 고정된 크기가 없으며 계속 커질 수 있습니다. 
  - ```
    uint[] dynamicArray;
    ```

구조체도 배열로 생성할 수 있습니다. 

```
Person[] perple;
```

구조체를 동적으로 생성하면 데이터베이스처럼 컨트랙트에 구조화된 데이터를 저장 할 수 있습니다. 



### Public 배열

`public`으로 배열을 선언할 수 있습니다. 솔리디티는 이런 배열을 위해 `getter` 메소드를 자동적으로 생성합니다. 

```
Person[] public people;
```

다른 컨트랙트들이 이 배열을 읽을 수 있습니다. 배열을 수정할 수는 없습니다. 이는 컨트랙트에 공개 데이터를 저장할 때 유용한 패턴입니다. 



## 함수 선언

```
function eatHamburgers(string _name, uint _amount){

}
```

솔리디티에서 함수 선언은 위와 같이 합니다. 이 함수는 `eatHamburgers`라는 함수로, string과 uint 2개의 인자를 전달받고 있습니다. 함수의 내용은 비어있습니다. 

> 함수 인자명을 언더스코어(_)로 시작해서 전역 변수와 구별하는 것이 관례입니다.(의무는 아닙니다.) 

함수를 호출할때는 아래와 같이 사용합니다.

```
eatHamburgers("vitalik", 100)
```



## 구조체와 배열 활용하기

### 새로운 구조체 생성하기

새로운 Person을 생성하고 people 배열에 추가하는 방법을 살펴보겠습니다. 

```
struct Person{
  uint age;
  string name;
}

Person[] public people;

// 새로운 사람을 생성한다.
Person satoshi = Person(172, "Satoshi")

// 이 사람을 배열에 추가한다.
people.push(satoshi);

perple.push(Person(16, "Vitalik"));
```

`array.push()` 는 무언가를 배열의 끝에 추가해서 모든 원소가 순서를 유지하도록 해줍니다. 

```
uint[] numbers;
numbers.push(5);
numbers.push(10);
numbers.push(15);
//numbers 배열은 [5,10,15] 와 같다.
```



## Private / Public 함수

솔리디티에서 함수는 기본적으로 `public`으로 선언됩니다. 즉, 누구나(혹은 다른 어느 컨트랙트가) 우리 컨트랙트의 함수를 호출하고 코드를 실행할 수 있다는 의미입니다. 

이는 항상 바람직한 건 아닐 뿐더러, 우리 컨트랙트를 공격에 취약하게 만들 수 있습니다. 그러니 **기본적으로 함수를 `private`으로 선언하고, 공개할 함수만 `public`으로 선언**하는 것이 좋습니다. 

```
uint[] numbers;

function _addToArray(uint _number) private {
  numbers.push(_number);
}
```

private는 컨트랙트 내의 다른 함수들만이 이 함수를 호출하여 numbers 배열로 무언가를 추가할 수 있다는 것을 의미합니다. 위의 예시에서 볼 수 있듯이 private 키워드는 함수명 다음에 적고, 함수 인자명과 마찬가지로 private 함수명도 언더바(_)로 시작하는 것이 관례입니다. 



## 함수 더 알아보기

### 리턴값

함수에서 어떤 값을 리턴 받으려면 다음과 같이 선언해야 합니다. 

```
string greeting = "What's up dog";

function sayHello() public returns (string){
  return greeting;
}
```

솔리디티에서 함수 선언은 반환값 종류를 포함합니다. (위의 경우에는 string 입니다. ) 



### 함수 제어자

위에서 살펴 본 함수 sayHello()는 솔리디티에서 상태를 변화시키지 않습니다. 즉 어떤 값을 변경하거나 무언가를 쓰지 않습니다. 

이 경우에는 함수를 view 함수로 선언합니다. 이는 함수가 데이터를 보기만하고 변경하지 않는 다는 뜻입니다. 

```
function sayHello() public view returns(string){}
```

솔리디티는 `pure` 함수도 가지고 있는데, 이는 함수가 앱에서 어떤 데이터도 접근하지 않는 것을 의미합니다. 

```
function _multiply(uint a, uint b) private pure returns (uint){
  return a * b;
}
```

이 함수는 앱에서 읽는 것도 하지 않고, 다만 반환값이 함수에 전달된 인자값에 따라서 달라집니다. 이러한 경우에 함수를 `pure`로 선언합니다.

> 함수를 `pure`나 `view`로 언제 표시할지 기억하기 어려울 수 있습니다. 솔리디티 컴파일러는 어떤 제어자를 써야 하는지 경고 메시지를 통해 알려줍니다. 



## Keccak256과 형 변환

우리가 `_generateRandomDna` 함수의 반환값이 (반)랜덤인 `uint`가 되기를 원하면 어떻게 해야할까요?

이더리움은 SHA3의 한 버전인 `keccak256`을 내장 해시 함수로 가지고 있습니다. 해시함수는 기본적으로 입력스트링을 랜덤 256비트 16진수로 매핑합니다. 스트링에 약간의 변화라도 있으면 해시값은 크게 달라집니다. 

해시 함수는 이더리움에서 여러 용도로 활용되지만, 여기서는 의사 난수 발생기(pseudo-random number generator)로 이용됩니다. 

```
//6e91ec6b618bb462a4a6ee5aa2cb0e9cf30f7a052bb467b0ba58b8748c00d2e5
keccak256("aaaab");
//b1f078126895a1424524de5321b339ab00408010b7cf0e6ed451514981e58aa9
keccak256("aaaac");
```

입력값의 한 글자만 달라졌음에도 불구하고 반환값은 완전히 달라짐을 알 수 있습니다. 

> 블록체인에서 안전한 의사 난수 발생기는 매우 어려운 문제입니다. 위의 방법은 안전하지는 않지만, 좀비 DNA에 있어서 보안은 최우선순위가 아니니 우리의 목적에는 충분히 적합합니다. 



### 형변환

```
uint8 a = 5;
uint b = 6;

uint8 c = a * b; // a * b의 값이 uint를 반환하므로 에러 메시지가 발생
uint8 c = a * uint8(b); // 정상
```

위의 예시에서 a * b 는 `uint`를 반환하지만 우리는 이 반환값을 uint8에 저장하려고 하니 잠재적으로 문제를 야기할 수 있습니다. 반환값을 uint8 으로 형 변환하여도 코드가 제대로 작동하고 컴파일러도 에러 메시지를 주지 않습니다. 