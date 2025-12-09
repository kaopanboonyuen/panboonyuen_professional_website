---
title: "SLICK: Selective Localization and Instance Calibration for Knowledge-Enhanced Car Damage Segmentation in Automotive Insurance"
authors:
- admin

date: "2025-03-07T00:00:00Z"
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
publishDate: "2025-03-07T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication:  In *arXiv:2506.10528 [cs.CV]*
publication_short:  In *arXiv:2506.10528 [cs.CV]*

abstract: We present SLICK, a novel framework for precise and robust car damage segmentation that leverages structural priors and domain knowledge to tackle real-world automotive inspection challenges. SLICK introduces five key components (1) Selective Part Segmentation using a high-resolution semantic backbone guided by structural priors to achieve surgical accuracy in segmenting vehicle parts even under occlusion, deformation, or paint loss; (2) Localization-Aware Attention blocks that dynamically focus on damaged regions, enhancing fine-grained damage detection in cluttered and complex street scenes; (3) an Instance-Sensitive Refinement head that leverages panoptic cues and shape priors to disentangle overlapping or adjacent parts, enabling precise boundary alignment; (4) Cross-Channel Calibration through multi-scale channel attention that amplifies subtle damage signals such as scratches and dents while suppressing noise like reflections and decals; and (5) a Knowledge Fusion Module that integrates synthetic crash data, part geometry, and real-world insurance datasets to improve generalization and handle rare cases effectively. Experiments on large-scale automotive datasets demonstrate SLICK's superior segmentation performance, robustness, and practical applicability for insurance and automotive inspection workflows.

# Summary. An optional shortened abstract.
summary: We propose SLICK, a novel and efficient framework for high-precision car damage segmentation, designed for real-world deployment in automotive insurance and inspection workflows. SLICK introduces five synergistic components, selective part segmentation guided by structural priors, localization-aware attention to highlight fine-grained damage, instance-sensitive refinement for precise boundary separation, cross-channel calibration to amplify subtle cues like scratches and dents, and a knowledge fusion module that integrates synthetic crash data, part geometry, and annotated insurance datasets. Trained using a teacher–student distillation strategy with ALBERT as the teacher, SLICK retains high segmentation fidelity while achieving up to 7× faster inference. Extensive experiments on large-scale automotive datasets demonstrate SLICK’s superior accuracy, generalization, and runtime efficiency—making it ideal for real-time, high-stakes applications in insurance automation and vehicle inspection.

tags:
- Car Damage Segmentation
- Automotive Insurance AI
- Instance Calibration
- Structural Priors in Vision
- Localization-Aware Attention
- Real-Time Vehicle Inspection
- Auto Insurance Automation
- Knowledge Distillation
- Teacher–Student Learning
- Transformer-Based Segmentation
- Efficient Deep Learning
- AI Model Compression
- Fast Inference Models
- Insurance Fraud Detection
- Synthetic Crash Data
- Deep Learning for Automotive Claims
- Lightweight Vision Models

featured: true

links:
- name: ArXiv
  url: 'https://arxiv.org/abs/2506.10528'
- name: MARSAIL
  url: 'https://kaopanboonyuen.github.io/blog/2025-07-01-marsail-the-smart-engine-behind-the-future-of-car-insurance/'
- name: Blog
  url: 'https://kaopanboonyuen.github.io/blog/2025-07-02-albert-vs-slick-marsail-new-ai-fashion/'
- name: Hugging Face
  url: 'https://huggingface.co/kaopanboonyuen'
# - name: Certificate
#   url: 'https://kaopanboonyuen.github.io/files/certificate/KST2025/Panboonyuen-Certificate-of-Contributions-53.pdf'
# - name: ICML talk
#   url: https://www.facebook.com/watch/live/?v=355035025132741&ref=watch_permalink
# - name: IEEE Spectrum article
#   url: https://spectrum.ieee.org/tech-talk/computing/software/deepmind-teaches-ai-teamwork
# - name: ICIAP 2017 Best Papers
#   url: https://link.springer.com/chapter/10.1007/978-3-319-60663-7_18
url_pdf: 'https://arxiv.org/pdf/2506.10528'
url_code: 'https://github.com/kaopanboonyuen/MARS'
url_dataset: ''
# url_poster: 'https://kaopanboonyuen.github.io/REG/'
url_project: 'https://kaopanboonyuen.github.io/blog/2025-07-02-albert-vs-slick-marsail-new-ai-fashion/'
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
![](compact.png)