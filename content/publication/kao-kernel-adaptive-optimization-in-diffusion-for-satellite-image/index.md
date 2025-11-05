---
title: "KAO: Kernel-Adaptive Optimization in Diffusion for Satellite Image"
authors:
- admin

date: "2025-10-15T00:00:00Z"
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
publishDate: "2025-10-15T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication:  In *IEEE Transactions on Geoscience and Remote Sensing (TGRS, Impact Factor 8.6)*
publication_short:  In *IEEE Transactions on Geoscience and Remote Sensing (TGRS, Impact Factor 8.6)*

abstract: Satellite image inpainting is a crucial task in remote sensing, where accurately restoring missing or occluded regions is essential for robust image analysis. In this paper, we propose KAO, a novel framework that utilizes Kernel-Adaptive Optimization within diffusion models for satellite image inpainting. KAO is specifically designed to address the challenges posed by very high-resolution (VHR) satellite datasets, such as DeepGlobe and the Massachusetts Roads Dataset. Unlike existing methods that rely on preconditioned models requiring extensive retraining or postconditioned models with significant computational overhead, KAO introduces a Latent Space Conditioning approach, optimizing a compact latent space to achieve efficient and accurate inpainting. Furthermore, we incorporate Explicit Propagation into the diffusion process, facilitating forward-backward fusion, which improves the stability and precision of the method. Experimental results demonstrate that KAO sets a new benchmark for VHR satellite image restoration, providing a scalable, high-performance solution that balances the efficiency of preconditioned models with the flexibility of postconditioned models.

# Summary. An optional shortened abstract.
summary: Satellite image inpainting is a crucial task in remote sensing, where accurately restoring missing or occluded regions is essential for robust image analysis. In this paper, we propose KAO, a novel framework that utilizes Kernel-Adaptive Optimization within diffusion models for satellite image inpainting. KAO is specifically designed to address the challenges posed by very high-resolution (VHR) satellite datasets, such as DeepGlobe and the Massachusetts Roads Dataset. Unlike existing methods that rely on preconditioned models requiring extensive retraining or postconditioned models with significant computational overhead, KAO introduces a Latent Space Conditioning approach, optimizing a compact latent space to achieve efficient and accurate inpainting. Furthermore, we incorporate Explicit Propagation into the diffusion process, facilitating forward-backward fusion, which improves the stability and precision of the method. Experimental results demonstrate that KAO sets a new benchmark for VHR satellite image restoration, providing a scalable, high-performance solution that balances the efficiency of preconditioned models with the flexibility of postconditioned models.

tags:
- kernel-adaptive-optimization
- diffusion-models
- satellite-image-inpainting
- remote-sensing
- vhr-datasets
- deepglobe
- massachusetts-roads-dataset
- latent-space-conditioning
- explicit-propagation
- forward-backward-fusion
- image-restoration
- geospatial-ai
- computer-vision
- scalable-inpainting
- high-resolution-imagery

featured: true

links:
# - name: PBY.LAB
#   url: 'https://pbylab.github.io/'

- name: IEEE TGRS Paper
  url: 'https://ieeexplore.ieee.org/document/11204656/'
- name: ArXiv
  url: 'https://arxiv.org/abs/2511.02462'
  
# - name: Certificate
#   url: 'https://kaopanboonyuen.github.io/files/certificate/KST2025/Panboonyuen-Certificate-of-Contributions-53.pdf'
# - name: ICML talk
#   url: https://www.facebook.com/watch/live/?v=355035025132741&ref=watch_permalink
# - name: IEEE Spectrum article
#   url: https://spectrum.ieee.org/tech-talk/computing/software/deepmind-teaches-ai-teamwork
# - name: ICIAP 2017 Best Papers
#   url: https://link.springer.com/chapter/10.1007/978-3-319-60663-7_18
url_pdf: 'https://ieeexplore.ieee.org/document/11204656/'
url_code: 'https://github.com/kaopanboonyuen/KAO'
# url_dataset: ''
# url_poster: 'https://kaopanboonyuen.github.io/REG/'
url_project: 'https://kaopanboonyuen.github.io/KAO/'
# url_slides: 'https://kaopanboonyuen.github.io/files/slides/Panboonyuen_CUICU_TSCCM2025_Slide.pdf'
url_source: 'https://kaopanboonyuen.github.io/KAO/'
# url_video: ''

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
![](compact.png)

![](https://kaopanboonyuen.github.io/KAO/results/re_show_01.png)
![](https://kaopanboonyuen.github.io/KAO/results/re_show_01.png)
![](https://kaopanboonyuen.github.io/KAO/results/re_all_02.png)
![](https://kaopanboonyuen.github.io/KAO/results/re_all_05.png)