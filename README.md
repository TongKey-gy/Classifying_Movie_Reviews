<🎬 IMDB 영화 리뷰 감성 분류 프로젝트>

이 프로젝트는 딥러닝 기반 자연어 처리(NLP) 기법을 활용하여
IMDB 영화 리뷰가 **긍정(Positive)**인지 **부정(Negative)**인지 판단하는 이진 분류 모델을 구현한 실습입니다.


<🛠 Tech Stack>

Language: Python
Libraries: TensorFlow(Keras), NumPy, Matplotlib
Task: Natural Language Processing, Binary Classification


<📊 Dataset & Preprocessing>

데이터셋: Keras 내장 IMDB Dataset
훈련 데이터: 25,000개
테스트 데이터: 25,000개
주요 전처리 단계
단어 제한 (num_words=10000)

가장 자주 등장하는 상위 10,000개 단어만 사용하여 노이즈를 제거했습니다.


<<벡터화 (Vectorization)>>

정수 시퀀스로 표현된 리뷰를 10,000차원 Multi-hot Encoding 벡터로 변환했습니다.
각 인덱스는 단어의 존재 여부(0 또는 1)를 나타냅니다.


<<레이블 변환>>

긍정: 1, 부정: 0
모델 손실 계산을 위해 float32 형식으로 변환했습니다.


<📉 Training Process & Key Insights>

1. 검증 데이터 분리 (Validation Split)

훈련 데이터 중 10,000개를 분리하여 학습 중 모델 성능을 실시간 확인했습니다.

2. 과대적합(Overfitting) 발견

20 Epoch 학습 실험 결과 Epoch 4 이후 검증 손실이 증가하며 과대적합이 발생했습니다.

이를 통해 최적 Epoch 수는 4회임을 확인했습니다.

3. 최종 모델 재학습

전체 25,000개 훈련 데이터를 모두 활용하여
Epoch 4까지 재학습 → 최적 성능 확보


<🏆 Final Results>

테스트 데이터(25,000개)에 대한 최종 평가 결과:

Metric	Score
Loss	0.29
Accuracy	88.1%

👉 이 모델은 새로운 영화 리뷰를 약 88%의 정확도로 긍정/부정을 분류할 수 있습니다.
