# medicine_ml
# 데이콘 신약개발 AI 경진대회

**팀명:** AI Drug Developers (이주용, 박단영, 정지훈)

**주최:** 데이콘

---

## 프로젝트 개요
이 프로젝트는 신약 개발을 위한 데이터 분석 및 예측 모델을 개발하는 데 중점을 두고 있습니다. 다양한 데이터 전처리 기법과 머신러닝 알고리즘을 사용하여 신약의 효능을 예측합니다.

### 프로젝트 목표
- 신약 개발 데이터 분석
- 효능 예측 모델 개발 및 평가

---

## 데이터
- **출처:** 데이콘 제공
- **구성:** 화합물 정보 및 생물학적 활성을 포함한 다양한 특징
- **전처리:** 결측값 처리, 정규화, 특징 공학(Feature Engineering)

---

## 탐색적 데이터 분석 (EDA)
- **목적:** 데이터의 분포와 상관 관계 파악
- **주요 분석 내용:**
  - 데이터의 기초 통계량 분석
  - 상관 관계 분석
  - 시각화를 통한 데이터 이해

### 주요 전처리 기법
- **로그 변환(Log Transformation):**
  - 왜도와 첨도가 높은 피처에 대해 로그 변환을 적용하여 분포를 정규화
  ```python
  train['num_rotatablebonds_log'] = np.log1p(train['num_rotatablebonds'])
  test['num_rotatablebonds_log'] = np.log1p(test['num_rotatablebonds'])
이상치 제거(Outlier Removal):
IQR 방법 등을 사용하여 이상치를 식별하고 제거
박스-콕스 변환(Box-Cox Transformation):
로그 변환이 실패하는 경우에 유용
정규화(Normalization)/표준화(Standardization):
각 피처의 스케일 차이로 인한 문제를 해결
모델링
사용된 알고리즘:

Gradient Boosting
LightGBM
XGBoost
PyCaret을 사용한 다양한 모델 비교
평가 방법:

정확도, 정밀도, 재현율, F1 스코어
혼동 행렬 분석
모델 학습 과정:

데이터 분할 (Train/Test Split)
하이퍼파라미터 튜닝
교차 검증 (Cross-validation)
주요 성과 및 결과
모델 성능:

각 모델의 정확도 및 F1 스코어 비교
최적 모델 선택 및 튜닝 결과
주요 인사이트:

중요한 특징 및 변수 파악
모델의 예측 성능에 영향을 미치는 요소 분석
코드 구조
데이터 전처리: 데이터 로딩 및 전처리 과정
EDA: 탐색적 데이터 분석 및 시각화
모델링: 다양한 모델 학습 및 평가
결과 분석: 최종 모델 성능 평가 및 인사이트 도출
