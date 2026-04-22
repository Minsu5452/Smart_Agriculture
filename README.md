# Smart Agriculture

2023 스마트농업 AI 경진대회 참여 저장소입니다. 여러 모델 계열을 빠르게 비교해 문제 특성과 검증 전략을 파악하는 데 초점을 둔 실험 기록입니다.

## Snapshot

| Item | Detail |
| --- | --- |
| Type | Competition project |
| Period | 2023 |
| Team | Team lead |
| Task | 스마트농업 데이터 기반 예측 |
| Approach | AutoML, CatBoost, LightGBM, Optuna, RandomForest |
| Result | Participation record |

## Work Summary

- 서로 다른 모델 계열을 같은 문제에 적용해 기준선을 비교했습니다.
- 범주형 처리와 부스팅 계열 성능을 집중적으로 확인했습니다.
- Optuna 기반 하이퍼파라미터 탐색으로 LightGBM 실험을 확장했습니다.

## Repository Layout

- `Modeling_AutoML.ipynb`
- `Modeling_Catboost.ipynb`
- `Modeling_LGBM.ipynb`
- `Modeling_LGBM_Optuna.ipynb`
- `Modeling_RandomForest.ipynb`
