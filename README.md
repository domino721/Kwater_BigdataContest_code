# K-water 대국민 물 빅데이터 공모전 💧
## 실시간 하수도 손상 유형 탐지 및 자동 분류화: Real-time AI & 드론 자율 주행

본 repository는 **'K-water 대국민 물 빅데이터 공모전'** 에 제출한 코드 및 코드에 대한 부가 설명이 있습니다. 아래 아이콘은 이 프로젝트에 사용된 framework입니다.

<div align="left">
   <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white"/>
   <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=Jupyter&logoColor=white"/>
   <img src="https://img.shields.io/badge/Ultralytics-024DA1?style=flat-square&logo=Ultralytics&logoColor=white"/>
   <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=OpenCV&logoColor=white"/>
</div>

### 📄Code Description
### Real Time 객체 인식.ipynb
이 코드는 **같은 네트워크에 접속한 기기들끼리 real-time으로 연결**할 수 있는 기능을 부여해줍니다. 저희 프로젝트의 목표는, 실시간으로 하수간 손상 유형을 탐지해주는 것이므로, 저희의 데이터셋으로 **학습된 YOLOv8 모델을 로드**해줍니다. 로드된 모델을 이용해 real-time으로 하수도의 파손부(객체)를 인식할 수 있도록, cv2 라이브러리를 활용해 카메라로 영상을 캡쳐합니다. 노트북을 들고 하수도에 들어가서 영상을 촬영하는 것에는 한계가 있는 관계로, **노트북과 같은 서버로 접속되어있는 스마트폰의 카메라를 이용해 두 기기를 연결**시킵니다.
* **두 기기를 연결시키는 방법**
  1. 스마트폰에 **'iPCamera - High-End Network Cam'** 애플리케이션 설치
  2. 스마트폰과 노트북이 **같은 네트워크(WiFi)에 접속시키기**

두 기기의 연결이 완료되면, 노트북에는 **'YOLOv8 Inference'이라는 팝업창**이 떠, 스마트폰으로 촬영된 영상 속 하수도의 손상 유형이 정확히 탐지하는지 확인하면 됩니다.

-----

### YOLOv8 학습 및 성능 평가.ipynb
**Ultralytics YOLOv8 모델을 사용하여 하수관로의 파손부를 자동으로 인식하는 컴퓨터 비전 모델**을 학습시키고 **테스트셋에 대한 mAP를 통해 모델의 성능을 평가**하는 코드입니다. 코드의 흐름은 다음과 같습니다.
1. **Custom Data에 대한 yaml 파일 만들기** - **Roboflow** 플랫폼을 이용하여 **하수관로 파손 유형별 이미지 파일과 어노테이션 파일이 저장된 데이터셋을 구축**한 뒤, 이를 YOLOv8 모델에 학습시키기 위한 **yaml 파일을 생성**합니다. Training, Validation, Test 폴더에 각각 images 폴더와 labels 폴더로 구성하여 저장하였습니다. 
2. **모델 학습** - **COCO 데이터셋으로 사전 학습된 YOLOv8 모델을 불러와** 6,600개의 Custom Dataset으로 학습시켰습니다. Epochs, patience, batch, imgsz를 포함한 다양한 파라미터를 바꿔가며 최적의 성능을 가진 모델을 확인할 수 있도록 했습니다. 
3. **성능 평가** - Validation Set과 Test Set에 대하여 객체 탐지를 수행하고 성능 평가를 진행했습니다. **성능 측정 지표는 mAP**를 이용했습니다. 
4. **객체 탐지 수행 확인** - 테스트셋에 대해 실제로 객체 탐지를 수행하고, 결과를 확인할 수 있도록 bbox가 포함된 이미지를 설정된 경로에 저장하였습니다. 
-----

### 자율주행 자동차 예시 코드.ipynb
이 코드는 자율 주행 자동차가 실제로 주행할 수 있도록 구현되어있습니다. 본 자동차는 'Roborobo'(https://roborobo.co.kr) 의 'ROBO KIT(Series)'제품으로, 자동차와 노트북을 연결시키기 위해서는 Roborobo의 공식 사이트(https://roborobo.co.kr/download/0)에서 소프트웨어를 다운받아야 합니다. 주행 코드를 실행시키기에 앞서서, 다운받은 소프트웨어를 설치한 후, 'RobokitRS'도 설치해야 합니다. 이것은 간단하게 노트북의 터미널 혹은 주피터 노트북 셀에서 'pip install RobokitRS'를 통해서 실행시킬 수 있습니다.
