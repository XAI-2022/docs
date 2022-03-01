# Literature | Machine Learning Robustness | Bit Flip attacks

* **Review Paper** (2020): [A Review of Deep Learning Security and Privacy Defensive Techniques](https://www.hindawi.com/journals/misy/2020/6535834/)
---
* (Hanif et al, 2018) [Robust Machine Learning Systems: Reliability and Security for Deep Neural Networks](https://ieeexplore.ieee.org/document/8474192)
   * Motiv: Need for Robsut ML and HW for reliable results when HW faults + privacy + security.
   * shows challenges for robustness (reliability and security) and SOTA techniques for analysis and mitigation of threats
   * Reliability threats = faults in HW = (1) soft errors (bit flips by ex/internal factors), (2) aging (circuit degredation overtime), (3) Process variations (silicon fabrication imperfections), (4) Temperature (higher  = more aging and soft errors)
   * Prev methods in detection of faults are based on redundancy technique
   * Reliability Experiment: shows how # of bit-flip injections and their locations in floating point bits (for VGG-f network's 1st layer weights) decreased accuracy on ImageNet validation set. Result: **0-to-1 flip is worse**. **flipping higher exponent bits of floating points are worse**. 
   * provided design-time and run-time methodology for reliabile ML systems
   * they showed same analysis on security aspect :D but out of our scope for now
   * **Limitations (in my opinion): only tried VGG and Imagenet. How about: 1) other nets? 2) models with Batch-Norm / dropout layers? 3) bit-flip in activation values, not weights? 4) non-floating quantized networks? 5) non-HW mitigation methods like inherently robust models?** 
* (Schorn et al, 2019) [An Efficient Bit-Flip Resilience Optimization Method for Deep Neural Networks Christoph](https://ieeexplore.ieee.org/document/8714885)
---
* (Rakin et al, 2019) [Bit-Flip Attack: Crushing Neural Network with Progressive Bit Search](https://openaccess.thecvf.com/content_ICCV_2019/papers/Rakin_Bit-Flip_Attack_Crushing_Neural_Network_With_Progressive_Bit_Search_ICCV_2019_paper.pdf)
* (Rakin et al, 2020) [TBT: Targeted Neural Network Attack with Bit Trojan](https://arxiv.org/abs/1909.05193)
* (Rakin et al, 2021) [T-BFA: Targeted Bit-Flip Adversarial Weight Attack](https://arxiv.org/abs/2007.12336)
---
* (Ghavami et al, 2021) [Stealthy Attack on Algorithmic-Protected DNNs via Smart Bit Flipping](https://arxiv.org/abs/2112.13162)
* (Ghavami et al, 2021) [BDFA: A Blind Data Adversarial Bit-flip Attack on Deep Neural Networks](https://arxiv.org/abs/2112.03477)
---
* (He et al, 2020) [Defending and Harnessing the Bit-Flip based Adversarial Weight Attack](https://openaccess.thecvf.com/content_CVPR_2020/papers/He_Defending_and_Harnessing_the_Bit-Flip_Based_Adversarial_Weight_Attack_CVPR_2020_paper.pdf)
  * **Overview**:
  * **Limitations**:  
* (Liu et al, 2020) [Concurrent Weight Encoding-based Detection for Bit-Flip Attack on Neural Network Accelerators](https://ieeexplore.ieee.org/document/9256559)
* (Yao et al, 2020) [DeepHammer: Depleting the Intelligence of Deep Neural Networks through Targeted Chain of Bit Flips](https://www.usenix.org/conference/usenixsecurity20/presentation/yao)
  * **Motivation:** ML as service deployed in more places, internal threats (adversarial tampering of ML model+parameters) still vulnerable. Internal threats include RowHammer in DRAM (worse problem as DRAM gets denser). Quantized DNN are widely deployed for their efficiency and they're known to be robust against bit-flips (99% of the time there are no accuracy changes)
  * **Question**: Uses an *untargeted* attack to deplete accuarcy of network to random guess, how vulnerable is quantized DNN to bit flips.
  * **Observations**: randomized bitflips will not work, we must look for targeted bits to flip
  * To achive the attack, we must find the bits that are most likely to swing the output
    * Use gradient to find the most influential bit, then rank. Check that those bits can be flipped based on DRAM configuration
  * **Limitations**: adversary requires lots of prior knowledge:
    * Precise system configuration, virtual-physical memory mapping, requires attacker to find these information *offline*
    * Finding most vulnerable bits required knowlege of the model architecture and parameters (white-box attack)
    * Attack is untargeted, but the outcome tends to favour a *winner-group* -- detection of attack may be easier.
  * **Question**: has such techniques been used on sparse networks where non-important weights have already been pruned?
* (Chen et al, 2021) [ProFlip: Targeted Trojan Attack with Progressive Bit Flips](https://openaccess.thecvf.com/content/ICCV2021/papers/Chen_ProFlip_Targeted_Trojan_Attack_With_Progressive_Bit_Flips_ICCV_2021_paper.pdf)
* (Li et al, 2021) [RADAR: Run-time Adversarial Weight Attack Detection and Accuracy Recovery](https://arxiv.org/abs/2101.08254)
  * **General Idea**: Rather than improving robustness during the network design or training stages, this paper focusses on detecting bit flips during inference through checksums. Checksums are computed using a secret key for the DRAM weights. When bitflips are detected, accuracy can be recovered by settind affected weights to zero. 
  *  **Limitations**: Recovery doesn't completely recover original 'clean' accuracy. There is also a runtime overhead. 
* (Park et al, 2021) [ZeBRA: Precisely Destroying Neural Networks with Zero-Data Based Repeated Bit Flip Attack](https://arxiv.org/abs/2111.01080#:~:text=version%2C%20v2)
* (Bai et al, 2021) [TARGETED ATTACK AGAINST DEEP NEURAL NET- WORKS VIA FLIPPING LIMITED WEIGHT BITS](https://arxiv.org/abs/2102.10496)
* (Park et al, 2021) [Mind control attack: Undermining deep learning with GPU memory exploitation](https://www.sciencedirect.com/science/article/pii/S0167404820303886)

---

- (Hong et al, 2019) [Terminal Brain Damage: Exposing the Graceless Degradation in Deep Neural Networks Under Hardware Fault Attacks](https://arxiv.org/abs/1906.01017)
  - **Motivation & Q**: how does DNN react to bit flips, and properties of bit-flips (position, flip-direction) that affect the output accuracy the most
  - Observation:
    - Around half of DNNs (non-quantized non sparse) parameters are vulnerable to bit flips that cause +10% accuracy drop; caused by spikes of parameter value
    - All models contain "critical parameters" that cause +90% accuracy drop -- drop out and batch normalization is ineffective in mitigating the vulnerabiltiy -- this makes since since these techniques don't affect the "critical parameters" anyway.
