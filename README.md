# 🌾 Smart Agriculture — 2023 스마트농업 AI 경진대회

![Host](https://img.shields.io/badge/Host-농림축산식품부-green)
![BDA](https://img.shields.io/badge/BDA%207기-연관%20활동-blue)
![Role](https://img.shields.io/badge/Role-팀장-orange)

> **농림축산식품부 주최 2023 스마트농업 AI 경진대회** · **BDA 7기 연관 활동**. AutoML · CatBoost · LightGBM · RandomForest 5-model 비교 실험.

---

## 🎯 Competition

- **대회**: 2023 스마트농업 AI 경진대회
- **주최**: 농림축산식품부
- **연관**: BDA(빅데이터 연합 대외 동아리) 7기 고급반 연관 활동
- **역할**: 팀장
- **결과**: 예선 참여

## 🔍 Overview

- **배경**: 스마트농업에서 AI 모델 성능 경쟁. 다양한 ML 모델 비교·앙상블로 일반화 성능 확보가 핵심.
- **문제**: 농작물/환경 데이터 기반 회귀·분류 예측.

## 🧠 Approach — 5-Model Benchmark

| 모델 | 목적 |
|------|------|
| **AutoML** | Baseline 성능 확보 |
| **CatBoost** | 범주형 특성 강점 |
| **LightGBM** | 빠른 학습·효율성 |
| **LightGBM + Optuna** | 하이퍼파라미터 최적화 |
| **RandomForest** | 비교 모델 |

## 📁 Structure

```
Smart_Agriculture/
├── Modeling_AutoML.ipynb
├── Modeling_Catboost.ipynb
├── Modeling_LGBM.ipynb
├── Modeling_LGBM_Optuna.ipynb   # Optuna hyperparameter tuning
├── Modeling_RandomForest.ipynb
└── README.md
```

## 🛠 Tech Stack

- Python · CatBoost · LightGBM · scikit-learn · Optuna · AutoML · Jupyter

---

> 🔗 Portfolio: [Minsu5452](https://github.com/Minsu5452)
