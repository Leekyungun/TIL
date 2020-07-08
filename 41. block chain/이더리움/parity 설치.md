# parity 설치



### Build Dependencies
```shell
yum install libudev-devel
yum group install "Development Tools"
```



OpenEthereum은 빌드하기 위해 최신 stable 버전의  Rust가 필요하다.

```shell
curl https://sh.rustup.rs -sSf | sh
```



`clang`(>=9.0), `clang++`, `pkg-config`, `file`, `make`, `cmake` 패키지도 필요하다.

```shell
sudo yum -y install clang file make
```



cmake는 3.0 이상 버전이 필요하므로 따로 설치해준다.
https://cmake.org/download/ 릴리즈 다운로드 링크 주소를 복사하여 사용한다. 

```shell
sudo yum remove cmake

wget https://github.com/Kitware/CMake/releases/download/v3.18.0-rc3/cmake-3.18.0-rc3.tar.gz
tar -xvzf cmake-3.18.0-rc3.tar.gz 
cd cmake-3.18.0-rc3

./bootstrap --prefix=/usr/local
make
sudo make install
```



`rustup`을 설치하면 `perl`과 `yasm`도 설치하여야 한다. 

```shell
sudo yum -y install perl
sudo yum -y install yasm
```



## Build from Source Code

```shell
git clone https://github.com/openethereum/openethereum
cd openethereum

cargo build --release --features final
```

이렇게 실행하면 `./target/release` 아래 실행 파일이 생성된다. 



만약 cargo가 설치되지 않았다고 나오면  아래 명령어로 실행하면 된다.

```shell
~/.cargo/bin/cargo build --release --features final
```



컴파일 도중 에러가 나면 대부분은 rust의 버전이 낮기 때문이다. Rust의 버전을 올리고 다시 실행하라. 최신 stable 버전의 Rust설치하였으면 저장소를 정소하고 다시 빌드하여라. 

```shell
cargo clean
git checkout stable
```







참고 : https://github.com/openethereum/openethereum
https://openethereum.github.io/wiki/Setup

