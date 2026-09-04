# Jongha Lee

**사람 곁에서 움직이는 로봇의 소프트웨어를 만듭니다.**

시각장애인 안내 로봇과 전동휠체어 자동 주차를 실제 로봇에서 개발해 왔습니다.
모듈을 각각 만드는 것보다 합쳤을 때 깨지는 지점을 찾는 일, 그리고 사용자가 실패를 볼 수 없는 환경에서 안전하게 실패하는 방법을 주로 다룹니다.

![ROS2](https://img.shields.io/badge/ROS2-Humble-22314E?logo=ros&logoColor=white)
![Nav2](https://img.shields.io/badge/Nav2-AMCL%20%7C%20SLAM-1f6feb)
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-00FFFF?logo=yolo&logoColor=black)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?logo=opencv&logoColor=white)
![Jetson](https://img.shields.io/badge/Jetson%20Nano-76B900?logo=nvidia&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00979D?logo=arduino&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)

[bell-ha.github.io](https://bell-ha.github.io) &nbsp;·&nbsp; jongha8273@gmail.com

단국대학교 배리어프리 ICT기술 연구센터(ITRC) 학부연구생 &nbsp;`2025.12 ~ `
정부지원 연구센터 과제로 시각장애인 안내 로봇과 전동휠체어 자동 주차 시스템을 개발하고 있습니다.

<br>

## Robotics

### [시각장애인 실내 안내 로봇](https://github.com/bell-ha/visually-impaired-navigation-robot)

`단독 개발` &nbsp;`ITRC 과제` &nbsp;`ROS2 Humble · Nav2 · AMCL · LiDAR · RealSense`

상용 로봇 플랫폼(Hello Robot Stretch SE3) 위에, 플랫폼이 제공하지 않는 엘리베이터 자율 탑승을 소프트웨어로 구현했습니다.
로봇과 엘리베이터의 연동은 승강기 제조사와 제작 연도마다 제어 방식이 달라 쓸 수 있는 표준 API가 없습니다.
그래서 연동 규격에 기대지 않고, 그리퍼 카메라로 버튼을 직접 인식해 누르는 방식으로 풀었습니다.

사용자가 로봇의 실패를 볼 수 없다는 점이 이 프로젝트의 가장 큰 제약이었습니다.
음성 명령 해석에는 LLM을 쓰되 실제 이동을 확정하는 것은 사용자가 누르는 물리 버튼으로 두었고,
겉으로 드러나지 않는 실패 **27건**을 목록으로 만들어 안전 항목부터 해결하고 있습니다.

**1층에서 5층까지 층간 이동을 end-to-end로 완주**했고(정상 시나리오 1회), ITRC 인재양성대전에서 시연했습니다.

[1층 → 5층 주행 영상](https://www.youtube.com/watch?v=3vwIzmuHD_s) &nbsp;·&nbsp; [ITRC 시연 영상](https://www.youtube.com/watch?v=SAGndz1JyPY)

### [전동휠체어 자동 주차 시스템](https://github.com/bell-ha/wheelchair-auto-parking-system)

`3인 팀 · 위치추정 / 인식 / 통합` &nbsp;`ITRC 과제` &nbsp;`YOLOv8 · OpenCV · SolvePnP · Kalman Filter · IBVS · Jetson Nano`

전동휠체어 사용자가 차에 탄 뒤, 남겨진 휠체어를 타인의 도움 없이 트렁크까지 수납하는 시스템입니다.

처음에는 차량의 어라운드뷰 카메라로 휠체어를 봤습니다. 어안 렌즈 왜곡으로 위치 추정값이 튀었고,
SolvePnP 잔차가 거리와 각도에 따라 체계적으로 편향된다는 것을 확인해 Ridge Regression 보정층과 칼만 필터를 붙였습니다.
그래도 남는 오차가 있었고, 원인이 튜닝이 아니라 "고정된 카메라로 넓은 영역을 왜곡 보정해 본다"는 구조 자체에 있다고 판단해
카메라를 차량에서 휠체어로 옮겼습니다.

이후 차량 부위 6종을 직접 촬영·라벨링해 학습시키고(**mAP50 최대 0.995**), 번호판 실측 규격과 핀홀 모델로
단안 카메라만으로 거리와 자세를 추정했습니다. IBVS와 초음파, IMU를 결합한 9단계 주차 시나리오를 구현했고,
휠체어에 실을 컴퓨터라는 제약에 맞춰 **Jetson Nano에서 15 FPS 실시간 구동**을 검증했습니다.

### [악력 재활 시스템](https://github.com/bell-ha/grip-rehab-system)

`2인 팀` &nbsp;`HX711 · Arduino · Python · 3D Printing`

악력을 회복해야 하는 환자를 위한 재활 훈련 시스템입니다. 반복 훈련이 지루해 지속률이 낮다는 점에서 출발해,
양손 악력을 게임과 소리로 되돌려주도록 설계했습니다.

로드셀 원신호는 스파이크와 진동 때문에 제어 입력으로 바로 쓸 수 없습니다.
스파이크 제거 → 중간값 → 이동평균 → 데드존 4단 필터로 다듬고, 센서 스레드와 게임 루프를 분리해
60 Hz 고정 dt를 유지했습니다. 센서를 Mock / Arduino / 라즈베리파이 3종으로 추상화해 하드웨어 없이도 개발할 수 있게 했습니다.

[데모 영상](https://www.youtube.com/watch?v=_I-ejlEAkNM)

### [두리 — AI 스마트 순찰 로봇](https://github.com/bell-ha/doori-robot-idea)

`SDGs 아이디어 공모전 대상`

포트홀과 파손된 점자블록을 탐지하는 순찰 로봇 제안. 3D 모델링과 Unity 시뮬레이션으로 실현 가능성을 검증했습니다.

<br>

## Software & AI

| | |
|---|---|
| **생성형 AI 반도핑 예방교육 시스템**<br><sub>연세대 AI 혁신연구원 · 2026.08 ~ </sub> | RAG 파이프라인 구축<br>개인화 프롬프트 · 환각 억제 설계 |
| [**Carbon-Aware Scheduler**](https://github.com/HyeonJeong-S/carbon-aware-scheduler)<br><sub>4인 팀 · 로드밸런서(ILP) 담당</sub> | LSTM 예측 + ILP 최적화 + SimPy 시뮬레이션<br>8개 리전 1년치 실측으로 탄소 **−56.9%** 검증 |
| [**Kubernetes 클러스터 인프라**](https://github.com/bell-ha/kubernetes-cloudstack-infrastructure)<br><sub>단독</sub> | Terraform · Ansible로 CloudStack에 K8s v1.30 클러스터 구축<br>GitLab · Jenkins CI/CD 파이프라인 |
| [**SEIHI 아티스트 플랫폼**](https://www.seihi.co.kr/)<br><sub>2인 팀 · 백엔드 담당 · 실서비스 운영</sub> | FastAPI + React 풀스택<br>Google OAuth · Email OTP · JWT 3경로 인증 |
| [**뉴뮤직학부 연습실 예약 시스템**](https://github.com/bell-ha/musicstudio-booking-system)<br><sub>2인 팀 · 백엔드 담당 · 학부생 실사용</sub> | 4중 예약 충돌 검증 (구간 겹침 · 사용자 중복)<br>JWT 인증 · AWS 운영 |
| **WGBS 유전체 분석 GUI**<br><sub>서울대 · 연세대 연구진 협업</sub> | 명령줄 다단계 분석을 GUI로 통합<br>특허 준비 중 |
| [**DelRev**](https://github.com/hitori839/DelRev)<br><sub>4인 팀</sub> | Unity · C# 3D 스텔스 서바이벌 게임<br>게임 로직 구현 및 사운드 디자인 |

<br>

## Music Technology

| | |
|---|---|
| [**국립국악원 음원 규격화**](https://qlaudio.co.kr/product/josun-series-platinum-bundle-%EC%A1%B0%EC%84%A0-%EC%8B%9C%EB%A6%AC%EC%A6%88-%ED%94%8C%EB%9E%98%ED%8B%B0%EB%84%98-%EB%B2%88%EB%93%A4-%EA%B5%AD%EC%95%85-%EA%B0%80%EC%83%81%EC%95%85%EA%B8%B0/15/category/46/display/1/) | 음질 균일화 · 포맷 표준화 후반 작업<br>「조선 시리즈」 국악 가상악기 **36종** 상용 출시 |
| [**감정 기반 TTS 보컬 합성**](https://bell-ha.github.io/papers/이종하_32203482_실시간표정인식을이용한감정기반TTS보컬합성시스템연구.pdf) | 실시간 표정 인식으로 감정을 추정해 보컬 합성에 반영<br>학사 졸업논문 |
| [**단편영화 「After Session」 음악**](https://brunch.co.kr/@3minff/579) | 장면 분석 기반 음악 구성<br>작곡 · 편곡 · 최종 믹싱 납품 |
| [**인터랙티브 사운드 & 퍼포먼스**](https://www.youtube.com/@%EC%9D%B4%EC%A2%85%ED%95%98-t9u) | MediaPipe 제스처 인식 + Max/MSP 실시간 사운드 제어<br>Unity · TouchDesigner 메타버스 입체음향 |
| **서울 마장중학교 밴드부 지도강사** | 피아노 · 베이스 · 일렉기타 · 드럼 · 보컬 5개 파트 지도 및 합주<br>2026.08 ~ |

<br>

## Skills

**Robotics** &nbsp; `ROS2 Humble` `Nav2` `AMCL` `SLAM` `LiDAR` `RealSense` `센서퓨전` `IMU` `CAN` `Jetson Nano` `Arduino` `3D Printing`

**Vision & AI** &nbsp; `YOLOv8` `OpenCV` `SolvePnP` `Kalman Filter` `IBVS` `MediaPipe` `TensorFlow` `GPT-4o Vision` `RAG`

**Languages** &nbsp; `Python` `C#` `TypeScript`

**Backend & Infra** &nbsp; `FastAPI` `React` `PostgreSQL` `Docker` `Kubernetes` `Terraform` `AWS`

**Music** &nbsp; `Max/MSP` `Logic Pro X` `Cubase` `Unity` `TouchDesigner`

<br>

## Education & Awards

단국대학교 뉴뮤직과 뮤직테크놀러지 전공, 컴퓨터공학 복수전공

전공 4.35 / 4.5 &nbsp;·&nbsp; 평점 4.22 / 4.5 &nbsp;·&nbsp; 교육부 예술체육비전 장학생

| | | |
|---|---|---|
| 2026.01 | 지능형 로봇 분야 SDGs 아이디어 공모전 **대상** | 산업통상자원부 · KIAT · 단국대 공학교육혁신센터 |
| 2025.12 | 2025학년도 캡스톤디자인 경진대회 G7부문 장려상 | 단국G-RISE사업단 · 75팀 중 6팀 |
| 2025.12 | 단국대학교 SW중심대학 캡스톤 페스티벌 장려상 | SW중심대학사업단 · 100팀 중 15팀 |
