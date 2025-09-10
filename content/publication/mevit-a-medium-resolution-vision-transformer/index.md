---
title: "MeViT: A Medium-Resolution Vision Transformer for Semantic Segmentation on Landsat Satellite Imagery for Agriculture in Thailand"
authors:
- admin
- C. Charoenphon
- C. Satirapod

date: "2023-05-01T00:00:00Z"
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
publishDate: "2023-05-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication: In *Remote Sensing (Supported by Ratchadapisek Somphot Postdoctoral Fund, 2022–2024)*
publication_short: In *Remote Sensing (Supported by Ratchadapisek Somphot Postdoctoral Fund, 2022–2024)*

abstract: Semantic segmentation is crucial in remote sensing for classifying each pixel in images into land use and land cover (LULC) categories. This paper presents MeViT (Medium-Resolution Vision Transformer), designed for key economic crops in Thailand such as para rubber, corn, and pineapple. MeViT enhances vision transformers by integrating medium-resolution multi-branch architectures, allowing for semantically rich and spatially precise representations. We improve mixed-scale convolutional feedforward networks (MixCFN) with multiple depth-wise convolution paths for better local information extraction, optimizing performance and efficiency. Extensive experiments on a publicly available Thai dataset show that MeViT outperforms state-of-the-art methods, achieving a precision of 92.22%, recall of 94.69%, F1 score of 93.44%, and mean IoU of 83.63%, highlighting its effectiveness in segmenting Landsat-8 data.

# Summary. An optional shortened abstract.
summary: In this paper, we present MeViT (Medium-Resolution Vision Transformer), designed for semantic segmentation of Landsat satellite imagery, focusing on key economic crops in Thailand para rubber, corn, and pineapple. MeViT enhances Vision Transformers (ViTs) by integrating medium-resolution multi-branch architectures and revising mixed-scale convolutional feedforward networks (MixCFN) to extract multi-scale local information. Extensive experiments on a public Thailand dataset demonstrate that MeViT outperforms state-of-the-art deep learning methods, achieving a precision of 92.22%, recall of 94.69%, F1 score of 93.44%, and mean IoU of 83.63%. These results highlight MeViT's effectiveness in accurately segmenting Thai Landsat-8 data.

tags:
- Remote Sensing
- Landsat-8
- Deep Learning
- Semantic Segmentation
- High-Resolution Imagery
- Convolutional Neural Networks
- Encoder-Decoder Networks
- Vision Transformers
- Transformer
- Multi-branch Architectures
- Mixed-scale Convolutional Feedforward Networks


featured: true

links:
# - name: Videos
#   url: https://www.youtube.com/channel/UCNzeAAPyZaX4EDr720q5msg
# - name: GYSS Poster
#   url: https://kaopanboonyuen.github.io/files/GYSS/panboonyuen_MeViT_Poster_toGYSS2025.pdf
# - name: GYSS Quickfire Pitch
#   url: https://www.youtube.com/watch?v=tgcKR97Ea8I
# - name: IEEE Spectrum article
#   url: https://spectrum.ieee.org/tech-talk/computing/software/deepmind-teaches-ai-teamwork
# - name: ICIAP 2017 Best Papers
#   url: https://link.springer.com/chapter/10.1007/978-3-319-60663-7_18
url_pdf: https://www.mdpi.com/2072-4292/15/21/5124
url_code: https://github.com/kaopanboonyuen/MeVit
url_dataset: ''
url_poster: 'https://kaopanboonyuen.github.io/files/GYSS/panboonyuen_MeViT_Poster_toGYSS2025.pdf'
url_project: 'https://kaopanboonyuen.github.io/MeViT/'
url_slides: ''
url_source: ''
url_video: https://www.youtube.com/watch?v=tgcKR97Ea8I

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

{{< youtube tgcKR97Ea8I >}}

## Introduction

Semantic segmentation is vital in remote sensing, particularly for identifying and categorizing different land use and land cover types. In regions like Thailand, where agriculture is central to the economy, precise segmentation of satellite imagery can enhance our ability to track crop health, predict yields, and improve resource management. Our model, *MeViT* (Medium-Resolution Vision Transformer), is specifically designed to classify agricultural crops like para rubber, corn, and pineapple across Thailand’s varied landscapes.

## Background on Vision Transformers

Unlike traditional convolutional neural networks (CNNs), which are excellent at capturing local spatial hierarchies, Vision Transformers excel at modeling long-range dependencies through self-attention mechanisms. This unique structure allows *MeViT* to interpret both local and global features, enhancing its effectiveness in agricultural land segmentation tasks where accuracy and detail are paramount.

## MeViT Architecture

*MeViT* leverages a multi-branch architecture tailored for medium-resolution images, balancing computational efficiency with high-quality feature extraction. This design approach enables the model to capture details across multiple spatial scales, which is crucial for segmenting complex land use patterns in agricultural imagery.

In particular, the revised mixed-scale convolutional feedforward network (MixCFN) in *MeViT* incorporates multiple depth-wise convolution paths, further refining feature extraction by allowing the model to focus on different spatial scales. This enhanced architecture achieves an efficient trade-off between model complexity and performance, making it well-suited for large-scale image analysis tasks.

![](featured_backup.png)

## Experimental Results and Evaluation

We extensively tested *MeViT* on Thailand’s Landsat-8 dataset, focusing on para rubber, corn, and pineapple classifications. Compared to other models, including state-of-the-art architectures like HRViT and SegFormer, *MeViT* demonstrated notable improvements in precision and segmentation accuracy, proving its efficacy in challenging, real-world datasets. This establishes *MeViT* as a leading tool in medium-resolution satellite imagery analysis, surpassing previous Vision Transformer models and CNN-based methods in delivering high-quality semantic segmentation.

![](compact.png)

## Conclusion

*MeViT* presents a significant advancement in Vision Transformer applications, setting a new standard for semantic segmentation in remote sensing. By combining multi-branch ViT architectures with optimized convolutional modules, *MeViT* delivers efficient, accurate LULC classification on satellite imagery, supporting agricultural insights and sustainable resource management across Thailand. This work contributes to the broader field of environmental monitoring and opens up new possibilities for enhanced remote sensing techniques globally.