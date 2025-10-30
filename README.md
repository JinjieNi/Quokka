<div align="center">

<!-- TITLE -->
<p align="center" width="100%">
<img src="resources/imgs/compute_constrained_allocations_ar_and_dlm.png"  width="80%" height="100%">
</p>

**Training Optimal Large Diffusion Language Models**
===========================

<h4>Large-Scale Scaling Laws for Diffusion Language Models.</h4>

[![Static Badge](https://img.shields.io/badge/Paper-2025--09--30-darkcyan)](https://jinjieni.github.io/Quokka/resources/pdfs/Training_Optimal_Large_Diffusion_Language_Models.pdf)
[![Static Badge](https://img.shields.io/badge/Resources-ckpts--logs-green)](#resources)
[![Twitter](https://img.shields.io/twitter/url/https/twitter.com/cloudposse.svg?style=social&label=tweet)](https://x.com/NiJinjie/status/1973031493707645146)



[Jinjie Ni†](https://jinjieni.github.io/), [Qian Liu](https://scholar.google.com/citations?user=bcbeUo0AAAAJ&hl=en), [Chao Du](https://duchao0726.github.io/), [Longxu Dou](https://longxudou.github.io/), [Hang Yan](https://scholar.google.com/citations?user=yigHzW8AAAAJ&hl=en), [Zili Wang](https://commencement.github.io/), [Tianyu Pang](https://p2333.github.io/), [Michael Qizhe Shieh](https://michaelshieh.com/)

†Correspondence to: Jinjie Ni \<jinjieni@nus.edu.sg\>
</div>

# News
[2025-10-27] We release the codebase, all training checkpoints, and logs. The codebase is highly optimized and is industry-level in terms scalability and efficiency.

[2025-10-03] The full paper is out! Check it out [here](https://jinjieni.github.io/Quokka/resources/pdfs/Training_Optimal_Large_Diffusion_Language_Models.pdf)!


<br>

# Code
The codebase is released [here](https://github.com/JinjieNi/MegaDLMs). It is a highly-optimized codebase for any-scale DLMs training.

> You can also use the code under the `mega-dlms` folder of this repo, which might not be actively maintained.

<br>

# Resources

We opensource all model checkpoints and training logs mentioned in the paper. All of them can be downloaded at https://huggingface.co/collections/jinjieni/mdga.

The easiest way to download a folder is using this script (setup the variables properly):
```
python utils/hf_download_folder.py
```

Alternatively, you can also use `wget` to directly download individual files from the folder, e.g.:
```bash
wget https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/batch_size1/1024_96b_1e_1b_ar/tensorboard/events.out.tfevents.1756378168.7837477398
```

We link the related resources below:

- [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/compute_constrained_scaling_law)] Compute-constrained scaling laws
- [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/data_constrained_scaling_law)] Data-constrained scaling laws
- Key Modeling and Optimization Choices
  - Masked and uniform transition kernels
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/mask_vs_uniform/masked_96b_1e_1b_difflm)] masked
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/mask_vs_uniform/uniform_96b_1e_1b_difflm)] uniform
  - diffusion schedules
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/diffusion_schedule1/Cosine_96b_1e_1b_difflm)] cosine
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/diffusion_schedule1/Linear_96b_1e_1b_difflm)] linear
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/diffusion_schedule1/Poly2_96b_1e_1b_difflm)] poly2
  - Uniform 𝑡 vs. clean-to-noisy 𝑡 sampling
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/diffusion_schedule2/Default_96b_1e_1b_difflm)] default
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/diffusion_schedule2/Moving-Gaussian_96b_1e_1b_difflm)] moving gaussian
  - Principled diffusion loss and MaskGIT loss
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/diffusion_loss_formula/Diffusion_300b_1e_1b_difflm)] diffusion
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/diffusion_loss_formula/MaskGIT_300b_1e_1b_difflm)] maskgit
  - Batch size transferability from AR models to DLMs
    - 256
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/batch_size1/256_96b_1e_1b_ar)] AR
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/batch_size2/256_96b_1e_1b_difflm)] DLM
    - 1024
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/batch_size1/1024_96b_1e_1b_ar)] AR
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/batch_size2/1024_96b_1e_1b_difflm)] DLM
    - 4096
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/batch_size1/4096_96b_1e_1b_ar)] AR
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/batch_size2/4096_96b_1e_1b_difflm)] DLM
  - Learning rate transferability from AR models to DLMs
    - 1e-4
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/learning_rate1/1e4_96b_1e_1b_ar)] AR
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/learning_rate2/1e4_96b_1e_1b_difflm)] DLM
    - 2e-4
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/learning_rate1/2e4_96b_1e_1b_ar)] AR
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/learning_rate2/2e4_96b_1e_1b_difflm)] DLM
    - 4e-4
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/learning_rate1/4e4_96b_1e_1b_ar)] AR
      - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/learning_rate2/4e4_96b_1e_1b_difflm)] DLM
  - The impact of weight decay on AR models in single epoch scenarios
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/weight_decay3/with_96b_1e_1b_ar)] with
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/weight_decay3/without_96b_1e_1b_ar)] without
  - The impact of weight decay on DLMs in single epoch scenarios
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/weight_decay4/with_96b_1e_1b_difflm)] with
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/weight_decay4/without_96b_1e_1b_difflm)] without
  - The impact of weight decay on AR models in multi-epoch scenarios
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/weight_decay1/with_1b_96e_1b_ar)] with
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/weight_decay1/without_1b_96e_1b_ar)] without
  - The impact of weight decay on DLMs in multi-epoch scenarios
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/weight_decay2/with_1b_96e_1b_difflm)] with
    - [[ckpt]()][[log](https://huggingface.co/datasets/MDGA-1/quokka_logs/tree/main/weight_decay2/without_1b_96e_1b_difflm)] without

You can refer to [this](https://github.com/JinjieNi/MegaDLMs/blob/main/examples/dlm_generation/dlm_inference.py) script to generate with the huggingface checkpoints. Due to the large amount, most small checkpoints above are still in megatron formats. You may refer to [this](https://github.com/JinjieNi/MegaDLMs/blob/main/examples/dlm_training/ckpt_conversion.sh) script to convert them (need to tweak the conversion scripts).

<br>

# Citation
```
@article{ni2025training,
  title={Training Optimal Large Diffusion Language Models},
  author={Ni, Jinjie and Liu, Qian and Du, Chao and Dou, Longxu and Yan, Hang and Wang, Zili and Pang, Tianyu and Shieh, Michael Qizhe},
  journal={arXiv preprint arXiv:2510.03280},
  year={2025}
}
```
