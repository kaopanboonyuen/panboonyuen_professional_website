---
title: UAMC2025 (Undergraduate in Applied Mathematics Conference 2025)

event: UAMC2025 (Undergraduate in Applied Mathematics Conference 2025)
event_url: http://www.math.sci.kmitl.ac.th/uamc2025/index.html

location: King Mongkut's Institute of Technology Ladkrabang (KMITL)
<!-- address:
  street: 1, Soi Chalongkrung 1, Lat Krabang District
  city: Bangkok
  region: Bangkok
  postcode: '10520'
  country: Thailand -->

summary: Discover the powerful math behind Vision Transformers (ViTs) and how they’re revolutionizing AI in the car insurance industry. We’ll dive into the self-attention mechanism that allows ViTs to process visual data with precision, explore custom loss functions to improve claim prediction accuracy, and discuss the exciting potential of integrating Large Language Models (LLMs) to elevate AI, unlocking new possibilities and driving innovation in the insurance world. By examining these cutting-edge techniques, we’ll uncover how AI is set to redefine the way insurance claims are handled, making processes smarter, faster, and more efficient.

abstract: This talk will provide an in-depth exploration of the mathematical principles behind Vision Transformers (ViTs) and their potential applications in the car insurance sector. We will begin by examining the core concepts of transformer models, with a particular focus on the self-attention mechanism, which allows the model to weigh the importance of different parts of an image. This leads to more accurate and robust image recognition. We will also cover the process of creating custom loss functions that are designed to train these models in the specific context of car insurance, improving both prediction accuracy and efficiency in claim assessment. Finally, we will discuss the future of this technology, including the exciting potential of Large Language Models (LLMs) to further enhance AI-driven solutions in this space. By the end of the session, attendees will have a strong understanding of both the mathematics behind Vision Transformers and their practical applications in the insurance industry.

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: "2025-03-27T013:00:00Z"
#date_end: "2030-06-01T15:00:00Z"
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: "2025-03-27T13:00:00Z"

authors: []
tags: []

# Is this a featured talk? (true/false)
featured: false

image:
  caption: ''
  focal_point: Right

links:
url_code: http://www.math.sci.kmitl.ac.th/uamc2025/index.html
url_pdf: http://www.math.sci.kmitl.ac.th/uamc2025/index.html
# url_poster: 'https://kaopanboonyuen.github.io/files/GYSS/panboonyuen_MeViT_Poster_toGYSS2025.pdf'
url_video: http://www.math.sci.kmitl.ac.th/uamc2025/index.html
# url_embed: https://www.nstda.or.th/nac/2025/youth-activities/youth-activity-2/

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
# slides: example

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
- internal-project

---
## Introduction

🚗💡 This Sunday (March 30, 2025), if you're around Ladkrabang, come join us for a math talk! 📚💬 We’ll dive deep into the fascinating world of Vision Transformers (ViTs) and their applications in car insurance AI. It's an exciting opportunity to explore how advanced mathematical techniques are driving the future of AI in the insurance industry. Don’t miss out—join us for this insightful session!

Topic: Mathematical Foundations of Vision Transformers in Car Insurance AI  
🕐 Time: 1:00 PM  

📍 Location: [Event Location](https://www.facebook.com/photo?fbid=1192313742905954&set=a.490286653108670)

![](featured.png)

![](uamc2025_images/UAMC2025xMARS_05.jpg)
![](uamc2025_images/UAMC2025xMARS_02.jpg)
![](uamc2025_images/UAMC2025xMARS_04.jpg)
![](uamc2025_images/UAMC2025xMARS_03.jpg)
![](uamc2025_images/UAMC2025xMARS_06.jpg)
![](uamc2025_images/UAMC2025xMARS_01.jpg)
![](uamc2025_images/UAMC2025xMARS_07.jpg)
![](uamc2025_images/UAMC2025xMARS_08.jpg)

---

In recent years, Vision Transformers (ViTs) have emerged as one of the most powerful models in the field of deep learning, particularly in tasks involving image recognition. This blog post explores the mathematical foundations of ViTs and their application in car insurance AI, with a focus on improving accuracy in claims prediction. We will cover key concepts such as the self-attention mechanism, custom loss functions, and how large language models (LLMs) could further enhance these AI systems. By the end of this article, you’ll have a deeper understanding of how cutting-edge AI technologies are reshaping the insurance industry.

## Vision Transformers: A Mathematical Overview

### The Transformer Architecture

At the heart of Vision Transformers lies the Transformer architecture, which was originally designed for natural language processing tasks. Unlike traditional convolutional neural networks (CNNs), which rely on convolutional layers to process spatial data, ViTs treat an image as a sequence of patches and apply self-attention to learn relationships between these patches.

The image is divided into non-overlapping patches, each of which is flattened into a vector. These patch vectors are then embedded into a higher-dimensional space. The idea is that these embedded patches will be processed as a sequence, similar to how words in a sentence are processed in NLP tasks. This sequence is passed through layers of self-attention, where the model learns how to focus on different parts of the image depending on their relevance.

### Self-Attention Mechanism

The self-attention mechanism is what allows Vision Transformers to capture complex relationships between distant regions of the image. In a standard convolutional network, filters are used to detect local patterns in the image. However, in ViTs, the self-attention mechanism dynamically determines the importance of each patch relative to others. This makes it possible for the model to capture long-range dependencies and subtle patterns across the entire image, rather than focusing only on local features.

By applying this mechanism, Vision Transformers can give more weight to certain parts of the image that are more relevant for the task at hand, whether it’s identifying damage in a vehicle or classifying certain types of claims.

## Custom Loss Functions for Car Insurance AI

### The Need for Custom Loss Functions

In the context of car insurance, traditional loss functions like cross-entropy are not always ideal. For instance, car insurance claims often involve rare and highly specific damage types that are underrepresented in training datasets. This creates a class imbalance issue, where the model may not perform well on minority classes, such as rare types of damage or low-frequency events.

To address this, custom loss functions are developed to weight certain classes higher than others, ensuring that the model focuses on less frequent but equally important classes. This type of custom loss function helps improve prediction accuracy, particularly in a domain like insurance, where predicting the likelihood of rare events is just as crucial as predicting common ones.

### Mean Squared Error for Regression Tasks

In some cases, car insurance AI needs to predict continuous values, such as the cost of repair. For such tasks, a loss function like Mean Squared Error (MSE) is commonly used. This loss function measures the difference between the predicted and true values, with the aim of minimizing this error. Using MSE ensures that the model’s predictions are as close as possible to the actual values, which is critical when estimating damage repair costs.

## Integrating Large Language Models (LLMs) for Enhanced AI

The integration of Large Language Models (LLMs) like GPT-4 with Vision Transformers can open up new possibilities for multi-modal AI systems. In car insurance, LLMs can process textual data—such as customer reports, claim descriptions, and policy documents—while ViTs handle visual data like images of the damaged vehicle.

By combining these two modalities, we can create a system that not only understands visual information but also the context behind it. For example, an LLM could help interpret the description of an accident or read through a claim submission and make sense of the visual evidence provided by the ViT. This multi-modal approach enhances decision-making, enabling more accurate claim assessments and better customer experiences.

## Conclusion

Vision Transformers are revolutionizing AI in the car insurance industry by enabling the accurate and efficient processing of complex visual data. By leveraging advanced mathematical concepts like self-attention and custom loss functions, we can build AI models that are more accurate and robust, even when dealing with rare and highly variable data. The potential for combining ViTs with LLMs represents the next frontier in AI, making it possible to create systems that understand both images and text, paving the way for more intelligent, automated solutions in car insurance.

---

## References

1. Vaswani, A., Shazeer, N., Parmar, N., Uszkoreit, J., Jones, L., Gomez, A. N., Kaiser, Ł., & Polosukhin, I. (2017). *Attention is All You Need*. In Advances in Neural Information Processing Systems (NeurIPS 2017). [Link to Paper](https://arxiv.org/abs/1706.03762)

2. Dosovitskiy, A., Berman, M., & Hinton, G. E. (2020). *An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale*. In Proceedings of the International Conference on Machine Learning (ICML 2020). [Link to Paper](https://arxiv.org/abs/2010.11929)

3. Brown, T. B., Mann, B., Ryder, N., Subbiah, M., Kaplan, J., Dhariwal, P., Neelakantan, A., Shinn, N., & others. (2020). *Language Models are Few-Shot Learners*. In Proceedings of NeurIPS 2020. [Link to Paper](https://arxiv.org/abs/2005.14165)

4. OpenAI. (2023). *GPT-4 Technical Report*. [Link to Paper](https://arxiv.org/abs/2303.08774)

---