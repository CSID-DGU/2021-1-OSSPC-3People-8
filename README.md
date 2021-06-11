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

![image](https://user-images.githubusercontent.com/65498159/121725594-6b09d600-cb24-11eb-9baa-09985d28eaef.png)
 - 화살표 상하 키로 메뉴 커서를 움직일 수 있습니다.
 - 엔터 키로 메뉴에 들어가고 나갈 수 있습니다.
 - 마우스로 화면 하단의 CO-OP 버튼을 누르면 협동모드로 이동합니다. PVP 버튼을 누르면 PVP모드로 이동합니다.
 - 로그인(LOGIN)을 눌러 기존 계정에 로그인 할 수 있습니다.
 - 계정 생성(CREATE ACCOUNT)을 눌러 새 계정을 만들 수 있습니다. 아이디는 4글자, 비밀번호는 3글자 까지 가능합니다.
 - 로그인 후 업적(ACHIEVEMENTS)에서 들어가서 본인의 업적을 확인할 수 있습니다. 업적은 미사일을 발사한 횟수인 shoot과 적을 명중한 횟수인 kill로 이루어져있습니다. 10회, 100회, 1000회를 달성할 때마다 뱃지를 획득할 수 있습니다.
 - 로그인 후 최고 점수(HIGH SCORES)에서 서버에 저장된 다른 사람들의 최고 기록을 볼 수 있습니다. 최고 기록 옆에는 유저가 획득한 업적 뱃지도 함께 표시됩니다.
![image](https://user-images.githubusercontent.com/65498159/121725628-7a891f00-cb24-11eb-9d76-d5d3c8904cfb.png)
 - 음악(MUSIC)과 효과음(SOUND FX)을 켜거나 끌 수 있습니다.
 - 언어(LANGUAGE)를 영어와 한국어 중 선택할 수 있습니다.

### Game
#### 1. Basic Rules
 - 우주선으로 미사일을 쏘아 적(외계인)을 격추하여 점수를 얻는 게임입니다.
 - 화살표 키로 우주선![ship](https://user-images.githubusercontent.com/65498159/121725939-d94e9880-cb24-11eb-891f-0734458abf66.png)을 움직일 수 있습니다.
 - 스페이스키로 미사일![missile](https://user-images.githubusercontent.com/65498159/121725969-e23f6a00-cb24-11eb-9242-7e2bd8e6b62f.png)을 발사하여 적을 무찌를 수 있습니다.
 - b키로 폭탄![bomb_powerup](https://user-images.githubusercontent.com/65498159/121726003-ec616880-cb24-11eb-802d-f5d71eae7285.png)을 사용할 수 있습니다.
 - 방패![shield_powerup](https://user-images.githubusercontent.com/65498159/121726056-fd11de80-cb24-11eb-98c4-1566acd989bd.png), 폭탄![bomb_powerup](https://user-images.githubusercontent.com/65498159/121726003-ec616880-cb24-11eb-802d-f5d71eae7285.png), 더블 미사일![doublemissile_powerup](https://user-images.githubusercontent.com/65498159/121726123-174bbc80-cb25-11eb-8dff-aa00d3929be2.png) 아이템이 랜덤으로 드랍됩니다. 방패는 적과 충돌을 1회 무효화합니다. 더블미사일 아이템은 잠깐동안 미사일이 2배로 발사되게 합니다.
 - 외계인은 색깔별로 서로 다른 이동패턴을 가지고 있으며, 격추하였을 때 얻을 수 있는 점수가 다릅니다. 
![image](https://user-images.githubusercontent.com/65498159/121726665-d43e1900-cb25-11eb-8862-d10e37284723.png)
 - 적을 많이 무찌르면 Wave가 증가합니다. Wave 증가 카운트다운에서 i키를 누르면 상점에 들어갈 수 있습니다.
 - 상점에서는 게임 내에서 드랍되는 코인으로 아이템을 구매할 수 있습니다.
![image](https://user-images.githubusercontent.com/65498159/121726898-20895900-cb26-11eb-9884-35af8f9efc04.png)

#### 2. Co-op Mode
![image](https://user-images.githubusercontent.com/65498159/121230557-57633300-c8ca-11eb-8366-e74deafe9fba.png)
 - 게임 화면에 또 하나의 우주선이 추가됩니다. 우주선2(green)는 w/a/s/d키로 움직일 수 있으며, v로 미사일을 발사하고 q로 폭탄을 사용합니다.
 - 협동 모드에서는 목숨과 폭탄을 공유합니다.
 - 협동 모드에서는 특별한 아이템인 팀방패가 드랍됩니다. 팀방패는 한 명이 획득하면 다른 한명에게도 적용되는 방패입니다.

#### 3. PVP Mode
![image](https://user-images.githubusercontent.com/65498159/121230445-3995ce00-c8ca-11eb-9a0f-2829d4692897.png)
 - PVP 모드에서는 두 명의 유저가 점수를 경쟁합니다. 우주선2의 조작 방법은 협동 모드와 같습니다.
 - PVP 모드에서는 특별한 아이템인 dist가 드랍됩니다. dist를 먹으면 잠시동안 상대방 화면을 안보이게 만들어 상대를 방해할 수 있습니다.
 - 게임 시작 전 L키를 누르면 플레이어 화면 위치를 바꿀 수 있습니다.

# Requirements
 - OS: Ubuntu 20.04
 - Python >= 3.6
 - pygame == 2.0.1 
 - grequests
