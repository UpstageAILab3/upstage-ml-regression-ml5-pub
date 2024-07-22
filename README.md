# House Price Prediction 경진대회
- Upstage AI Stages https://stages.ai/en/competitions/312/overview/description

![](https://github.com/UpstageAILab3/upstage-ml-regression-ml5/blob/kimkihong/docs/image/team5-001.JPG?raw=true)

## Team

![](https://github.com/UpstageAILab3/upstage-ml-regression-ml5/blob/kimkihong/docs/image/team5-004.JPG?raw=true)

## 1. Competiton Info

### Overview
- House Price Prediction 경진대회는 서울의 아파트 실거래가를 효과적으로 예측하는 모델을 개발하는 대회입니다. 부동산은 개인과 판매자, 그리고 정부 모두에게 중요한 요소로, 아파트 자체의 가치뿐만 아니라 주변 환경(강, 공원, 백화점 등)에 의해 가격이 변동됩니다.

* 이 대회는 다양한 부동산 관련 의사결정을 돕기 위해 서울시의 아파트 실거래가를 예측하는 모델을 개발하는 것을 목표로 합니다.
    - 개인: 합리적인 가격에 좋은 집을 찾기 위함
    - 판매자: 적절한 가격에 집을 판매하기 위함
    - 정부: 비정상적 시세 변동 및 부정 거래를 파악하기 위함


### Timeline

- 대회기간 : 2024년 7월 9일 ~ 7월 19일

### Evaluation

- RMSE
    - RMSE는 예측된 값과 실제 값 간의 평균편차를 측정합니다.
    - 아파트 매매의 맥락에서는 회귀 모델이 실제 거래 가격의 차이를 얼마나 잘 잡아내는지 측정합니다. 

## 2. Components

### Directory

- ensemble_12281.7758 폴더 : Private Leader Board 팀내 1등
```python
Model.ipynb : 학습, 예측
Model_for_finding_hyperparam.ipynb : GridSearchCV 를 사용한 HyperParameter Tuning (미완성)
Preprocess_jibun_xy_by_naver.ipynb : Naver Maps API 를 활용한 위도, 경도 결측치 처리
Preprocess_nearestElemSchool.ipynb : 최단거리 초등학교 피처 생성
Preprocess_기대인플레이션율.ipynb : 기대인플레이션율 전처리
```

- randomforest_13620.6815 폴더 : Private Leader Board 팀내 2등
```python
00_240716_building_name : 아파트명 -> 건물명 복사해서 결측치 해결
00_240716_data : 데이터 전처리
00_240717_notnull_df_2 : 데이터 전처리
00_240717_zdate_n : 데이터 전처리
240717_02_model_test : 모델별 성능 테스트, randomforest 팀내 2등한 모델 
240718_03_kf_cv: time series 구현
```

### 개인 Branch
- 김기홍 https://github.com/UpstageAILab3/upstage-ml-regression-ml5/tree/kimkihong
- 이재명 https://github.com/UpstageAILab3/upstage-ml-regression-ml5/tree/ljm
- 이윤재 https://github.com/UpstageAILab3/upstage-ml-regression-ml5/tree/yoonjae
- 장은지 https://github.com/UpstageAILab3/upstage-ml-regression-ml5/tree/ejj
- 최지미 https://github.com/UpstageAILab3/upstage-ml-regression-ml5/tree/jimi

## 3. Process

### 설계
1. 평가지표
    1. Train / Valid / Test / Submission 별 점수 비교를 위한 성능 지표 설계
    2. RMSE 외 보조 지표(R-squared, MAE) 함께 활용
2. 실험 기록
    1. 실험 결과로부터 인사이트 도출과 팀원간 원활한 공유를 위해 테이블 생성
    2. 항목 : 실험 일시, 수행 시간, 모델, 피처, 하이퍼 파라미터, 평가지표, 분석 내용 등

### 수행 절차
1. 강의 수강 및 베이스라인 코드 확인
2. 기본 데이터 분석 및 전처리
3. 자료 탐색 : 외부 데이터, 논문, 대회
4. 피처 엔지니어링
5. 피처 셀렉션
6. 데이터셋 분할 : Hold Out, Time Series 
7. 모델링
    1. 모델 선정 : Random Forest, LightGBM, XGBoost, CatBoost, 앙상블
    2. 하이퍼 파라미터 튜닝
    3. 학습 및 예측
    4. 성능 평가
8. 1~7 반복

## 4. Data descrption

### Dataset overview

![](https://github.com/UpstageAILab3/upstage-ml-regression-ml5/blob/kimkihong/docs/image/team5-008.JPG?raw=true)

### EDA

![](https://github.com/UpstageAILab3/upstage-ml-regression-ml5/blob/kimkihong/docs/image/team5-014.JPG?raw=true)

![](https://github.com/UpstageAILab3/upstage-ml-regression-ml5/blob/kimkihong/docs/image/team5-018.JPG?raw=true)

### Feature engineering

![](https://github.com/UpstageAILab3/upstage-ml-regression-ml5/blob/kimkihong/docs/image/team5-020.JPG?raw=true)

![](https://github.com/UpstageAILab3/upstage-ml-regression-ml5/blob/kimkihong/docs/image/team5-023.JPG?raw=true)

## 5. Modeling

### Model descrition

![](https://github.com/UpstageAILab3/upstage-ml-regression-ml5/blob/kimkihong/docs/image/team5-026.JPG?raw=true)

### Modeling Process

![](https://github.com/UpstageAILab3/upstage-ml-regression-ml5/blob/kimkihong/docs/image/team5-029.JPG?raw=true)

## 6. Result

### Leader Board

- Midterm - RMSE_16985.3668 - 7위
- Final - RMSE_12281.7758 - 4위(동메달)

### Presentation

- [패스트캠퍼스_Upstage AI Lab 3기_ML 경진대회_발표자료_5조](/docs/pdf/패스트캠퍼스_Upstage_AI_Lab_3기_ML_경진대회_발표자료_5조.pdf)

## etc

### Meeting Log

- [서울아파트_실거래가_예측_현황공유판](/docs/pdf/서울아파트_실거래가_예측_현황공유판.xlsx)
- [사전 미팅 로그](https://www.notion.so/a5ce164af8ca43c486865b2b93c257cf?v=c4aff498a69049779e147c2a2832ac2a&pvs=4)

### Reference
*  외부데이터
    - 서울 열린데이터광장 https://data.seoul.go.kr
    - 부동산 빅데이터 플랫폼 https://www.bigdata-realestate.kr
    - 공공데이터포털 https://www.data.go.kr
    - KB부동산 데이터허브 https://data.kbland.kr
    - KOSIS 국가통계포털 https://kosis.kr
    
* 논문
    - 주정민, 강선미, 최지웅, 한영우, 기계학습을 이용한 아파트 매매가격 예측 연구 : 한국 아파트의 내·외적 데이터 수집과 가격 예측 중심으로(2020.11) https://manuscriptlink-society-file.s3-ap-northeast-1.amazonaws.com/kips/conference/2020fall/presentation/KIPS_C2020B0235.pdf
    
* 대회
    - 데이콘 아파트 실거래가 예측 AI 경진대회 https://dacon.io/competitions/official/21265
