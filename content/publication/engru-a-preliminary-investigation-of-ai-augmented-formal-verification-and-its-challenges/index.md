---
title: "ENGRU: A Preliminary Investigation of AI-Augmented Formal Verification and Its Challenges"
authors:
- C. Dechsupa
- admin
- W. Vatanawood

date: "2025-02-02T00:00:00Z"
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
publishDate: "2025-02-02T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication:  In *IEEE Access* **Impact Factor 3.4**
publication_short:  In *IEEE Access* **Impact Factor 3.4**

abstract: State-space graphs and automata serve as fundamental tools for modeling and analyzing the behavior of computational systems. Recurrent neural networks (RNNs) and language models are deeply intertwined, as RNNs provide the foundational architecture that enables language models to process sequential data, capture contextual dependencies, and improve natural language processing tasks. Both RNNs and state-space graphs are used to evaluate discrete-time systems within this formal framework. However, the basic question of their equivalence remains an open challenge, particularly with regard to the models governing sentence structure in natural language and the formal models in automata theory. In this paper, we present ENGRU (Enhanced Gated Recurrent Units), a novel deep learning-based approach for formal verification. ENGRU integrates model checking techniques, Colored Petri Nets (CPNs), and sequential learning to analyze systems at a high level of abstraction. CPN models undergo state-space enumeration through a model-checking tool, generating a state-space graph and an automaton based on inherent state transition patterns. These graphs are transformed into sequential representations as sub-paths, enabling ENGRU to learn execution paths and predict system behaviors. ENGRU effectively predicts goal states within discrete-time models, leveraging the competency of gated recurrent mechanisms. This encourages early bug detection and enables predictive state-space exploration. Experimental results demonstrate that ENGRU achieves high accuracy and efficiency in goal state predictions. The source code for ENGRU is available at https://github.com/kaopanboonyuen/ENGRU.

# Summary. An optional shortened abstract.
summary: State-space graphs and automata are essential for modeling and analyzing computational systems. Recurrent neural networks (RNNs) underpin language models by processing sequential data and capturing contextual dependencies. Both RNNs and state-space graphs evaluate discrete-time systems, but their equivalence, especially in sentence structure modeling, remains unresolved. This paper introduces ENGRU (Enhanced Gated Recurrent Units), a deep learning approach for formal verification. ENGRU combines model checking, Colored Petri Nets (CPNs), and sequential learning to analyze systems abstractly. CPNs undergo state-space enumeration to generate graphs and automata, which are transformed into sequential representations for ENGRU to learn and predict system behaviors. ENGRU effectively predicts goal states in discrete-time models, aiding early bug detection and predictive state-space exploration. Experimental results show high accuracy and efficiency in goal state predictions. ENGRU’s source code is available at https://github.com/kaopanboonyuen/ENGRU.


tags:
- Formal Verification
- Model Checking
- Petri Nets
- Computational Modeling
- Analytical Models

featured: true

links:
# - name: ArXiv
#   url: 'https://ieeexplore.ieee.org/abstract/document/10929005/'
# - name: Certificate
#   url: 'https://kaopanboonyuen.github.io/files/certificate/KST2025/Panboonyuen-Certificate-of-Contributions-53.pdf'
# - name: ICML talk
#   url: https://www.facebook.com/watch/live/?v=355035025132741&ref=watch_permalink
# - name: IEEE Spectrum article
#   url: https://spectrum.ieee.org/tech-talk/computing/software/deepmind-teaches-ai-teamwork
# - name: ICIAP 2017 Best Papers
#   url: https://link.springer.com/chapter/10.1007/978-3-319-60663-7_18
url_pdf: 'https://ieeexplore.ieee.org/document/10993355'
url_code: 'https://github.com/kaopanboonyuen/ENGRU'
url_dataset: ''
# url_poster: 'https://kaopanboonyuen.github.io/REG/'
url_project: 'https://github.com/kaopanboonyuen/ENGRU'
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