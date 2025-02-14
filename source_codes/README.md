# PAAR

This repository contains our implementation of paper **Multi-hop Knowledge Graph Reasoning Based on Hyperbolic Knowledge Graph Embedding and Reinforcement Learning** _Xingchen Zhou, Peng Wang, Qiqing Luo, Zhe Pan_

## 1. Dependencies

- Python 3.6+
- Pytorch 1.0+

## 2. Results

The results of _PAAR_ on _FB15k-237-20%_ and _NELL23K_ are shown as follows.
| Datasets | MRR | H@13 | H@10 |
| --------- | ---- | ---- | ---- |
| FB15k-237-20% | .241 | .263 | .375 |
| NELL23K | .184 | .202 | .309 |

## 3. Instructions for running

To analyze **PAAR**'s performance on the datasets, please run our code as follows.

### 3.1 Data Process

```python
./experiment.sh configs/<dataset>.sh --process_data <gpu-ID>

./experiment.sh configs/fb15k-237-20.sh --process_data 0
```

### 3.2 Hyperbolic Knowledge Graph Embedding

```python
./experiment-emb.sh configs/<dataset>-conve.sh --train <gpu-ID>

./experiment-emb.sh configs/fb15k-237-20-conve.sh --train 0
```

### 3.3 Train

```python

./experiment-rs.sh configs/<dataset>-rs.sh --train <gpu-ID>

./experiment-rs.sh configs/<dataset>-rs.sh --train 0
```

### 3.4 Test

```python
./experiment-rs.sh configs/<dataset>-rs.sh --inference <gpu-ID>
```

## 4. Acknowledgement

We refer to the code of [DacKGR](https://github.com/THU-KEG/DacKGR). Thanks for their contributions.

## 5. Licences

Every source code file written exclusively by the author of this repo is licensed under Apache License Version 2.0. For more information, please refer to the [license](https://github.com/prokolyvakis/hyperkg/blob/master/LICENSE).
