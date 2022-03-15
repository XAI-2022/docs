This document contains a list of literature reviews

## Survey/Review Papers

| Paper                                                        | Authors      | Published                       | Year | Citations | Note                                                         |
| ------------------------------------------------------------ | ------------ | ------------------------------- | ---- | --------- | ------------------------------------------------------------ |
| [A survey on modeling and improving reliability of DNN algorithms and accelerators][17] | Mittal       | Journal of Systsms Architecture | 2020 | 41        | Include studies of other hardware faults in accelerators. [See notes](readings/mittal-survey.md) |
| [Robust Machine Learning Systems: Reliability and Security for Deep Neural Networks][1] | Hanif et al. | IOLTS                           | 2018 | 26        |                                                              |
| [A Review of Deep Learning Security and Privacy Defensive Techniques][19] | Tariq        | Mobile Information Systems      | 2020 | 16        |                                                              |

## Attack Papers

| Paper                                                        | Authors        | Published                    | Year | Citations | Note                                       |
| ------------------------------------------------------------ | -------------- | ---------------------------- | ---- | --------- | ------------------------------------------ |
| [TBT][3]                                                     | Rakin et al.   | ICCV                         | 2019 | 92        |                                            |
| [Terminal brain damage][15]                                  | Hong et al.    | USEINX Security              | 2019 | 83        |                                            |
| [DeepHammer][9]                                              | Yao et al.     | USENIX Security              | 2020 | 41        |                                            |
| [T-BFA][4]                                                   | Rakin et al.   | TPAMI                        | 2021 | 21        |                                            |
| [Targeted Attack against Deep Neural Networks via Flipping Limited Weight Bits][13] | Bai et al.     | ---                          | 2021 | 14        |                                            |
| [Stealthy Attack no Algorithmic-Protected DNNs via Smart Bit Flipping][5] | Ghavami et al. | ---                          | 2021 | 0         |                                            |
| [BDFA][6]                                                    | Ghavami et al. | ---                          | 2021 | 0         |                                            |
| [ProFlip][10]                                                | Chen et al.    | ICCV                         | 2021 | 1         |                                            |
| [ZeBRA][12]                                                  | Park et al.    | ---                          | 2021 | 0         |                                            |
| [Mind control][14]                                           | Park et al.    | Journal: Computer & Security | 2021 | 1         | Other hardware fault attack via GPU memory |

## Defense Papers

Defenses against bit-flip fault attacks on DNNs belong to one of serveral layers (here listed from low-level to high level):

- Memory hardware level mitigation; attempts to close vulnerability that a bit could flipped via physical redesigns (e.g. SRAM)

- Memory hardware level detection and correction (e.g. ECC memory)

- Register/architectural level mitigation: (e.g. preventing attacks like RowHammer)

- OS 

  

| Paper                                                        | Authors       | Published | Year | Citations | Note                                                |
| ------------------------------------------------------------ | ------------- | --------- | ---- | --------- | --------------------------------------------------- |
| [TRRespass][16]                                              | Frigo et al.  | SP        | 2020 | 75        | Hardware-level defense against RowHammer in general |
| [BinFI][18]                                                  | Chen et al.   | SC        | 2019 | 32        |                                                     |
| [Defending and Harnessing the Bit-Flip based Adversarial Weight Attack][7] | He et al.     | CVPR      | 2020 | 28        |                                                     |
| [An Efficient Bit-Flip Resilience Optimization Method for Deep Neural Networks][2] | Schorn et al. | DATE      | 2019 | 10        |                                                     |
| [Concurrent Weight Encoding-based Detection for Bit-Flip Attack on Neural Network Accelerators][8] | Liu et al.    | ICCAD     | 2020 | 3         |                                                     |
| [RADAR][11]                                                  | Li et al.     | DATE      | 2021 | 5         |                                                     |

### Existing Features of DNNs that are resilient against faults

- **Computation**: normalization, ReLU, max-pooling
- **Training**: retraining network, dropout training, [DropConnect][20]




[1]: <https://ieeexplore.ieee.org/document/8474192> "Robust Machine Learning Systems: Reliability and Security for Deep Neural Networks"
[2]: <https://ieeexplore.ieee.org/document/8714885> "An Efficient Bit-Flip Resilience Optimization Method for Deep Neural Networks"
[3]: <http://openaccess.thecvf.com/content_ICCV_2019/papers/Rakin_Bit-Flip_Attack_Crushing_Neural_Network_With_Progressive_Bit_Search_ICCV_2019_paper.pdf> "Bit-flip attack: Crushing neural network with progressive bit search"
[4]: <https://ieeexplore.ieee.org/document/9540274/?casa_token=ZiJggSz2BtcAAAAA:KF5e9GVXDtrPpOq18s8S8GQpJKEH3Xum5vtcmqkmJFMeNGUoawRkkUQKayrCLGr6NCLXlKsD> "T-bfa: Targeted bit-flip adversarial weight attack"
[5]: <https://arxiv.org/abs/2112.13162> "Stealthy Attack on Algorithmic-Protected DNNs via Smart Bit Flipping"
[6]: <https://arxiv.org/abs/2112.03477> "BDFA: A Blind Data Adversarial Bit-flip Attack on Deep Neural Networks"

[7]: <https://openaccess.thecvf.com/content_CVPR_2020/papers/He_Defending_and_Harnessing_the_Bit-Flip_Based_Adversarial_Weight_Attack_CVPR_2020_paper.pdf> "Defending and Harnessing the Bit-Flip based Adversarial Weight Attack"
[8]: <https://ieeexplore.ieee.org/document/9256559> "Concurrent Weight Encoding-based Detection for Bit-Flip Attack on Neural Network Accelerators"
[9]: <https://www.usenix.org/conference/usenixsecurity20/presentation/yao> "DeepHammer: Depleting the Intelligence of Deep Neural Networks through Targeted Chain of Bit Flips"
[10]: <http://openaccess.thecvf.com/content/ICCV2021/html/Chen_ProFlip_Targeted_Trojan_Attack_With_Progressive_Bit_Flips_ICCV_2021_paper.html> "ProFlip: Targeted Trojan Attack with Progressive Bit Flips"
[11]: <https://ieeexplore.ieee.org/abstract/document/9474113/?casa_token=oHrm1cj7cDIAAAAA:n9lfGRu7WJIv_wP8GY78Xt24Y54VjVRH0ct6_3TOqLBSMPjpWeBMTgf5gvkXtshQLGmyfjl7> "RADAR: Run-time Adversarial Weight Attack Detection and Accuracy Recovery"
[12]: <https://arxiv.org/abs/2111.01080> "[ZeBRA: Precisely Destroying Neural Networks with Zero-Data Based Repeated Bit Flip Attack](https://arxiv.org/abs/2111.01080)"
[13]: <https://arxiv.org/abs/2102.10496> "Targeted Attack against Deep Neural Networks via Flipping Limited Weight Bits"
[14]: <https://www.sciencedirect.com/science/article/pii/S0167404820303886> "Mind control attack: Undermining deep learning with GPU memory exploitation"
[15]: <https://www.usenix.org/conference/usenixsecurity19/presentation/hong> "Terminal Brain Damage: Exposing the Graceless Degradation in Deep Neural Networks Under Hardware Fault Attacks"
[16]: <https://ieeexplore.ieee.org/abstract/document/9152631?casa_token=JXMz283XFL4AAAAA:MSitDtaMstDq9QScaNYCwDBAK9_fQIYxN_iPUhsyuxJevjiTGzB8FmVH60pjc5bESn3NwM6g> "TRRespass: Exploiting the Many Sides of Target Row Refresh"
[17]: <https://www.sciencedirect.com/science/article/pii/S1383762119304965> "A survey on modeling and improving reliability of DNN algorithms and accelerators"
[18]: <https://dl.acm.org/doi/abs/10.1145/3295500.3356177> "*BinFI*: an efficient fault injector for safety-critical machine learning systems"
[19]: <https://www.hindawi.com/journals/misy/2020/6535834/> "A Review of Deep Learning Security and Privacy Defensive Techniques"
[20]: <https://proceedings.mlr.press/v28/wan13.html> "Regularization of Neural Networks using DropConnect"

