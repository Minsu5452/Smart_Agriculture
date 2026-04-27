# 스마트팜 수확량·에너지 예측

스마트농업 데이터를 이용해 수확량과 난방 에너지 사용량을 동시에 예측한 multi-target 회귀 프로젝트입니다.

## 개요

| 항목 | 내용 |
| --- | --- |
| 대회 | 2023 스마트농업 AI 경진대회 |
| 기간 | 2023.09.14 - 2023.09.25 |
| 주최 / 주관 | 농림축산식품부 / 농림수산식품교육문화정보원 |
| 결과 | 예선 탈락 |
| 과제 | 수확량과 난방 에너지 누적값 예측 |
| 연계 활동 | BDA 7기 데이터 분석 고급반 |

## 접근

- 단일값 컬럼, 중복 컬럼, 식별자 컬럼을 정리하고 날짜 기반 피처를 만들었습니다.
- 수치형 피처에 `PowerTransformer`를 적용했습니다.
- SHAP 기반 중요도로 타겟별 feature set을 분리했습니다.
- LinearRegression, RandomForest, GradientBoosting, LightGBM, CatBoost, XGBoost를 5-fold로 비교했습니다.
- 최종 후보 모델을 Optuna로 튜닝해 타겟별 RMSE를 확인했습니다.

## 저장소 구성

```text
.
├── notebooks/
│   ├── 01_data_overview.ipynb
│   ├── 02_preprocessing_and_feature_selection.ipynb
│   ├── 03_baseline_model_comparison.ipynb
│   └── 04_optuna_tuning_and_final_evaluation.ipynb
└── requirements.txt
```

## 공개 범위

대회 원본 데이터, 전처리 데이터셋, 학습된 모델 파일은 포함하지 않았습니다. 노트북 출력과 실행 메타데이터를 정리했습니다.
