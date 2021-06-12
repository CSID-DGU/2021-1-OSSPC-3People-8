# 2021-1-OSSPC-3People-8
- Shooting game
- 8조 3인분(김태환, 박재민, 배유진)

## Original source
https://github.com/jpritcha3-14/shooting-game

## Requirements
 - OS: Ubuntu 20.04
 - Python >= 3.6
 - pygame == 2.0.1 
 - grequests

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
![image](https://user-images.githubusercontent.com/65498159/121736179-300e9f00-cb32-11eb-8a62-4f0304338d4c.png)
### Menus
![image](https://user-images.githubusercontent.com/65498159/121725594-6b09d600-cb24-11eb-9baa-09985d28eaef.png)
 - 화살표 상하 키로 메뉴 커서를 움직일 수 있습니다.
 - 엔터 키로 메뉴에 들어가고 나갈 수 있습니다.
 - 마우스로 화면 하단의 ![mode1](https://user-images.githubusercontent.com/65498159/121728766-a73f3580-cb28-11eb-8552-2e9111c7ee4b.png) 버튼을 누르면 협동모드로 이동합니다. ![mode2](https://user-images.githubusercontent.com/65498159/121728804-b3c38e00-cb28-11eb-9707-56cd3dbb09bb.png) 버튼을 누르면 PVP모드로 이동합니다.
 - 협동 모드와 PVP모드로 이동한 상태에서 ![main](https://user-images.githubusercontent.com/65498159/121728866-c6d65e00-cb28-11eb-9427-f208d943c5b6.png) 버튼을 누르면 다시 기본 모드로 돌아옵니다.
 - 로그인(LOGIN)을 눌러 기존 계정에 로그인 할 수 있습니다.
 - 계정 생성(CREATE ACCOUNT)을 눌러 새 계정을 만들 수 있습니다. 아이디는 4글자, 비밀번호는 3글자 까지 가능합니다.
 - 로그인 후 업적(ACHIEVEMENTS)에서 들어가서 본인의 업적을 확인할 수 있습니다. 업적은 미사일을 발사한 횟수인 shoot과 적을 명중한 횟수인 kill로 이루어져있습니다. 10회, 100회, 1000회를 달성할 때마다 뱃지를 획득할 수 있습니다.
 - 로그인 후 최고 점수(HIGH SCORES)에서 서버에 저장된 다른 사람들의 최고 기록을 볼 수 있습니다. 최고 기록 옆에는 유저가 획득한 업적 뱃지도 함께 표시됩니다.
![image](https://user-images.githubusercontent.com/65498159/121725628-7a891f00-cb24-11eb-9d76-d5d3c8904cfb.png)
 - 음악(MUSIC)과 효과음(SOUND FX)을 켜거나 끌 수 있습니다.
 - 언어(LANGUAGE)를 영어와 한국어 중 선택할 수 있습니다.
 - 로그아웃(LOGOUT)을 눌러 로그아웃 할 수 있습니다.

### Game
#### 1. Basic Rules
 - 우주선으로 미사일을 쏘아 적(외계인)을 격추하여 점수를 얻는 게임입니다.
 - 적과 우주선이 충돌하면 우측 상단의 life가 줄어듭니다. life 3개가 모두 사라지면 게임이 종료됩니다.
 - 화살표 키로 우주선![ship](https://user-images.githubusercontent.com/65498159/121725939-d94e9880-cb24-11eb-891f-0734458abf66.png)을 움직일 수 있습니다.
 - 스페이스키로 미사일![missile](https://user-images.githubusercontent.com/65498159/121725969-e23f6a00-cb24-11eb-9242-7e2bd8e6b62f.png)을 발사하여 적을 무찌를 수 있습니다.
 - b키로 폭탄![bomb_powerup](https://user-images.githubusercontent.com/65498159/121726003-ec616880-cb24-11eb-802d-f5d71eae7285.png)을 사용할 수 있습니다.
 - 게임 도중 p키를 누르면 일시정지 할 수 있습니다.
 - 방패![shield_powerup](https://user-images.githubusercontent.com/65498159/121726056-fd11de80-cb24-11eb-98c4-1566acd989bd.png), 폭탄![bomb_powerup](https://user-images.githubusercontent.com/65498159/121726003-ec616880-cb24-11eb-802d-f5d71eae7285.png), 더블 미사일![doublemissile_powerup](https://user-images.githubusercontent.com/65498159/121726123-174bbc80-cb25-11eb-8dff-aa00d3929be2.png) 아이템이 랜덤으로 드랍됩니다. 방패는 적과 충돌을 1회 무효화합니다. 더블미사일 아이템은 잠깐동안 미사일이 2배로 발사되게 합니다.
 - 외계인은 색깔별로 서로 다른 이동패턴을 가지고 있으며, 격추하였을 때 얻을 수 있는 점수가 다릅니다. 
![image](https://user-images.githubusercontent.com/65498159/121726665-d43e1900-cb25-11eb-8862-d10e37284723.png)
 - 적을 많이 무찌르면 Wave가 증가합니다. Wave 증가 카운트다운에서 i키를 누르면 상점에 들어갈 수 있습니다.
 - 상점에서는 게임 내에서 드랍되는 코인![coin_powerup](https://user-images.githubusercontent.com/65498159/121728628-7f4fd200-cb28-11eb-8227-7787abc35cd0.png)![coin2_powerup](https://user-images.githubusercontent.com/65498159/121728678-8d9dee00-cb28-11eb-8e28-e4bc4d864a55.png)으로 아이템을 구매할 수 있습니다.
![image](https://user-images.githubusercontent.com/65498159/121726898-20895900-cb26-11eb-9884-35af8f9efc04.png)

#### 2. Co-op Mode
![image](https://user-images.githubusercontent.com/65498159/121728072-bbcefe00-cb27-11eb-93f0-1b65f9a16a07.png)
 - 협동 모드는 두 명의 플레이어가 한 화면 안에서 협동하는 모드입니다.
 - 게임 화면에 또 하나의 우주선![ship2](https://user-images.githubusercontent.com/65498159/121728191-e4ef8e80-cb27-11eb-9e41-255b8f886181.png)이 추가됩니다. 이 우주선은 w/a/s/d키로 움직일 수 있으며, v로 미사일을 발사하고 q로 폭탄을 사용합니다.
 - 빨간색 우주선![ship](https://user-images.githubusercontent.com/65498159/121729672-b377c280-cb29-11eb-9b75-d5f9ac353533.png)의 조작 방법은 기본 모드와 같습니다.
 - 협동 모드에서는 목숨과 폭탄을 공유하고, 두 플레이어가 얻은 점수는 합산됩니다.
 - 협동 모드에서는 특별한 아이템인 팀방패![teamshield_powerup](https://user-images.githubusercontent.com/65498159/121728430-38fa7300-cb28-11eb-82d3-cdf34be5d296.png)가 드랍됩니다. 팀방패는 한 명이 획득하면 다른 한명에게도 적용되는 방패입니다.
 - 협동 모드에서 로그인을 진행하면 로그인 창이 두 번 나타납니다. 이후 업적과 최고기록에서도 두 명이 세운 기록으로 표시됩니다.
![image](https://user-images.githubusercontent.com/65498159/121728575-70691f80-cb28-11eb-93c1-2874826a9d6c.png)

#### 3. PVP Mode
![image](https://user-images.githubusercontent.com/65498159/121729401-63006500-cb29-11eb-9777-987ab6c0ae26.png)
 - PVP 모드는 두 명의 플레이어가 경쟁하는 모드입니다. 적과 충돌하지 않고 더 오래 살아남는 쪽이 승리합니다.
 - 플레이어 1은 화살표키로 우주선을 움직이고 스페이스키로 미사일을 발사, b로 폭탄을 사용할 수 있습니다.
 - 플레이어 2는 w/a/s/d키로 우주선을 움직이고 v로 미사일을 발사, q로 폭탄을 사용할 수 있습니다.
 - 게임 시작 전 L키를 누르면 플레이어 화면 위치와 우주선 색을 바꿀 수 있습니다. U키를 누르면 게임을 시작합니다.
![image](https://user-images.githubusercontent.com/65498159/121730113-3b5dcc80-cb2a-11eb-9c4b-6234dca87ae1.png)
 - PVP 모드에서는 특별한 방해 아이템![dist_powerup](https://user-images.githubusercontent.com/65498159/121729868-e8841500-cb29-11eb-9a00-6cf048e184cf.png)이 드랍됩니다. 방해 아이템을 먹으면 잠시동안 상대방 화면을 안보이게 만들어 상대를 방해할 수 있습니다.
 - PVP 모드에서는 최고기록과 업적, 로그인 및 로그아웃을 이용할 수 없습니다.

## 프로젝트 진행
### 개발환경
 - OS : Ubuntu  
 - 툴 : VSCode  
 - 언어: Python
 - 웹서버: AWS

### 타임라인
![image](https://user-images.githubusercontent.com/65498159/121224377-74483800-c8c3-11eb-9f9a-b21bff99597e.png)

### Git 협업 규칙
 - 팀 저장소를 fork한 개인 저장소에서 팀원들이 각자 코드를 작성한 뒤 ```pull request``` 
 - 팀장이 확인 후 merge 및 충돌이 있는 코드들을 병합 
 - 코드 간 충돌을 최대한 막기 위해 pull request 후에는 카톡방을 통해 공지 
 - 매주 주말에는 개인 fork를 업데이트하고(```fetch upstream```), 로컬 저장소를 동기화(```git pull```) 

### 코드 구성
```
main.py(38 lines): 모드와 화면 크기를 관리하는 코드로 게임 플레이를 위해 실행해야 하는 코드 
shooting_game.py(1407 lines): 게임의 기본 모드를 실행하는 코드
mode_one.py(1407 lines): 협동모드를 실행하는 코드
mode_two.py(958 lines): PVP모드를 실행하는 코드
load.py(38 lines): 게임 내의 이미지와 음악을 로드하는 함수를 선언하는 코드
sprites.py(624 lines): 게임 내에서 사용되는 객체를 정의하는 코드
database.py (61 lines): 하이스코어를 저장하는 hiScore.db를 생성하고, db에서 인게임으로 점수를 불러오는 코드
server_code.txt(189 lines): 서버에 업로드한 코드를 txt형식으로 저장해 놓은 파일(실제 코드는 AWS EC2에서 구동 중)
```

### 서버
