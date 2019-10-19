# 비트코인

## 1. HandsOn 소개

비트코인 RegTest망을 이용해 비트코인의 동작원리를 실습한다.

<br><br>
## 2. 실습순서
 - VirtualBox 설치 및 환경 설정
 - 비트코인 설치(RegTest)
 - 비트코인 실습(bitcoin-qt, bitcoind, bitcoin-cli)

<br><br>
## 3. 준비환경
 - 개인 Desktop 준비
 - (Optional) Putty(윈도우 사용자) / iterm(Mac 사용자<br>
 - (Optional) FileZilla
 - VirtualBox 설치 및 환경 설정
 - Linux OS(Ubuntu 18.04.2 LTS) 설치
<br><br>


<br><br>
## 4. Getting Started
### 4.1 VirtualBox 설치 및 환경 설정
// To-Do
<br>

### 4.2 비트코인 Core 다운로드
- Ubuntu 접속
- FireFox 브라우저 열기
- https://bitcoin.org/en/download 접속
- Linux용 Bitcoin Core 다운로드
```
위 방법이 안될 경우
$) curl -O https://bitcoin.org/bin/bitcoin-core-0.18.1/bitcoin-0.18.1-x86_64-linux-gnu.tar.gz
```
<br>

### 4.3 비트코인 Core 압축풀기
```
$) tar -xvzf bitcoin-0.18.1-x86_64-linux-gnu.tar.gz
```
<br>

### 4.4 비트코인 실행을 위한 권한 설정 및 절대경로 지정
```
$) sudo install -m 0755 -o root -g root -t /usr/local/bin bitcoin-0.18.1/bin/*
```
<br>

### 4.5 비트코인 실행하기
#### - bitcoin-qt 또는 bitcoind를 이용해 비트코인 네트워크를 구동


#### 4.5.1 bitcoin-qt :  크로스 플랫폼 애플리케이션 / GUI Interface 무료 툴킷<br>
```
$)./bitcoin-qt
```

#### 4.5.2 bitcoind : 개발자 및 운영자를 위한 블록체인 네트워크
- bitcoin 서비스 켜기(운영망)
```
$) bitcoind -daemon
```

- bitcoin 서비스 확인
```
$) ps -ef | grep bitcoin
$) netstat -anp | grep 8332
$) watch -n 1 du .bitcoin
```

- bitcoin 서비스 중지
```
$) bitcoin-cli stop
```
<br><br>

#### 잠깐! 비트코인은 어디에 연결되어 블록을 받아오는 것일까?
https://github.com/bitcoin/bitcoin/blob/4b51ed89cfce9870a20d75001fae3b68ac1dfd86/src/chainparams.cpp

1. Seed 서버가 랜덤으로 Node IP(Public) 제공(IP가 변경되는 주기는 몇초 이상) 
$) dig seed.bitcoinstats.com +short

2. 오프라인일 경우 캐쉬


#### 비트코인 노드의 위치를 확인하기
https://bitnodes.earn.com/#join-the-network







