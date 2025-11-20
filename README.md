Github README에 올리기 좋도록 프로젝트 개요, 데이터 처리, 모델 구조, 학습 과정, 최종 결과 순서로 깔끔하게 요약해 드립니다.

아래 내용을 복사해서 README.md 파일에 붙여넣으시면 됩니다. 필요에 따라 내용을 조금씩 수정해서 사용하세요!

📋 IMDB 영화 리뷰 감성 분류 (Binary Classification)
이 프로젝트는 딥러닝을 활용하여 IMDB 영화 리뷰가 **긍정(Positive)**인지 **부정(Negative)**인지 판별하는 이진 분류 모델을 구현한 실습입니다.

🛠 Tech Stack
Language: Python

Library: TensorFlow (Keras), NumPy, Matplotlib

📊 Dataset
Source: Keras Built-in IMDB Dataset

Size: 훈련 데이터 25,000개 / 테스트 데이터 25,000개

Preprocessing:

num_words=10000: 빈도수 상위 10,000개 단어만 사용

Vectorization: 리스트 형태의 리뷰 데이터를 10,000 차원의 원-핫 인코딩(Multi-hot encoding) 벡터로 변환

Label: float32 타입으로 변환


📉 Training Process & Insight
검증 데이터 분리: 훈련 데이터 중 10,000개를 검증셋(Validation Set)으로 분리하여 학습 과정을 모니터링했습니다.

과대적합(Overfitting) 감지:

초기 실험(20 Epochs) 결과, Epoch 4 이후부터 훈련 손실은 줄어들지만 검증 손실이 다시 증가하는 과대적합 현상을 확인했습니다.

이를 통해 최적의 학습 횟수가 4회임을 도출했습니다.

최적화: 전체 훈련 데이터를 사용하여 4 Epochs로 모델을 재학습시켰습니다.

🏆 Final Results
테스트 데이터(25,000개)를 통한 최종 평가 결과는 다음과 같습니다.

Loss: 0.29

Accuracy: 88.1%
