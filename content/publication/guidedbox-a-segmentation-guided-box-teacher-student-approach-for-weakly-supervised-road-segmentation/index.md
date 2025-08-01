---
title: "GuidedBox: A segmentation-guided box teacher-student approach for weakly supervised road segmentation"
authors:
- admin
- C. Charoenphon
- C. Satirapod

date: "2025-07-28T00:00:00Z"
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
publishDate: "2025-07-28T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication:  In *European Journal of Remote Sensing (Taylor & Francis)*
publication_short:  In *European Journal of Remote Sensing (Taylor & Francis)*

abstract: The importance of road segmentation in remote sensing data cannot be overstated, as it underpins various critical applications such as urban planning, traffic moni- toring, and autonomous driving systems. Automatically labeling objects with pixel- wise segmentation is a labor-intensive task, especially when compared to bound- ing boxes. Many existing weakly supervised instance segmentation methods rely on heuristic losses derived from bounding box priors. However, we hypothesize that box-supervised techniques may yield high-quality segmentation masks, prompting us to investigate whether detectors can effectively learn from these masks while dis- regarding those of low quality. To address this inquiry, we introduce GuidedBox, an end-to-end training framework tailored for robust, weakly supervised instance segmentation. GuidedBox employs a sophisticated teacher model to generate pre- cise masks as pseudo-labels. Recognizing the potentially detrimental effects of noisy masks on training, we propose a mask-aware confidence scoring mechanism to as- sess the quality of pseudo-masks. Additionally, we introduce noise-aware pixel loss and noise-reduced affinity loss functions to optimize the student model with pseudo masks dynamically. Extensive experimentation demonstrates the efficacy of Guided- Box across multiple datasets. Notably, GuidedBox outperforms existing state-of-the- art methods such as SOLOv2, CondInst, and Mask R-CNN on the challenging Mas- sachusetts Roads Dataset, achieving an AP50 score of 0.9231. Furthermore, Guid- edBox shows competitive performance on the SpaceNet and DeepGlobe datasets, highlighting its robustness and adaptability across different remote sensing scenarios. Code has been made available at https://github.com/kaopanboonyuen/GuidedBox.

# Summary. An optional shortened abstract.
summary: Road segmentation in remote sensing is crucial for applications like urban planning, traffic monitoring, and autonomous driving. Labeling objects via pixel-wise segmentation is challenging compared to bounding boxes. Existing weakly supervised segmentation methods often rely on heuristic bounding box priors, but we propose that box-supervised techniques can yield better results. Introducing GuidedBox, an end-to-end framework for weakly supervised instance segmentation. GuidedBox uses a teacher model to generate high-quality pseudo-masks and employs a confidence scoring mechanism to filter out noisy masks. We also introduce a noise-aware pixel loss and affinity loss to optimize the student model with pseudo-masks. Our extensive experiments show that GuidedBox outperforms state-of-the-art methods like SOLOv2, CondInst, and Mask R-CNN on the Massachusetts Roads Dataset, achieving an AP50 score of 0.9231. It also shows strong performance on SpaceNet and DeepGlobe datasets, proving its versatility in remote sensing applications. Code has been made available at https://github.com/kaopanboonyuen/GuidedBox.

tags:
- weakly-supervised-learning
- road-segmentation
- remote-sensing
- teacher-student-framework
- pseudo-labeling
- instance-segmentation
- computer-vision
- geospatial-ai
- mask-generation
- noise-aware-learning

featured: true

links:
# - name: ArXiv
#   url: 'http://arxiv.org/abs/2507.13655'
# - name: Certificate
#   url: 'https://kaopanboonyuen.github.io/files/certificate/KST2025/Panboonyuen-Certificate-of-Contributions-53.pdf'
# - name: ICML talk
#   url: https://www.facebook.com/watch/live/?v=355035025132741&ref=watch_permalink
# - name: IEEE Spectrum article
#   url: https://spectrum.ieee.org/tech-talk/computing/software/deepmind-teaches-ai-teamwork
# - name: ICIAP 2017 Best Papers
#   url: https://link.springer.com/chapter/10.1007/978-3-319-60663-7_18
url_pdf: 'https://www.tandfonline.com/doi/full/10.1080/22797254.2025.2540963'
url_code: 'https://github.com/kaopanboonyuen/GuidedBox/'
# url_dataset: ''
# url_poster: 'https://kaopanboonyuen.github.io/REG/'
url_project: 'https://kaopanboonyuen.github.io/GuidedBox/'
# url_slides: 'https://kaopanboonyuen.github.io/files/slides/Panboonyuen_CUICU_TSCCM2025_Slide.pdf'
url_source: 'https://kaopanboonyuen.github.io/GuidedBox/'
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

![](compact.png)
