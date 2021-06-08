# 2021-1-OSSPC-3People-8
- Shooting game
- 8조 3인분(김태환, 박재민, 배유진)

## Original source
https://github.com/jpritcha3-14/shooting-game

## 개발환경
 - OS : Ubuntu  
 - 툴 : VSCode  
 - 언어: Python3.6  
 - 웹서버: AWS

## 타임라인
![image](https://user-images.githubusercontent.com/65498159/121224377-74483800-c8c3-11eb-9f9a-b21bff99597e.png)

## 실행 방법
pip3가 설치되어있지 않다면, pip3를 설치합니다. 
```
$ sudo apt install python3-pip
```
pygame과 grequests 설치 후 저장소를 clone합니다. 
```
$ pip3 install pygame
$ pip3 install grequests 
$ git clone https://github.com/CSID-DGU/2021-1-OSSPC-3People-8.git
```
main.py를 실행합니다.
```
$ cd 2021-OSSP-3People-8
$ python3 main.py
```

## Game Controls
### Menus
![image](https://user-images.githubusercontent.com/65498159/121228285-875d0700-c8c7-11eb-802c-e5fe83f12206.png)
 - w/s로 메뉴 커서를 움직일 수 있습니다.
 - 마우스로 화면 하단의 CO-OP 버튼을 누르면 협동모드로 이동합니다. PVP 버튼을 누르면 PVP모드로 이동합니다.
 - 로그인을 눌러 기존 계정에 로그인 할 수 있습니다.
 - 계정 생성을 눌러 새 계정을 만들 수 있습니다. 아이디는 4글자, 비밀번호는 3글자 까지 가능합니다.
 - 로그인 후 업적창에 들어가서 본인의 업적을 확인할 수 있습니다.
 - 로그인 후 최고 점수에서 서버에 저장된 다른 사람들의 최고 기록을 볼 수 있습니다.
 - 음악과 효과음을 켜거나 끌 수 있습니다.
 - 언어를 영어와 한국어 중 선택할 수 있습니다.

### Game
#### 1. Basic Rules
 - 화살표 키로 우주선을 움직일 수 있습니다.
 - 스페이스키로 미사일을 발사하여 적을 무찌를 수 있습니다.
 - b키로 폭탄을 사용할 수 있습니다.
 - 적을 많이 무찌르면 Wave가 증가합니다. Wave 증가 카운트다운에서 i키를 누르면 상점에 들어갈 수 있습니다.
 - 상점에서는 게임 내에서 드랍되는 코인으로 아이템을 구매할 수 있습니다.

#### 2. Co-op Mode
![image](https://user-images.githubusercontent.com/65498159/121228737-1538f200-c8c8-11eb-9657-17fa2d0c01a9.png)
 - 게임 화면에 또 하나의 우주선이 추가됩니다. 우주선2(green)는 w/a/s/d키로 움직일 수 있으며, v로 미사일을 발사하고 q로 폭탄을 사용합니다.
 - 협동 모드에서는 목숨과 폭탄을 공유합니다.
 - 협동 모드에서는 특별한 아이템인 팀방패가 드랍됩니다. 팀방패는 한 명이 획득하면 다른 한명에게도 적용되는 방패입니다.

#### 3. PVP Mode
![image](https://user-images.githubusercontent.com/65498159/121228796-271a9500-c8c8-11eb-9896-618c241ec8fa.png)
 - PVP 모드에서는 두 명의 유저가 점수를 경쟁합니다. 우주선2의 조작 방법은 협동 모드와 같습니다.
 - PVP 모드에서는 특별한 아이템인 dist가 드랍됩니다. dist를 먹으면 잠시동안 상대방 화면을 안보이게 만들어 상대를 방해할 수 있습니다.
 - 게임 시작 전 L키를 누르면 플레이어 화면 위치를 바꿀 수 있습니다.

# Requirements
 - OS: Ubuntu 20.04
 - Python >= 3.6
 - pygame == 2.0.1 
 - grequests
