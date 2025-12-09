---
title: "CU-ICU: Customizing Unsupervised Instruction-Finetuned Language Models for ICU Datasets via Text-to-Text Transfer Transformer"
authors:
- admin

date: "2025-07-17T00:00:00Z"
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
publishDate: "2025-07-17T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["3"]

# Publication name and optional abbreviated publication name.
publication:  In *the 14th Critical Care Conference (King Chulalongkorn Memorial Hospital)*
publication_short:  In *the 14th Critical Care Conference (King Chulalongkorn Memorial Hospital)*

abstract: Integrating large language models into specialized domains like healthcare presents unique challenges, including domain adaptation and limited labeled data. We introduce CU-ICU, a method for customizing unsupervised instruction-finetuned language models for ICU datasets by leveraging the Text-to-Text Transfer Transformer (T5) architecture. CU-ICU employs a sparse fine-tuning approach that combines few-shot prompting with selective parameter updates, enabling efficient adaptation with minimal supervision. Our evaluation across critical ICU tasks—early sepsis detection, mortality prediction, and clinical note generation—demonstrates that CU-ICU consistently improves predictive accuracy and interpretability over standard fine-tuning methods. Notably, CU-ICU achieves up to a 15% increase in sepsis detection accuracy and a 20% enhancement in generating clinically relevant explanations while updating fewer than 1% of model parameters in its most efficient configuration. These results establish CU-ICU as a scalable, low-overhead solution for delivering accurate and interpretable clinical decision support in real-world ICU environments.

# Summary. An optional shortened abstract.
summary: Integrating large language models into specialized domains like healthcare presents unique challenges, including domain adaptation and limited labeled data. We introduce CU-ICU, a method for customizing unsupervised instruction-finetuned language models for ICU datasets by leveraging the Text-to-Text Transfer Transformer (T5) architecture. CU-ICU employs a sparse fine-tuning approach that combines few-shot prompting with selective parameter updates, enabling efficient adaptation with minimal supervision. Our evaluation across critical ICU tasks—early sepsis detection, mortality prediction, and clinical note generation—demonstrates that CU-ICU consistently improves predictive accuracy and interpretability over standard fine-tuning methods. Notably, CU-ICU achieves up to a 15% increase in sepsis detection accuracy and a 20% enhancement in generating clinically relevant explanations while updating fewer than 1% of model parameters in its most efficient configuration. These results establish CU-ICU as a scalable, low-overhead solution for delivering accurate and interpretable clinical decision support in real-world ICU environments.

tags:
- clinical-llms  
- parameter-efficient-finetuning  
- peft  
- medical-ai  
- prompt-learning  
- flan-t5  
- healthcare-innovation  
- sepsis-detection  
- icu-mortality-prediction  

featured: true

links:
- name: ArXiv
  url: 'http://arxiv.org/abs/2507.13655'
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
url_pdf: 'http://arxiv.org/pdf/2507.13655'
url_code: 'https://github.com/kaopanboonyuen'
url_dataset: ''
# url_poster: 'https://kaopanboonyuen.github.io/REG/'
url_project: 'https://kaopanboonyuen.github.io/blog/2025-07-17-cuicu-customizing-unsupervised-instruction-finetuned-language-models/'
url_slides: 'https://kaopanboonyuen.github.io/files/slides/Panboonyuen_CUICU_TSCCM2025_Slide.pdf'
url_source: 'https://kaopanboonyuen.github.io/blog/2025-07-17-cuicu-customizing-unsupervised-instruction-finetuned-language-models/'
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
