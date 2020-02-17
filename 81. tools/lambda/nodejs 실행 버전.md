# nodejs 실행 버전



## 에러 상황

```javascript
{
    "errorType": "Error",
    "errorMessage": "The module '/var/task/node_modules/scrypt/build/Release/scrypt.node'\nwas compiled against a different Node.js version using\nNODE_MODULE_VERSION 59. This version of Node.js requires\nNODE_MODULE_VERSION 64. Please try re-compiling or re-installing\nthe module (for instance, using `npm rebuild` or `npm install`).",
    "stack": [
        "Error: The module '/var/task/node_modules/scrypt/build/Release/scrypt.node'",
        "was compiled against a different Node.js version using",
        "NODE_MODULE_VERSION 59. This version of Node.js requires",
        "NODE_MODULE_VERSION 64. Please try re-compiling or re-installing",
        "the module (for instance, using `npm rebuild` or `npm install`).",
        "    at Object.Module._extensions..node (internal/modules/cjs/loader.js:807:18)",
        "    at Module.load (internal/modules/cjs/loader.js:653:32)",
        "    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)",
        "    at Function.Module._load (internal/modules/cjs/loader.js:585:3)",
        "    at Module.require (internal/modules/cjs/loader.js:692:17)",
        "    at require (internal/modules/cjs/helpers.js:25:18)",
        "    at Object.<anonymous> (/var/task/node_modules/scrypt/index.js:3:20)",
        "    at Module._compile (internal/modules/cjs/loader.js:778:30)",
        "    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)",
        "    at Module.load (internal/modules/cjs/loader.js:653:32)",
        "    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)",
        "    at Function.Module._load (internal/modules/cjs/loader.js:585:3)",
        "    at Module.require (internal/modules/cjs/loader.js:692:17)",
        "    at require (internal/modules/cjs/helpers.js:25:18)",
        "    at Object.<anonymous> (/var/task/node_modules/scrypt.js/node.js:1:14)",
        "    at Module._compile (internal/modules/cjs/loader.js:778:30)"
    ]
}
```



## 원인

컴파일된 `NODE_MODULE_VERSION` (59) 과 필요한 `NODE_MODULE_VERSION`(64) 이 달라 발생하는 에러

`npm install` 명령어로 `node_module` 생성 시  필요한 `NODE_MODULE_VERSION`(64)와 맞추어 준다. 



### NODE_MODULE_VERSION

[NODE_MODULE_VERSION 확인 사이트](https://nodejs.org/ko/download/releases/)

설치 해야할 `NODE_MODULE_VERSION`을 확인 할 수 있다. 



람다 함수 생성 시 Runtime 함수를 설정하는 부분이 나온다. 
![1568030577503](images/nodejs%20%EC%8B%A4%ED%96%89%20%EB%B2%84%EC%A0%84/1568030577503.png)

 

예를들어 nodejs 8.10 를 선택하면 
해당 `NODE_MODULE_VERSION`(57)만 사용하여야 한다. 

nodejs 10.x 를 선택하면 `NODE_MODULE_VERSION`(64) 버전을 선택하여 사용한다. 



## node 버전 변경

```
sudo npm cache clean -f
sudo npm install -g n

nvm install v8.16.1
nvm list
nvm use v8.16.1
```

