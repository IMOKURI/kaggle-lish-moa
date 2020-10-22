# lish-moa

## Notebook


### Ensemble Base


#### Version 21


##### Update PCA parameters

```
variance_threshould = 0.7
ncompo_genes = 80
ncompo_cells = 10
```

##### Clipping threshold

`1e-7` to `1.0 / len(train)` (so `1 / 23814 == 4.1992105484168974e-05`)

##### Update TabNet parameters

before

```
num_layers=2,
feature_dim=1024,
output_dim=1024,
```

after

```
num_layers=1,
feature_dim=64,
output_dim=64,
```


