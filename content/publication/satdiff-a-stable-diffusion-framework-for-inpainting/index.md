---
title: "SatDiff: A Stable Diffusion Framework for Inpainting Very High-Resolution Satellite Imagery"
authors:
- admin
- C. Satirapod

date: "2025-03-13T00:00:00Z"
doi: ""

author_notes:
- ""
- ""
- ""
- ""
- ""
- ""
- ""
- ""

# Schedule page publish date (NOT publication's date).
publishDate: "2025-03-13T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication: IEEE Access 2025
publication_short: IEEE Access 2025

abstract: Satellite image inpainting is a critical task in remote sensing, requiring accurate restoration of missing or occluded regions for reliable image analysis. In this paper, we present SatDiff, an advanced inpainting framework based on diffusion models, specifically designed to tackle the challenges posed by very high-resolution (VHR) satellite datasets such as DeepGlobe and the Massachusetts Roads Dataset. Building on insights from our previous work, SatInPaint, we enhance the approach to achieve even higher recall and overall performance. SatDiff introduces a novel Latent Space Conditioning technique that leverages a compact latent space for efficient and precise inpainting. Additionally, we integrate Explicit Propagation into the diffusion process, enabling forward-backward fusion for improved stability and accuracy. Inspired by encoder-decoder architectures like the Segment Anything Model (SAM), SatDiff is seamlessly adaptable to diverse satellite imagery scenarios. By balancing the efficiency of preconditioned models with the flexibility of postconditioned approaches, SatDiff establishes a new benchmark in VHR satellite datasets, offering a scalable and high-performance solution for satellite image restoration. The code for SatDiff is publicly available at https://github.com/kaopanboonyuen/SatDiff.

# Summary. An optional shortened abstract.
summary: Satellite image inpainting is a critical task in remote sensing, requiring accurate restoration of missing or occluded regions for reliable image analysis. In this paper, we present SatDiff, an advanced inpainting framework based on diffusion models, specifically designed to tackle the challenges posed by very high-resolution (VHR) satellite datasets such as DeepGlobe and the Massachusetts Roads Dataset. Building on insights from our previous work, SatInPaint, we enhance the approach to achieve even higher recall and overall performance. SatDiff introduces a novel Latent Space Conditioning technique that leverages a compact latent space for efficient and precise inpainting. Additionally, we integrate Explicit Propagation into the diffusion process, enabling forward-backward fusion for improved stability and accuracy. Inspired by encoder-decoder architectures like the Segment Anything Model (SAM), SatDiff is seamlessly adaptable to diverse satellite imagery scenarios. By balancing the efficiency of preconditioned models with the flexibility of postconditioned approaches, SatDiff establishes a new benchmark in VHR satellite datasets, offering a scalable and high-performance solution for satellite image restoration. The code for SatDiff is publicly available at https://github.com/kaopanboonyuen/SatDiff.

tags:
- Satellite Image Inpainting
- Diffusion Models
- Latent Space Conditioning
- VHR Satellite Datasets
- Image Restoration

featured: true

links:
- name: ArXiv
  url: 'https://arxiv.org/'
# - name: Certificate
#   url: 'https://kaopanboonyuen.github.io/files/certificate/KST2025/Panboonyuen-Certificate-of-Contributions-53.pdf'
# - name: ICML talk
#   url: https://www.facebook.com/watch/live/?v=355035025132741&ref=watch_permalink
# - name: IEEE Spectrum article
#   url: https://spectrum.ieee.org/tech-talk/computing/software/deepmind-teaches-ai-teamwork
# - name: ICIAP 2017 Best Papers
#   url: https://link.springer.com/chapter/10.1007/978-3-319-60663-7_18
url_pdf: 'https://ieeeaccess.ieee.org/featured-articles/'
url_code: 'https://github.com/kaopanboonyuen/SatDiff'
url_dataset: ''
# url_poster: 'https://kaopanboonyuen.github.io/REG/'
url_project: 'https://github.com/kaopanboonyuen/SatDiff'
# url_slides: 'https://kaopanboonyuen.github.io/files/slides/20240906_Panboonyuen_AI_ThaiHighway.pdf'
# url_source: 'https://kaopanboonyuen.github.io/blog/2024-09-07-refined-generalized-focal-loss-for-road-asset-detection-on-thai-highways-using-vision-models/'
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: ''
  focal_point: Center
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

![](featured.png)

## Keywords

- Diffusion Models
- High-Resolution Satellite Imagery
- Inpainting
- Latent Space Conditioning
- Remote Sensing
- Stable Diffusion
- Satellite Image Restoration
- Very High-Resolution Images

## Introduction

Satellite image inpainting is a crucial process in remote sensing, aimed at recovering missing or damaged areas to ensure precise data analysis. Satellite images are often affected by occlusions from factors like clouds, atmospheric disturbances, or physical obstructions, making it challenging to obtain fully clear and complete data. To overcome these challenges, especially in high-resolution satellite imagery, effective inpainting methods are required that can reconstruct the missing portions while maintaining the overall structural coherence of the image.

Diffusion models have emerged as powerful tools in image inpainting, representing a significant advancement in the field. They have been applied to a wide array of tasks, such as object removal, generative inpainting with contextual attention, and addressing semantic differences between masked and unmasked regions. These models excel in maintaining structural consistency while producing high-quality restorations, making them effective for complex tasks, such as video inpainting, text-based object removal, and sketch-based inpainting.

![](main_arch_01.png)

In recent years, diffusion models have become prominent for image inpainting due to their ability to generate high-fidelity results. Traditionally, inpainting with diffusion models has been approached through either preconditioned or postconditioned techniques. Preconditioned models are designed explicitly for inpainting tasks, enabling efficient inference but requiring extensive domain-specific training. In contrast, postconditioned models do not necessitate retraining but involve slower inference, as they rely on multiple forward-backward iterations to achieve optimal solutions.

The two primary strategies—preconditioning and postconditioning—differ in how they incorporate inpainting into diffusion models. Preconditioning integrates inpainting into the training phase, where a conditional model predicts missing regions based on the masked input. While effective for specific domains, this approach requires retraining for new applications. Postconditioning, on the other hand, employs an unconditioned generative model, applying forward diffusion to unmasked pixels and reverse diffusion to fill in masked areas. Although this eliminates the need for retraining, it is computationally intensive, requiring numerous diffusion passes to refine the final image.

Achieving effective image inpainting requires seamless propagation of information from unmasked to masked regions to ensure semantic consistency and a coherent final image. Inspired by our previous work, SatInPaint, we introduce **SatDiff**, a novel diffusion-based framework that builds on this foundation to achieve improved recall and overall performance. SatDiff employs a **Latent Space Conditioning** approach to facilitate inpainting within the latent space, rather than the image space, enabling efficient and precise reconstruction. Additionally, we integrate a forward-backward fusion mechanism within the latent space, enhancing stability and accuracy. SatDiff further incorporates the **Segment Anything Model (SAM)** to refine the propagation process, boosting reconstruction quality and preserving semantic coherence.

![](main_arch_02.png)

Through extensive experimentation on very high-resolution (VHR) satellite datasets, including DeepGlobe and the Massachusetts Roads Dataset, we validate the contributions of each component in our proposed method. Our results demonstrate that SatDiff not only surpasses state-of-the-art methods in inpainting accuracy and runtime efficiency but also excels in reconstructing realistic satellite images that closely resemble the ground truth. Building on the strengths of SatInPaint, SatDiff sets a new benchmark for high-quality and scalable satellite image restoration solutions.

## Results and Examples

![](satdif_result_01.png)
![](satdif_result_02.png)
![](satdif_result_03.png)

### Satellite Image Inpainting Results

We present examples of satellite image inpainting results across different object sizes. The comparison showcases the input images (with occlusions), the ground truth targets (without occlusions), and the outputs generated by our method, SatDiff. These results highlight SatDiff's capability to address real-world challenges, such as reconstructing satellite imagery obscured by clouds or other obstacles, with high accuracy.

## Conclusion

In this work, we introduced **SatDiff**, a novel framework for satellite image inpainting based on diffusion models. By incorporating Latent Space Conditioning and Explicit Propagation, SatDiff achieves improved accuracy and efficiency for high-resolution satellite datasets. The results demonstrate the effectiveness of the proposed method in addressing real-world satellite inpainting challenges.

For more details, visit the official [SatDiff GitHub repository](https://github.com/kaopanboonyuen/SatDiff).