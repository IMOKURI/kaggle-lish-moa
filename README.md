# Kaggle - Mechanisms of Action (MoA) Prediction

## Score


| Version | Private LB | Public LB | CV                  | AUC                | CV Strategy | Fold | Seed | Execution Time | Blend Weight                       |
| ---     | ---        | ---       | ---                 | ---                | ---         | ---  | ---  | ---            | ---                                |
| v128    | 0.01622    | 0.01840   | 0.01661682437083058 | 0.6732857787671046 | new         | 5    | 4    | 5898s          | [0.48228004 0.29394546 0.2237745 ] |
| v131    | 0.01618    | 0.01836   | 0.01512241439772212 | 0.8415474216651967 | old         | 7    | 2    | 5964s          | average                            |


## Basic Strategy

- Preprocessing
    - Remove `ctrl_vehicle`
    - RankGauss
    - PCA + Existing Features
    - KMeans
    - Basic stats
- Model
    - Multi head ResNet (tensorflow)
    - TabNet (pytorch)
    - NODE - Neural Oblivious Decision Ensembles (tensorflow)
- Training
    - Pre-train with scored and non-scored target
    - Train with public test pseudo label
    - Add swap noise for train data
    - Optimizer: Adam/AdamW with `weight_decay`
    - Loss: BCE with Label smoothing + Logits
- Prediction
    - Ensemble above with weight optimization


## Review







