# Smart Agriculture

> 2023 스마트농업 AI 경진대회 참여 프로젝트입니다. 농가 운영 데이터로부터 **수확량(outtrn_cumsum)** 과 **난방 에너지 사용량(HeatingEnergyUsage_cumsum)** 두 누적 타겟을 동시에 예측하는 multi-target 회귀 문제로, SHAP 기반 피처 선택과 5-fold CV 모델 비교, Optuna 튜닝을 단계별로 정리했습니다.

## Overview

| 항목 | 내용 |
| --- | --- |
| 대회 | 2023 스마트농업 AI 경진대회 |
| 기간 | 2023.09.14 ~ 2023.09.25 |
| 주최 | 농림축산식품부 |
| 주관 | 농림수산식품교육문화정보원 |
| 팀 구성 | 4인팀, 팀장 |
| 결과 | 예선 탈락 |
| 과제 | 농가 운영 데이터 기반 수확량 / 난방 에너지 누적값 예측 (multi-target 회귀) |
| 연계 활동 | BDA 7기 데이터 분석 고급반 |

## Approach

- 단일값 컬럼·중복 컬럼·농가 식별자를 정리하고 `date` 에서 시간 파생 피처를 생성했습니다.
- 수치형 피처에 `PowerTransformer` 를 적용해 분포를 정규화했습니다.
- SHAP TreeExplainer 기반 피처 중요도 누적 비율(99%) 기준으로 타겟별 피처 셋을 분리했습니다 (`X_yield`, `X_energy`).
- LinearRegression / RandomForest / GradientBoosting / LightGBM / CatBoost / XGBoost 를 5-fold KFold 로 비교해 분산까지 함께 보고 후보를 선별했습니다.
- 최종 모델 LightGBM 을 두 타겟 각각에 대해 Optuna(TPE) 50 trial 로 튜닝하고 베이스라인 대비 RMSE 향상 폭을 정리했습니다.

## Repository Structure

```text
.
├── notebooks/
│   ├── 01_data_overview.ipynb
│   ├── 02_preprocessing_and_feature_selection.ipynb
│   ├── 03_baseline_model_comparison.ipynb
│   └── 04_optuna_tuning_and_final_evaluation.ipynb
├── requirements.txt
└── README.md
```

## Public Scope

이 저장소는 포트폴리오 공개용으로 정리한 버전입니다.

- 대회 제공 원본 데이터셋과 전처리 산출물(`data/processed/`), 학습된 모델 파일은 포함하지 않았습니다.
- 노트북 출력 결과와 실행 메타데이터는 제거했습니다.
- 이전 버전의 단일 노트북 5개(`Modeling_AutoML.ipynb` 등)는 EDA·전처리·모델별 비교가 매번 중복되어 있어, 4단계 단일 흐름 노트북으로 재구성했습니다.
- 실행하려면 대회 데이터(`2023_smartFarm_AI_hackathon_dataset.csv`)를 `data/` 경로에 별도로 배치해야 합니다.
