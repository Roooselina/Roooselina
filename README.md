<div align="center">

## 이은정 · Lee EunJeong

**AI 모델 개발 · AI 서비스 / 백엔드 개발**

순천향대학교 컴퓨터공학과 · 2027년 2월 졸업 예정

</div>

음성 딥페이크 탐지 졸업논문에서 음향 특징 설계, 시퀀스 모델 비교, 통계 검정까지 진행했고, LLM으로 회의 결정과 산출물 문서의 불일치를 찾는 데스크톱 Agent를 만들었습니다. 모델 결과를 평가 조건과 함께 기록하고, AI 기능을 실제로 실행되는 서비스 구조(로컬 API 서버, 캐시, 테스트)에 연결하는 일에 관심이 있습니다.

<br>

### 대표 프로젝트

#### 1. [Decision Agent: 의사결정 변경 전파 불일치 탐지](https://github.com/Roooselina/decision_agent)

`Python` `Anthropic API` `FastAPI` `SQLite` `scikit-learn` `pytest` · 2026 학술제 장려상

- **문제**: 회의에서 결정이 바뀌어도 요구사항·Task·테스트·일정 문서에 옛 내용이 남는다. 결정에는 MVP 한정처럼 적용 범위가 있어 키워드 검색으로는 구분하기 어렵다.
- **구현**: 결정·관계·scope를 구조화해 SQLite에 저장하고, 산출물마다 유효한 결정을 계산한 뒤 LLM으로 판정. 같은 판단 함수를 고정 순서 Pipeline과 도구 선택형 Agent가 공유하도록 설계. 근거가 부족하면 확인 질문.
- **서비스화**: 폴더 감시 → 바뀐 topic만 재점검, LLM 응답 디스크 캐시, `127.0.0.1` 전용 FastAPI 화면, 키는 OS 자격 증명 저장소에만 저장.
- **확인 가능한 결과**: 테스트 767개 통과(2026-11-05, Windows 11 로컬 실행). 실제 LLM에서의 탐지 정확도는 아직 측정하지 않음.

#### 2. [딥페이크 음성 탐지: 다중 음향 특징 + 시퀀스 모델 비교](https://github.com/Roooselina/Capstone-Project)

`Python` `PyTorch` `librosa` `scikit-learn` · 졸업논문(개인 연구) · 2025.09–11

- **문제**: 실제 음성과 합성 음성 구분.
- **구현**: MFCC·Δ·ΔΔ·LFCC·Mel·Spectral Contrast를 같은 프레임 격자에서 106차원으로 결합, BiLSTM·Transformer·Hybrid를 같은 조건으로 비교. RAM 15 GB에서 약 31 GB 특징을 다루기 위해 청크 저장과 Welford 정규화 사용.
- **결과**: ASVspoof 2019 LA + LibriSpeech로 구성한 테스트 분할 15,891건에서 BiLSTM Macro F1 0.9990, EER 0.082%. McNemar 검정에서 Transformer와의 차이는 유의(p=0.013), BiLSTM과 Hybrid는 차이 없음(p=1.0).
- **한계**: 파일 단위 무작위 분할이라 화자·코퍼스 누수 가능성이 있고 외부 데이터 일반화는 검증하지 않음.

#### 3. [AI 오늘의 말투 변환기](https://github.com/Roooselina/Mobile-Application-Programming)

`Java` `Android` `SQLite` `Retrofit` `Claude API` · 3인 팀

- **문제**: 상대와 상황을 매번 설명하지 않고 한국어 문장의 말투를 바꾸기.
- **담당**: Android 개발, DB, 인증, 대화 로직, API 연동.
- **구현**: 계정별 프롬프트·대화 이력·응답 버전을 SQLite에 저장, 이메일 인증과 SHA-256+솔트 비밀번호, 입력 후 1.2초 미리보기와 전송 시 재사용.
- **한계**: 클라이언트가 API를 직접 호출하므로 배포 전 서버 프록시가 필요.

<br>

### 그 밖의 저장소

| 저장소 | 내용 |
|---|---|
| [deepfake-voice-detector](https://github.com/Roooselina/deepfake-voice-detector) | 딥페이크 음성 판별 Android 앱 + Flask 서버 (2인 팀, 웹–AI 연결 외 개발 담당) |
| [Deep_Learning](https://github.com/Roooselina/Deep_Learning) | MLP·CNN·전이학습 과제, 신선/부패 식품 분류와 Grad-CAM |
| [SEMINAR_SCH_UNIV](https://github.com/Roooselina/SEMINAR_SCH_UNIV) | 연구실 머신러닝 기초·심화, DQN/DDQN 세미나 실습 |
| [Computer-Game](https://github.com/Roooselina/Computer-Game) | Unity 2D 러너와 3D 탄알 피하기 텀프로젝트 |
| [CSLab2025_CodingTest](https://github.com/Roooselina/CSLab2025_CodingTest) | 연구실 코딩 테스트 스터디 (Python) |

<br>

<div align="center">

### Tech

**AI / ML**<br>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
<img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white" alt="PyTorch" />
<img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn" />
<img src="https://img.shields.io/badge/librosa-4B5563?style=flat-square" alt="librosa" />
<img src="https://img.shields.io/badge/Anthropic_API-191919?style=flat-square&logo=anthropic&logoColor=white" alt="Anthropic API" />

**Backend / App**<br>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
<img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white" alt="SQLite" />
<img src="https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white" alt="pytest" />
<img src="https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white" alt="Java" />
<img src="https://img.shields.io/badge/Android-34A853?style=flat-square&logo=android&logoColor=white" alt="Android" />

**수업에서 사용**<br>
C · C++ · C# (WinForms) · Unity · Flask · HTML/CSS/JavaScript

</div>

<br>

### 활동 · 자격

- 학부연구생: 순천향대학교 CSE 연구실(2023.12 ~ 2025), IPL 연구실(2025 ~ 현재)
- 수상: 2024 공학대학 학술제 은상, 2025 공학대학 학술제 금상, 2026 학술제 장려상(Decision Agent)
- 학술제 발표: 2024 퍼스널 컬러 진단 앱(모델 학습 담당, [디자인·발표 자료](https://github.com/Roooselina/personalized-color-app)), 2026 Decision Agent
- 멋쟁이사자처럼 순천향대 13기 AI 파트: 세션 예제 코드 작성, 과제 PR 리뷰·병합
- CODE 동아리 운영위원(2024 ~ 2025): 1학년 대상 코딩 수업 진행
- ADsP (데이터분석 준전문가, 2025-06)

### Contact

kurocheki1@gmail.com
