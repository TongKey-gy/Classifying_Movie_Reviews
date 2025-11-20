🎬 IMDB 영화 리뷰 감성 분류 프로젝트
이 프로젝트는 딥러닝을 활용하여 IMDB 영화 리뷰가 **긍정(Positive)**인지 **부정(Negative)**인지 판별하는 이진 분류(Binary Classification) 모델을 구현한 실습입니다.

🛠 사용 기술 (Tech Stack)
Language: Python

Library: TensorFlow (Keras), NumPy, Matplotlib

Task: Natural Language Processing (NLP), Classification

📊 데이터셋 및 전처리 (Dataset & Preprocessing)
데이터 출처: Keras 내장 IMDB 데이터셋

데이터 크기: 훈련 데이터 25,000개 / 테스트 데이터 25,000개

주요 전처리 과정:

단어 제한 (num_words=10000): 데이터에서 가장 빈번하게 등장하는 상위 10,000개의 단어만 사용하여 노이즈를 줄였습니다.

벡터화 (Vectorization): 리뷰 텍스트(정수 시퀀스)를 0과 1로 이루어진 **10,000 차원의 벡터(Multi-hot encoding)**로 변환하여 모델에 입력했습니다.

레이블 변환: 긍정(1), 부정(0) 레이블을 float32 실수형으로 변환하여 손실 계산에 최적화했습니다.

📉 학습 과정 및 인사이트 (Training & Insights)
1. 검증 데이터 분리 (Validation) 훈련 데이터 중 10,000개를 검증 데이터로 따로 분리하여, 학습 도중 모델의 성능을 실시간으로 모니터링했습니다.

2. 과대적합(Overfitting) 해결 초기 20 Epoch 학습 실험 결과, Epoch 4 이후부터 훈련 손실은 줄어들지만 검증 손실은 오히려 증가하는 과대적합 현상을 발견했습니다. 이를 통해 최적의 학습 횟수가 4회임을 도출해냈습니다.

3. 최종 모델 재학습 검증 데이터를 포함한 전체 25,000개 훈련 데이터를 모두 사용하여, 과대적합이 발생하기 직전인 4 Epoch 동안 모델을 다시 학습시켜 성능을 극대화했습니다.

🏆 최종 결과 (Final Results)
처음 보는 테스트 데이터 25,000개에 대한 최종 평가 결과는 다음과 같습니다.

Loss (손실값): 0.29

Accuracy (정확도): 88.1%

이 모델은 새로운 영화 리뷰에 대해 약 88%의 확률로 긍정과 부정을 정확하게 분류해냅니다.
