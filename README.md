# 이종하 (Jongha Lee)

**사용자가 무엇을 원하는지 파고들고, 실제로 돌아가게 만듭니다.**

시각장애인 안내 로봇은 당사자를 직접 인터뷰해 필요한 것을 정하고 실기체에서 동작시켰습니다.<br>
전동휠체어 자동 주차는 인식 방식이 안 되겠다고 판단해 곧바로 다른 방식으로 바꿨습니다.<br>
3D 잠입 액션 게임 DelRev에서는 직접 플레이하며 찾은 문제를 반영해 플레이어 시스템과 사운드를 만들었습니다.

실서비스로 배포한 백엔드, 직접 구축한 쿠버네티스 클러스터, 상용 출시한 음악도 같은 방식으로 만들었습니다.

**[Portfolio](https://bell-ha.github.io/)** · [Resume](https://bell-ha.github.io/resume.html) · [YouTube](https://www.youtube.com/@%EC%9D%B4%EC%A2%85%ED%95%98-t9u) · jongha8273@gmail.com<br>
단국대학교 뉴뮤직과 · 컴퓨터공학 복수전공 · 배리어프리 ICT기술 연구센터(ITRC) 학부연구생

---

## Tech Stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) ![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=csharp&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)

**Robotics & Embedded**

![ROS2](https://img.shields.io/badge/ROS2-22314E?style=flat&logo=ros&logoColor=white) ![Nav2](https://img.shields.io/badge/Nav2-1F6FEB?style=flat) ![SLAM](https://img.shields.io/badge/SLAM-1F6FEB?style=flat) ![LiDAR](https://img.shields.io/badge/LiDAR-1F6FEB?style=flat) ![RealSense](https://img.shields.io/badge/RealSense-0071C5?style=flat&logo=intel&logoColor=white) ![Jetson Nano](https://img.shields.io/badge/Jetson_Nano-76B900?style=flat&logo=nvidia&logoColor=white) ![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat&logo=arduino&logoColor=white)

**AI & Vision**

![YOLOv8](https://img.shields.io/badge/YOLOv8-00FFFF?style=flat&logo=yolo&logoColor=black) ![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white) ![MediaPipe](https://img.shields.io/badge/MediaPipe-0097A7?style=flat&logo=google&logoColor=white) ![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white) ![RAG](https://img.shields.io/badge/RAG-412991?style=flat&logo=openai&logoColor=white)

**Game**

![Unity](https://img.shields.io/badge/Unity-000000?style=flat&logo=unity&logoColor=white) ![NavMesh](https://img.shields.io/badge/NavMesh-3E7BBF?style=flat) ![URP](https://img.shields.io/badge/URP-222C37?style=flat)

**Backend & Infra**

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white) ![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat&logo=terraform&logoColor=white) ![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat&logo=ansible&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)

**Music & Interactive**

![Logic Pro X](https://img.shields.io/badge/Logic_Pro_X-000000?style=flat&logo=apple&logoColor=white) ![Max/MSP](https://img.shields.io/badge/Max%2FMSP-525252?style=flat) ![Cubase](https://img.shields.io/badge/Cubase-CF0F1B?style=flat) ![TouchDesigner](https://img.shields.io/badge/TouchDesigner-1D1D1D?style=flat)

---

## Projects

### Robotics & Embedded

| | |
|---|---|
| **[시각장애인 실내 안내 로봇](https://github.com/bell-ha/visually-impaired-navigation-robot)** | Hello Robot Stretch SE3 기반 실내 자율 안내 로봇. 그리퍼 카메라로 엘리베이터 버튼을 직접 인식해 누르고 1층에서 5층까지 이동. |
| **[전동휠체어 자동 주차 시스템](https://github.com/bell-ha/wheelchair-auto-parking-system)** | 카메라를 휠체어에 실어 차량 부위 6종을 인식하고 스스로 수납. YOLOv8 재학습, 단안 거리 추정, Jetson Nano 실시간 구동. |
| **[악력 재활 훈련 시스템](https://github.com/bell-ha/grip-rehab-system)** | HX711 로드셀 + Arduino 기반 양손 악력 측정. 신호 처리 파이프라인, 재활 게임 4종, 실시간 신디사이저. |
| **[두리 — AI 스마트 순찰 로봇](https://github.com/bell-ha/doori-robot-idea)**<br>*2025 지능형 로봇 SDGs 아이디어 공모전 대상* | 포트홀·점자블록 파손을 실시간 감지하는 자율 순찰 로봇 제안. YOLOv8 탐지, ROS2 + SLAM, Unity 시뮬레이션. |

### Game

| | |
|---|---|
| **[DelRev — 3D 잠입 액션 게임](https://github.com/hitori839/DelRev)**<br>*캡스톤 경진대회 장려상 2회* | Unity 2022(URP) + C# 게임. 플레이어 시스템, 위험 게이지, 방해자 AI, 사운드 58개 담당. |

### Software & AI

| | |
|---|---|
| **생성형 AI 반도핑 예방교육 시스템** | 연세대 AI 혁신연구원 프로젝트. RAG 파이프라인, 개인화 프롬프트, 환각 억제 설계. |
| **[Carbon-Aware Scheduler](https://github.com/HyeonJeong-S/carbon-aware-scheduler)** | LSTM 예측과 ILP 최적화로 데이터센터 탄소 56.9% 절감. SimPy 시뮬레이션으로 8개 리전 1년치 실측 검증. |
| **[Cloud-Native Kubernetes Cluster Infrastructure](https://github.com/bell-ha/kubernetes-cloudstack-infrastructure)** | CloudStack에 Terraform + Ansible로 k8s 클러스터를 IaC 자동화. Calico·MetalLB, GitLab·Jenkins 배포. |
| **[아티스트 홍보 플랫폼 SEIHI](https://github.com/bell-ha/artist-promotion-platform)** | FastAPI + React 18/TypeScript 풀스택 웹 서비스. Google OAuth·이메일 OTP 인증, Cloudinary 업로드. |
| **[단국대학교 뉴뮤직학부 연습실 예약 시스템](https://github.com/bell-ha/musicstudio-booking-system)** | 학부 학생들이 실제로 사용하는 예약·장비 관리 서비스. JWT 인증, 중복 예약 방지, AWS EC2 운영. |
| **WGBS 유전체 분석 자동화 데스크톱 프로그램** | 서울대·연세대 연구진과 협업. 명령줄 다단계 분석을 비전공자도 쓸 수 있는 GUI로 통합. 특허 준비 중. |
| **실시간 표정 인식 기반 감정 TTS 보컬 합성 시스템**<br>[논문 PDF](https://bell-ha.github.io/papers/이종하_32203482_실시간표정인식을이용한감정기반TTS보컬합성시스템연구.pdf) | 표정으로 감정을 추정해 보컬 합성에 실시간 반영하는 시스템을 설계·구현한 학사학위 논문. |

### Music Technology

| | |
|---|---|
| **게임 사운드팩 — 여섯 장르** | 캐주얼 시뮬레이션 · 카드 전략 · FPS/배틀로얄 · 다크 판타지 RPG · 캐주얼 퍼즐 · 액션 격투 사운드팩 제작. |
| **국립국악원 국악 음원 규격화 및 아카이빙**<br>[조선 시리즈](https://qlaudio.co.kr/product/josun-series-platinum-bundle-%EC%A1%B0%EC%84%A0-%EC%8B%9C%EB%A6%AC%EC%A6%88-%ED%94%8C%EB%9E%98%ED%8B%B0%EB%84%98-%EB%B2%88%EB%93%A4-%EA%B5%AD%EC%95%85-%EA%B0%80%EC%83%81%EC%95%85%EA%B8%B0/15/category/46/display/1/) | 음질 균일화·포맷 표준화 후반 작업. 국립국악원 × Qlaudio 협업 음원은 36종 국악 가상악기로 출시. |
| **단편영화 「After Session」 음악 제작**<br>[정보](https://brunch.co.kr/@3minff/579) | 권혁준 감독 작품의 작곡·편곡 및 사운드 디자인, 최종 믹싱. |
| **인터랙티브 사운드 & 퍼포먼스 작업**<br>[YouTube](https://www.youtube.com/@%EC%9D%B4%EC%A2%85%ED%95%98-t9u) | MediaPipe 제스처 인식, Max/MSP 실시간 사운드 제어, Unity 공간 음향. |
| **서울 마장중학교 방과후 지도강사** | 오케스트라·밴드부 파트별 점검과 합주 지도, 연주회 무대 준비. |

---

## Education & Awards

**단국대학교** 뉴뮤직과 뮤직테크놀러지 · 컴퓨터공학 복수전공 (2020.03 ~ 2027.02 졸업예정)<br>
전공 학점 4.35 / 4.5 · 평점 평균 4.22 / 4.5 · 교육부 예술체육비전 장학생

| | |
|---|---|
| 2026.01 | 지능형 로봇 분야 SDGs 아이디어 공모전 **대상** |
| 2025.12 | 캡스톤디자인 경진대회 G7부문 장려상 · 75팀 중 6팀 |
| 2025.12 | SW중심대학 캡스톤 페스티벌 장려상 · 100팀 중 15팀 |
