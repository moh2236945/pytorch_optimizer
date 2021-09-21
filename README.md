# pytorch-optimizer

Bunch of optimizer implementations in PyTorch with clean-code, strict types. Highly inspired by [pytorch-optimizer](https://github.com/jettify/pytorch-optimizer).

## Usage

### Install

```
$ pip3 install pytorch-optimizer
```

## Supported Optimizers

| Optimizer | Description | Official Code | Paper |
| :---: | :---: | :---: | :---: |
| AdamP | *Slowing Down the Slowdown for Momentum Optimizers on Scale-invariant Weights* | [github](https://github.com/clovaai/AdamP) | [https://arxiv.org/abs/2006.08217](https://arxiv.org/abs/2006.08217) |
| Chebyshev LR Schedules | *Acceleration via Fractal Learning Rate Schedules* | [~~github~~]() | [https://arxiv.org/abs/2103.01338v1](https://arxiv.org/abs/2103.01338v1) |
| Lookahead | *k steps forward, 1 step back* | [github](https://github.com/alphadl/lookahead.pytorch) | [https://arxiv.org/abs/1907.08610v2](https://arxiv.org/abs/1907.08610v2) |
| RAdam | *On the Variance of the Adaptive Learning Rate and Beyond* | [github](https://github.com/LiyuanLucasLiu/RAdam) | [https://arxiv.org/abs/1908.03265](https://arxiv.org/abs/1908.03265) |
| Ranger | *a synergistic optimizer combining RAdam and LookAhead, and now GC in one optimizer* | [github](https://github.com/lessw2020/Ranger-Deep-Learning-Optimizer) | |
| Ranger21 | *a synergistic deep learning optimizer* | [github](https://github.com/lessw2020/Ranger21) | [https://arxiv.org/abs/2106.13731](https://arxiv.org/abs/2106.13731) |

## Useful Resources

Several optimization ideas to regularize & stabilize the training. Most of the ideas are applied in `Ranger21` optimizer.

Also, most of the captures are taken from `Ranger21` paper.

### Adaptive Gradient Clipping (AGC)

This idea originally proposed in `NFNet (Normalized-Free Network)` paper. 
AGC (Adaptive Gradient Clipping) clips gradients based on the `unit-wise ratio of gradient norms to parameter norms`.

* github : [code](https://github.com/deepmind/deepmind-research/tree/master/nfnets)
* paper : [arXiv](https://arxiv.org/abs/2102.06171)

### Gradient Centralization (GC)

![gradient_centralization](assets/gradient_centralization.png)

Gradient Centralization (GC) operates directly on gradients by centralizing the gradient to have zero mean.

* github : [code](https://github.com/Yonghongwei/Gradient-Centralization)
* paper : [arXiv](https://arxiv.org/abs/2004.01461)

### Soft-plus Transformation

### Gradient Normalization

### Norm Loss

![norm_loss](assets/norm_loss.png)

* paper : [arXiv](https://arxiv.org/abs/2103.06583)

### Positive-Negative Momentum

![positive_negative_momentum](assets/positive_negative_momentum.png)

* github : [code](https://github.com/zeke-xie/Positive-Negative-Momentum)
* paper : [arXiv](https://arxiv.org/abs/2103.17182)

### Linear learning-rate warm-up

![linear_lr_warmup](assets/linear_lr_warmup.png)

* paper : [arXiv](https://arxiv.org/abs/1910.04209)

### Stable weight decay

![stable_weight_decay](assets/stable_weight_decay.png)

* github : [code](https://github.com/zeke-xie/stable-weight-decay-regularization)
* paper : [arXiv](https://arxiv.org/abs/2011.11152)

### Explore-exploit learning-rate schedule

### Lookahead

## Citations

<details>

<summary>AdamP</summary>

```
@inproceedings{heo2021adamp,
    title={AdamP: Slowing Down the Slowdown for Momentum Optimizers on Scale-invariant Weights},
    author={Heo, Byeongho and Chun, Sanghyuk and Oh, Seong Joon and Han, Dongyoon and Yun, Sangdoo and Kim, Gyuwan and Uh, Youngjung and Ha, Jung-Woo},
    year={2021},
    booktitle={International Conference on Learning Representations (ICLR)},
}
```

</details>

<details>

<summary>Adaptive Gradient Clipping (AGC)</summary>

```
@article{brock2021high,
  author={Andrew Brock and Soham De and Samuel L. Smith and Karen Simonyan},
  title={High-Performance Large-Scale Image Recognition Without Normalization},
  journal={arXiv preprint arXiv:2102.06171},
  year={2021}
}
```

</details>

<details>

<summary>Chebyshev LR Schedules</summary>

```
@article{agarwal2021acceleration,
  title={Acceleration via Fractal Learning Rate Schedules},
  author={Agarwal, Naman and Goel, Surbhi and Zhang, Cyril},
  journal={arXiv preprint arXiv:2103.01338},
  year={2021}
}
```

</details>

<details>

<summary>Gradient Centralization (GC)</summary>

```
@inproceedings{yong2020gradient,
  title={Gradient centralization: A new optimization technique for deep neural networks},
  author={Yong, Hongwei and Huang, Jianqiang and Hua, Xiansheng and Zhang, Lei},
  booktitle={European Conference on Computer Vision},
  pages={635--652},
  year={2020},
  organization={Springer}
}
```

</details>

<details>

<summary>Lookahead</summary>

```
@article{zhang2019lookahead,
  title={Lookahead optimizer: k steps forward, 1 step back},
  author={Zhang, Michael R and Lucas, James and Hinton, Geoffrey and Ba, Jimmy},
  journal={arXiv preprint arXiv:1907.08610},
  year={2019}
}
```

</details>

<details>

<summary>RAdam</summary>

```
@inproceedings{liu2019radam,
 author = {Liu, Liyuan and Jiang, Haoming and He, Pengcheng and Chen, Weizhu and Liu, Xiaodong and Gao, Jianfeng and Han, Jiawei},
 booktitle = {Proceedings of the Eighth International Conference on Learning Representations (ICLR 2020)},
 month = {April},
 title = {On the Variance of the Adaptive Learning Rate and Beyond},
 year = {2020}
}
```

</details>

<details>

<summary>Norm Loss</summary>

```
@inproceedings{georgiou2021norm,
  title={Norm Loss: An efficient yet effective regularization method for deep neural networks},
  author={Georgiou, Theodoros and Schmitt, Sebastian and B{\"a}ck, Thomas and Chen, Wei and Lew, Michael},
  booktitle={2020 25th International Conference on Pattern Recognition (ICPR)},
  pages={8812--8818},
  year={2021},
  organization={IEEE}
}
```

</details>

<details>

<summary>Positive-Negative Momentum</summary>

```
@article{xie2021positive,
  title={Positive-Negative Momentum: Manipulating Stochastic Gradient Noise to Improve Generalization},
  author={Xie, Zeke and Yuan, Li and Zhu, Zhanxing and Sugiyama, Masashi},
  journal={arXiv preprint arXiv:2103.17182},
  year={2021}
}
```

</details>

## Author

Hyeongchan Kim / [@kozistr](http://kozistr.tech/about)
