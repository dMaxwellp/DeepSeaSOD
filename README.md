# DeepSeaSOD (Deepsea Salient Object Detection Dataset)
Underwater salient object detection (USOD) is challenged by frequent object scale variation and distance-dependent image degradation, where scattering blur and light attenuation jointly hinder robust saliency inference. Existing ConvNet-based USOD models typically rely on fixed effective receptive fields (ERFs), making them ill-suited to balancing long-range context aggregation and detail preservation for scale variations. To address this issue, we introduce the modulation of ERFs in the pure ConvNet USOD architecture design for the first time, inspired by the octopus’s vision. We further observe two phenomena: 1) there exists an inherent trade-off between scattering-induced blurriness and direct light attenuation within ERFs, 2) the limited ERF prevents USOD models from covering objects across the wide range of scales present in underwater scenes. Building on these observations, we propose EPRNet, an ERF-guided pure ConvNet for USOD. Specifically, an ERF Resolution Matching Module (ERMM) performs resolution-aware ERF modulation with large kernels, while a vision aggregation feed-forward network (VAFN) suppresses redundant responses and a Parallel Resolution Interaction (PRI) backbone exchanges complementary information between adjacent resolution branches. Extensive experiments on underwater benchmarks demonstrate the effectiveness of EPRNet in handling scale variation. To further validate EPRNet, we introduce DeepseaSOD , a real deep-sea image dataset collected during multiple South China Sea expeditions for evaluating USOD in extreme deep-sea operational scenarios.

## Dataset Structure

```text
DeepseaSOD/
  JPEGImages/
    1.jpg
    2.jpg
    ...
  SegmentationClass/
    1.png
    2.png
    ...
```

Files with the same numeric stem form one image/annotation pair. For example, `JPEGImages/1.jpg` corresponds to `SegmentationClass/1.png`.

The annotations in `SegmentationClass` are binary masks stored as single-channel PNG files:

- `0`: background
- `1`: foreground

## Acknowledgement

The public release of the DeepseaSOD dataset is only for academic purposes and excludes a subset of images that cannot be made public due to confidentiality requirements of projects conducted with the Institute of Deep-sea Science and Engineering, Chinese Academy of Sciences.

We sincerely thank the Institute of Deep-sea Science and Engineering, Chinese Academy of Sciences, for providing the data and for their assistance in completing this work.

```
@article{DeepSeaSOD,
  title={An Effective Receptive Field-Guided Parallel Resolution ConvNet for Underwater Salient Object Detection},
  author={Zhu, Haodi and Su, Jiayi and Zhou, Xinyi and Yang, Shaojian and Han, Haibin and Wang, Wenchu and Feng, Jiayi and Wei, Yan and Qu, Fengzhong},
  journal={IEEE Journal of Oceanic Engineering},
  month={May},
  year={2026}
}
```
