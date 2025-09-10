---
title: "CHULA: Custom Heuristic Uncertainty-Guided Loss for Accurate Land Title Deed Segmentation"
authors:
- admin
- C. Charoenphon
- C. Satirapod

date: "2025-05-11T00:00:00Z"
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
publishDate: "2025-05-11T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication:  In *IEEE Access (Supported by C2F Postdoctoral Funding, 2025–2026)*
publication_short:  In *IEEE Access (Supported by C2F Postdoctoral Funding, 2025–2026)*

abstract: Accurately segmenting land boundaries from Thai land title deeds is crucial for reliable land management and legal processes, but remains challenging due to low-quality scans, diverse layouts, and complex overlapping elements in documents. Existing methods often struggle with these difficulties, resulting in imprecise delineations that can cause disputes or inefficiencies. To address these issues, we propose CHULA, a novel Custom Heuristic Uncertainty-guided Loss tailored specifically for robust land title deed segmentation. CHULA uniquely combines domain-specific heuristic priors with uncertainty modeling in a unified loss function that effectively guides the model to focus on clearer regions while refining boundaries and suppressing noisy areas. Evaluated on a carefully curated Thai Land Title Deed Dataset, CHULA achieves an impressive 92.4% accuracy, significantly surpassing standard segmentation baselines. Our results highlight the promise of integrating uncertainty and heuristic knowledge to enhance segmentation accuracy in complex, real-world documents. The code is publicly available at https://github.com/kaopanboonyuen/CHULA.

# Summary. An optional shortened abstract.
summary: Accurately segmenting land boundaries from Thai land title deeds is crucial for reliable land management and legal processes, but remains challenging due to low-quality scans, diverse layouts, and complex overlapping elements in documents. Existing methods often struggle with these difficulties, resulting in imprecise delineations that can cause disputes or inefficiencies. To address these issues, we propose CHULA, a novel Custom Heuristic Uncertainty-guided Loss tailored specifically for robust land title deed segmentation. CHULA uniquely combines domain-specific heuristic priors with uncertainty modeling in a unified loss function that effectively guides the model to focus on clearer regions while refining boundaries and suppressing noisy areas. Evaluated on a carefully curated Thai Land Title Deed Dataset, CHULA achieves an impressive 92.4% accuracy, significantly surpassing standard segmentation baselines. Our results highlight the promise of integrating uncertainty and heuristic knowledge to enhance segmentation accuracy in complex, real-world documents. The code is publicly available at https://github.com/kaopanboonyuen/CHULA.

tags:
- document-segmentation
- uncertainty-modeling
- heuristic-loss
- land-title-deeds
- thai-documents
- geospatial-ai
- weak-supervision
- noisy-labels
- legal-document-analysis
- deep-learning
- custom-loss-function
- computer-vision
- boundary-refinement
- real-world-data
- image-segmentation

featured: true

links:
- name: PBY.LAB
  url: 'https://pbylab.github.io/'
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
url_pdf: 'https://ieeexplore.ieee.org/document/11146788'
url_code: 'https://github.com/kaopanboonyuen/CHULA'
# url_dataset: ''
# url_poster: 'https://kaopanboonyuen.github.io/REG/'
url_project: 'https://kaopanboonyuen.github.io/CHULA/'
# url_slides: 'https://kaopanboonyuen.github.io/files/slides/Panboonyuen_CUICU_TSCCM2025_Slide.pdf'
url_source: 'https://kaopanboonyuen.github.io/CHULA/'
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
