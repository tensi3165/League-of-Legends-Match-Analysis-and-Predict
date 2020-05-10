# League of legend Winner team predict to Using Riot API

> 2019.07.02-2019.11.12 데이터 분석 개인 프로젝트 리메이크

A project to collect league-of-legend game records to analyze the factors that affect victory and to predict winning rates based on real-time score fluctuations.

리그 오브 레전드 경기 기록을 수집하고, 가공하여 승률에 영향을 주는 요인 분석과 실시간 스코어 변동 따른 승률 예측 / 전적 피드백 프로젝트

![image](https://i.imgur.com/8YdHEAB.jpg)

## 프로젝트 개요

많은 사람이 리그 오브 레전드, 롤을 즐기고 나 또한 이 게임을 매우 좋아하고 즐겨한다. 어릴때부터 친구들과 랭크 경쟁을 하면서 롤을 잘하고 싶었다.

나는 롤을 시즌4, 2014년부터 해온 흔히 말하는 골수 유저인데 티어대가 실버, 골드(상위 30%-40%)에 머물며 매 시즌마다 크게 향상이 없었다. 오브젝트, KDA, 등등 게임 내의 수많은 지표를 보면서 피드백을 해야 승률과 티어가 오르는데 프로도 아니고 개인들이 어디서 객관적인 피드백을 받을 수 있을까.
예를 들어 친구들은 내가 게임의 후반 운영을 할 줄 모른다고 하는데, 정확하게 무엇을 해라 등이 아닌 추상적인 말로 피드백을 한다. 

위의 문제는 나 뿐만이 아니라 게임을 하는 모두가 겪고 자신의 플레이를 객관적으로 분석해주길 바란다. 하지만 프로팀이 아닌 일반인으로서는 객관적인 분석을 받기 어렵다. (프로팀은 코치나, 스태프가 전문적인 분석과 피드백을 지원해준다.)

부산대학교 정보컴퓨터공학부 학술동아리 Untoc에서 개발하는 [E-sport platform](https://github.com/tensi3165/Esports_platform) 은 사람들이 쉽게 리그를 열고 참가할 수 있게끔 대회 관리 뿐만 아니라 전적 관리도 지원하는데, 해당 플랫폼이 아마추어, 일반인 대상이라 전적 관리에서 더 나아가 코치 없이도 전적을 분석하여 피드백을 제공하는 알고리즘의 필요성을 느꼈다.

이를 해결하기 위한 방안으로 자동화 데이터 분석과 머신러닝을 통한 피드백이 있지만, 이를 위해서는 많은 데이터가 필요하다.

현재 E-sports 플랫폼이 크롤링하는 롤 전적 사이트인 OP.GG는 RIOT(롤 개발사)에서 제공하는 API를 이용해 유저의 전적과 게임의 결과를 표시해준다. 이는 Riot-API를 사용하면 경기 전체의 RAW 데이터를 얻을 수 있음을 뜻한다.

따라서, Riot-API를 이용한 개인 프로젝트로 신뢰성 있고 좋은 경기력을 가진 천상계(게임의 최고위 티어인 챌린저, 그랜드마스터, 마스터)의 전적을 수집한다.
이후 데이터 분석과 머신러닝 모델링을 진행해 천상계의 게임은 어떻게 진행되는지, 승률에 미치는 중요한 지표와 해당 지표에 따른 승률을 예측해보고, 전적을 피드백하는 모델을 개발하여 플랫폼 업그레이드와 , 사람들의 롤 실력 향상에 도움이 되었으면 좋겠다.

## 프로젝트 구성

모든 프로젝트는 Jupyter notebook으로 진행되어 실행결과가 표시되어 있음

또한 ipynb 파일에 세세한 설명과 정리를 해두었으며 데이터만 준비되면 모든 프로젝트가 실행가능함.

### 1. DATA ETL(Extract, Transform, Load) 

> 2019.07.02 - 2019.08.23

RIOT에서 제공하는 API를 이용해 데이터를 수집하고 가공하고, 파일화하여 저장한다.

### 2. Match Data EDA(Exploratory Data Analysis) 

> 2019.08.24 - 2019.08.25

모은 데이터를 분석에 용이하도록 전처리하고, 승패에 영향이 가는 변수를 분석한다.

### 3. Feature Engineering & Modeling

> 2019.08.26 - 2019.09.01

EDA를 통해 얻은 정보로 특성 공학을 진행하고,

승패 예측을 진행할 모델을 구축한 뒤 튜닝을 통해 예측의 정확도를 올려 신뢰성 있는 모델을 만든다.

회귀 분석과 특성 중요도 시각화로 모델을 분석하고, 해당 지표가 실제로 승률에 영향을 미치는가 확인.

### 4.Project Analytics & Result 

> 2019.09.03 - 2019.11.12( 랭크 게임 종료시까지 )

프로젝트 마무리와 해당 피드백을 중심으로 게임을 하고 달성한 티어대 기록.

## 업데이트 내역

* (2020.03.20)
  
  DATA ETL 데이터 업데이트

* (2020.04.10)
  
  DATA EDA코드 업데이트

* (2020.04.28)

  Repository 재생성, 정리

* (2020.05.09)

  DATA EDA코드 결과 정리
  
## ALL DATA SET LINK

모든 데이터 셋은 Kaggle 에 공개하였음.

<https://www.kaggle.com/shinbg/lol-classic-rank-game-datakrtop-3-tier>

코드 복제와 데이터 셋 사용은 자유이며 다른 사람도 유용한 인사이트를 도출해 실버 골드를 탈출하길 바람.
