# K-water 대국민 물 빅데이터 공모전 💧
## 실시간 하수도 손상 유형 탐지 및 자동 분류화: Real-time AI & 드론 자율 주행

본 repository는 **'K-water 대국민 물 빅데이터 공모전'**에 제출한 코드 및 프로젝트 결과물입니다. YOLOv8을 이용한 실시간 객체 탐지와 자율주행 자동차를 결합하여 하수도 유지보수를 자동화하는 솔루션을 제안합니다.

<div align="left">
   <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white"/>
   <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=Jupyter&logoColor=white"/>
   <img src="https://img.shields.io/badge/Ultralytics-024DA1?style=flat-square&logo=Ultralytics&logoColor=white"/>
   <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=OpenCV&logoColor=white"/>
</div>

---

## 📁 Repository Structure

```text
Kwater_BigdataContest_code/
├── assets/                  # 프로젝트 관련 이미지 및 미디어
├── models/                  # 학습된 모델 가중치 (final.pt)
├── notebooks/               # 주요 분석 및 실행 Jupyter Notebooks
│   ├── Real Time 객체 인식.ipynb
│   ├── YOLOv8 학습 및 성능 평가.ipynb
│   └── 자율주행 자동차 예시 코드.ipynb
├── requirements.txt         # 설치 라이브러리 목록
├── .gitignore               # 불필요한 파일 제외 설정
└── README.md                # 프로젝트 설명 문서
```

---

## 🚀 Getting Started

### 1. 환경 설정 (Installation)
프로젝트 실행을 위해 필요한 라이브러리를 설치합니다.
```bash
pip install -r requirements.txt
```

### 2. 주요 코드 설명

#### 🔍 Real Time 객체 인식.ipynb
*   **기능**: YOLOv8 모델을 로드하여 스마트폰 카메라와 연동된 실시간 탐지 수행.
*   **연결 방법**:
    1. 스마트폰에 'iPCamera' 앱 설치.
    2. 동일 네트워크(WiFi) 접속 후 IP 연결.
    3. 노트북 팝업창에서 실시간 탐지 결과 확인.

#### 🧠 YOLOv8 학습 및 성능 평가.ipynb
*   **기능**: Custom Dataset을 이용한 YOLOv8 모델 학습 및 mAP 성능 평가.
*   **과정**: Roboflow 데이터셋 구축 → 가중치 학습 → 성능 지표(mAP) 측정.

#### 🏎️ 자율주행 자동차 예시 코드.ipynb
*   **기능**: Roborobo 'ROBO KIT' 자동차의 자율 주행 제어 로직 구현.
*   **사전 준비**: 
    1. [Roborobo 공식 사이트](https://roborobo.co.kr/download/0)에서 소프트웨어 설치.
    2. `pip install RobokitRS` 명령어로 제어 라이브러리 설치.

---

## 📊 결과 요약
*   **모델**: YOLOv8 Nano (Custom Dataset 학습)
*   **성능**: 테스트셋 기준 높은 mAP 달성 및 실시간 탐지 성공.
*   **하드웨어**: Roborobo 자동차 및 스마트폰 카메라 서버 연동.

---

## ⚠️ 주의 사항
*   `models/final.pt` 파일은 용량이 크므로 Git LFS 설정을 권장합니다.
*   하드웨어(자동차) 연결 시 포트 번호 및 네트워크 설정을 반드시 확인하십시오.
