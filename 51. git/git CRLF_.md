익히 알다시피 Windows 에서는  line ending으로 CR(Carriage-Return, \r)과 LF(Line Feed, \n)을 사용하고 Unix 나 Mac OS 는 LF 만 사용한다.

이는 상당히 골치아픈 문제를 발생시킨다. 실제 코드는 변경된 게 없는데 소스의 CR/LF 때문에 변경으로 착각하여 commit 을 하게 될 수 있으며 변경 로그를 보거나 merge 마다 문제가 될 소지가 있다.

이런 문제를 방지하기 위해 OS 가 달라도 문제가 없도록 crlf 처리 방법을 결정해야 한다.





협업할 때 겪는 소스 포맷(Formatting)과 공백 문제는 미묘하고 난해하다. 동료 사이에 사용하는 플랫폼이 다를 때는 특히 더 심하다. 다른 사람이 보내온 Patch는 공백 문자 패턴이 미묘하게 다를 확률이 높다. 편집기가 몰래 공백문자를 추가해 버릴 수도 있고 크로스-플랫폼 프로젝트에서 윈도 개발자가 줄 끝에 CR(Carriage-Return) 문자를 추가해 버렸을 수도 있다. Git에는 이 이슈를 돕는 몇 가지 설정이 있다.



core.autocrlf

윈도에서 개발하는 동료와 함께 일하면 줄 바꿈(New Line) 문자에 문제가 생긴다. **윈도는 줄 바꿈 문자로 CR(Carriage-Return)과 LF(Line Feed) 문자를 둘 다 사용하지만, Mac과 Linux는 LF 문자만 사용한다.** 아무것도 아닌 것 같지만, 크로스 플랫폼 프로젝트에서는 꽤 성가신 문제다.



Git은 커밋할 때 자동으로 CRLF를 LF로 변환해주고 반대로 Checkout할 때 LF를 CRLF로 변환해 주는 기능이 있다. core.autocrlf 설정으로 이 기능을 켤 수 있다. 윈도에서 이 값을 true로 설정하면 Checkout할 때 LF 문자가 CRLR 문자로 변환된다:



$ git config --global core.autocrlf true

줄 바꿈 문자로 LF를 사용하는 Linux와 Mac에서는 Checkout할 때 Git이 LF를 CRLF로 변환할 필요가 없다. 게다가 우연히 CRLF가 들어간 파일이 저장소에 들어 있어도 Git이 알아서 고쳐주면 좋을 것이다. core.autocrlf 값을 input으로 설정하면 커밋할 때만 CRLF를 LF로 변환한다:



$ git config --global core.autocrlf input

이 설정을 이용하면 윈도에서는 CRLF를 사용하고 Mac, Linux, 저장소에서는 LF를 사용할 수 있다.



윈도 플랫폼에서만 개발하면 이 기능이 필요 없다. 이 옵션을 false라고 설정하면 이 기능이 꺼지고 CR 문자도 저장소에도 저장된다:



$ git config --global core.autocrlf false

core.whitespace

Git에는 공백 문자를 다루는 방법으로 네 가지가 미리 정의돼 있다. 두 가지는 기본적으로 켜져 있지만 끌 수 있고 나머지 두 가지는 꺼져 있지만 켤 수 있다.



먼저 기본적으로 켜져 있는 것을 살펴보자. trailing-space는 각 줄 끝에 공백이 있는지 찾고 space-before-tab은 모든 줄 처음에 tab보다 공백이 먼저 나오는지 찾는다.



기본적으로 꺼져 있는 나머지 두 개는 indent-with-non-tab과 cr-at-eol이다. intent-with-non-tab은 tab이 아니라 공백 8자 이상으로 시작하는 줄이 있는지 찾고 cr-at-eol은 줄 끝에 CR 문자가 있어도 괜찮다고 Git에 알리는 것이다.



core.whitespace 옵션으로 이 네 가지 방법을 켜고 끌 수 있다. 설정에서 해당 옵션을 빼버리거나 이름이 -로 시작하면 기능이 꺼진다. 예를 들어, 다른 건 다 켜고 cr-at-eol 옵션만 끄려면 아래와 같이 설정한다:



$ git config --global core.whitespace \

​    trailing-space,space-before-tab,indent-with-non-tab

git diff 명령을 실행하면 Git은 이 설정에 따라 검사해서 컬러로 표시해준다. 그래서 좀 더 쉽게 검토해서 커밋할 수 있다. git apply 명령으로 Patch를 적용할 때도 이 설정을 이용할 수 있다. 아래처럼 명령어를 실행하면 해당 Patch가 공백문자 정책에 들어맞는지 확인할 수 있다:



$ git apply --whitespace=warn <patch>

아니면 Git이 자동으로 고치도록 할 수 있다:



$ git apply --whitespace=fix <patch>

이 옵션은 git rebase 명령에서도 사용할 수 있다. 공백 문제가 있는 커밋을 서버로 Push하기 전에 --whitespace=fix 옵션을 주고 Rebase하면 Git은 다시 Patch를 적용하면서 공백을 설정한 대로 고친다.





https://handam.tistory.com/127