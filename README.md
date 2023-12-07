# kobert-ipc
[KoBERT](https://github.com/SKTBrain/KoBERT) 모델을 fine-tuning하여 특허의 초록을 기반으로 해당 특허의 IPC 코드를 분류하는 multi-label classification 모델



### 개발 기간 및 환경
- 2023-10-25 ~ 2023-12-07
- `Python 3.8.18`
- **IDE** : PyCharm 2023.2.5
  
<br>

### 기타 특이사항
- KoBERT 레포지토리의 파일을 로컬 환경에 설치하여 사용
- import 시 설치한 KoBERT 파일의 수정 필요
- Google Colab에서 실행하려면 수정 필요

<br>

### Data description

- '초록', 'ipc코드' 2개의 열로 구성
- 초록에는 전처리를 마친 해당 특허의 초록이 존재
- ipc코드에는 [0, 0, 1, ..., 0]과 같이 해당하는 label은 1, 해당하지 않는 label은 0으로 binary하게 coding 되어 있음
  
<br>

### Model description
- 손실함수로는 Balanced focal loss 사용
- 평가 지표로는 Accuracy를 사용하였으나, F1 score등의 기타 metric 권장
- Epoch 하나 당 약 40분 소요 (학습 환경에 따라 달라질 수 있음)
