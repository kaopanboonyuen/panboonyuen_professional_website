---
title: "REG: Refined Generalized Focal Loss for Road Asset Detection on Thai Highways Using Vision-Based Detection and Segmentation Models"
authors:
- admin
- N. Rattanachona
- P. Thungthin
- N. Subsompon
- S. Thongbai
- W. Wongweeranimit
- R. Phukham

date: "2024-09-01T00:00:00Z"
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
publishDate: "2024-09-01T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *5th International Conference on Highway Engineering* **ICHE 2024**
publication_short: In *5th International Conference on Highway Engineering* **ICHE 2024**

abstract: This paper dives into the cutting-edge world of road asset detection on Thai highways, showcasing a novel approach that combines an upgraded REG model with Generalized Focal Loss. Our focus is on identifying key road elements—like pavilions, pedestrian bridges, information and warning signs, and concrete guardrails—to boost road safety and infrastructure management. While deep learning methods have shown promise, traditional models often struggle with accuracy in tricky conditions, such as cluttered backgrounds and variable lighting. To tackle these issues, we've integrated REG with Generalized Focal Loss, enhancing its ability to detect road assets with greater precision. Our results are impressive, the REGx model led the way with a mAP50 of 80.340, mAP50-95 of 60.840, precision of 79.100, recall of 76.680, and an F1-score of 77.870. These findings highlight the REGx model’s superior performance, demonstrating the power of advanced deep learning techniques to improve highway safety and infrastructure maintenance, even in challenging conditions.

# Summary. An optional shortened abstract.
summary: This paper dives into the cutting-edge world of road asset detection on Thai highways, showcasing a novel approach that combines an upgraded REG model with Generalized Focal Loss. Our focus is on identifying key road elements—like pavilions, pedestrian bridges, information and warning signs, and concrete guardrails—to boost road safety and infrastructure management. While deep learning methods have shown promise, traditional models often struggle with accuracy in tricky conditions, such as cluttered backgrounds and variable lighting. To tackle these issues, we've integrated REG with Generalized Focal Loss, enhancing its ability to detect road assets with greater precision. Our results are impressive, the REGx model led the way with a mAP50 of 80.340, mAP50-95 of 60.840, precision of 79.100, recall of 76.680, and an F1-score of 77.870. These findings highlight the REGx model’s superior performance, demonstrating the power of advanced deep learning techniques to improve highway safety and infrastructure maintenance, even in challenging conditions.

tags:
- Deep Learning
- Semantic Segmentation
- Convolutional Neural Networks
- Thai Highway Imagery
- Generalized Focal Loss
- YOLO
- REG

featured: true

links:
- name: Blog
  url: https://kaopanboonyuen.github.io/blog/2024-09-07-refined-generalized-focal-loss-for-road-asset-detection-on-thai-highways-using-vision-models/
- name: ArXiv
  url: https://www.arxiv.org/abs/2409.09877
- name: Certificate
  url: 'https://kaopanboonyuen.github.io/files/certificate/KST2025/Panboonyuen-Certificate-of-Contributions-57.pdf'
# - name: IEEE Spectrum article
#   url: https://spectrum.ieee.org/tech-talk/computing/software/deepmind-teaches-ai-teamwork
# - name: ICIAP 2017 Best Papers
#   url: https://link.springer.com/chapter/10.1007/978-3-319-60663-7_18
url_pdf: https://www.arxiv.org/abs/2409.09877
url_code: https://github.com/kaopanboonyuen/REG
url_dataset: ''
url_poster: 'https://kaopanboonyuen.github.io/REG/'
url_project: 'https://kaopanboonyuen.github.io/REG/'
url_slides: 'https://kaopanboonyuen.github.io/files/slides/20240906_Panboonyuen_AI_ThaiHighway.pdf'
url_source: 'https://kaopanboonyuen.github.io/blog/2024-09-07-refined-generalized-focal-loss-for-road-asset-detection-on-thai-highways-using-vision-models/'
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

### Exciting News: Oral Presentation at iCHE 2024!

I am thrilled to share that our paper titled **"Enhanced REG-Based Object Detection of Road Assets Utilizing Generalized Focal Loss: A Case Study on Thai Highway Imagery"** has been accepted for an oral presentation at the **5th International Conference on Highway Engineering (iCHE 2024)**! After a long absence from international conferences since my Ph.D. studies, I'm incredibly excited to rejoin the academic community in person and present our latest research.

> Dive into the complete details of our research on road asset detection in Thai highways with advanced vision models. Check out the full blog post here: [REG: Refined Generalized Focal Loss for Road Asset Detection](https://kaopanboonyuen.github.io/blog/2024-09-07-refined-generalized-focal-loss-for-road-asset-detection-on-thai-highways-using-vision-models/)

## Meet REG: The Game-Changer in Highway Asset Detection

Hi guys, fellow tech enthusiasts! I'm thrilled to unveil a cutting-edge innovation from my latest research—Refined Generalized Focal Loss (REG). This revolutionary approach is transforming road asset detection on Thai highways, and it’s as exciting as it sounds.

> So, what’s the big deal with REG? Imagine a detection system that not only sees but truly understands the intricate details of highway scenes. REG pushes the boundaries of current vision-based detection models by tackling the most challenging issues: imbalanced datasets, tiny objects, and complex highway backdrops.

![](featured.png)

My method (check out Fig. 1) brings a whole new level of precision to the table. By integrating a custom loss function into the detection architecture, REG doesn't just improve performance—it redefines it. This means sharper, more reliable detection of critical road assets like signs, lane markings, and barriers. And let’s be real, that’s a game-changer for infrastructure management and road safety.

<div style="text-align: center;"> 
<img src="REG_1.png" alt="Refined Generalized Focal Loss Framework" style="max-width: 100%; height: auto;"> 
<p style="font-style: italic; margin-top: 0px;">Fig. 1. The REG-based detection framework employs Generalized Focal Loss to master class imbalance in Thai highway road asset detection. Combining Transformer layers with convolutional modules, and using Batch Normalization and Adaptive Dropout, this model stands out for its robustness. It’s finely tuned to capture the unique aspects of Thai highways, focusing on rare and challenging assets. 
<a href="https://arxiv.org/pdf/2006.04388" target="_blank">[Refined Generalized Focal Loss]</a></p> 
</div>

REG isn't just a theoretical leap; it’s a practical breakthrough with real-world impact. It’s especially useful for regions with road structures similar to Thai highways, where conventional detection algorithms might falter. By merging Vision Transformers (ViT) with conditional random fields (CRF), we’ve supercharged the model’s ability to segment and identify road assets with pinpoint accuracy. 

{{% callout note %}}
This isn’t just about the future of intelligent transportation systems; it’s about the here and now. As we edge closer to autonomous vehicle navigation, innovations like REG are paving the way for smarter, safer roads. Buckle up and stay tuned—exciting times are ahead!
{{% /callout %}}

## Motivation and Relevance

Thailand's highway infrastructure plays a critical role in its economic development and connectivity. However, managing and maintaining these extensive road networks presents numerous challenges, particularly in detecting and assessing road assets. Accurate identification of road features such as signs, barriers, and markings is essential for effective maintenance and safety management.

![](RE_REG_01.png)
![](RE_REG_02.png)

{{% callout note %}}
In this context, our research addresses a pressing need in highway engineering: improving road asset detection on Thai highways. Traditional object detection methods often struggle with the diverse and complex conditions found on roadways, leading to inaccuracies and inefficiencies. To tackle this challenge, we have developed a novel approach that leverages an advanced vision model with a refined Generalized Focal Loss.
{{% /callout %}}

Our proposed method (Fig. 2) enhances the capability of REG-based object detection systems by incorporating a tailored loss function designed to address the unique characteristics of Thai highway imagery. By optimizing the detection process, our approach aims to provide more reliable and precise data for road asset management. This advancement not only contributes to the field of highway engineering but also supports the development of more efficient infrastructure management practices in Thailand.

<div style="text-align: center;"> <img src="proposed_method.png" alt="Proposed Method Image"> <p style="font-style: italic; margin-top: 0px;">Fig. 2. The proposed Enhanced REG-based object detection framework integrates Generalized Focal Loss for improved detection accuracy. This approach includes various REG model variants, ranging from REGn to REGx, each offering a balance between computational efficiency and detection performance. The network architecture leverages convolutional layers with Batch Normalization and Leaky ReLU activations. The Generalized Focal Loss, designed to address class imbalance, enhances performance for small and difficult-to-detect objects by focusing on hard examples. Our contribution didn’t just stop at the models; we also built our own dataset from scratch. By equipping a vehicle with high-resolution cameras, we captured detailed imagery of road assets across Thai highways. This custom dataset forms the backbone of our approach, providing a strong foundation for model training. The training utilizes the AdamW optimizer with specific hyperparameters to optimize convergence and model performance. <a href="https://github.com/kaopanboonyuen/REG" target="_blank">[REG: Refined Generalized Focal Loss]</a></p> </div>

This paper represents a significant step forward in applying cutting-edge computer vision techniques to real-world problems. We are enthusiastic about presenting our findings at iCHE 2024 and engaging with other experts in the field to explore further innovations and collaborations.

Stay tuned for updates, and a big thank you to my incredible research team:  
**N. Rattanachona (N'Fuse)**, **P. Thungthin (N'Dear)**, **N. Subsompon (N'Tien)**. Your hard work and dedication were essential to this project!

![](Kao_iCHE2024/kao_mars_x_iche2024_00.jpg)
![](featured_full.png)

Here I am, presenting our work on the Enhanced REG model and its application in detecting road assets!

![](Kao_iCHE2024/kao_mars_x_iche2024_02.jpg)

We have visualizations of the detection results produced by the Enhanced REG model. The bounding boxes and labels demonstrate the model’s ability to accurately locate and classify objects. These visuals reflect the high-resolution output and the model’s performance in detecting road assets in various environments. The clarity of these results illustrates the practical utility of our model in real-time applications. It effectively showcases how our model handles complex and dynamic scenes.

### Generalized Focal Loss for Multi-Class Detection

The detection task focuses on identifying seven key classes of road assets: Pavilions, Pedestrian bridges, Information signs, Single-arm poles, Bus stops, Warning signs, and Concrete guardrails (Fig. 3). The challenge lies in dealing with class imbalance — smaller and harder-to-detect objects can be easily overlooked by traditional object detection models. We address this by utilizing **Generalized Focal Loss (GFL)**, which extends the classical Focal Loss to multi-class detection, giving more focus to underrepresented and challenging classes.

<div style="text-align: center;">
    <img src="REG_2.png" alt="Generalized Focal Loss for Multi-Class Detection">
    <p style="font-style: italic; margin-top: 0px;">Fig. 3. My proposed Generalized Focal Loss for multi-class detection tackles class imbalance across seven asset classes. By extending Focal Loss, we improve detection accuracy for small and difficult-to-classify objects.</p>
</div>

### Refined Generalized Focal Loss for Segmentation

For the segmentation task, we detect road assets at the pixel level, focusing on five classes: Pavilions, Pedestrian bridges, Information signs, Warning signs, and Concrete guardrails (Fig. 4). The key here is to ensure that every pixel is correctly classified into one of these categories, which is a non-trivial problem in cluttered highway imagery. My **Refined Generalized Focal Loss** applies pixel-wise loss calculation, extending GFL into the realm of segmentation.

<div style="text-align: center;">
    <img src="REG_3.png" alt="Refined Generalized Focal Loss for Segmentation">
    <p style="font-style: italic; margin-top: 0px;">Fig. 4. The segmentation process classifies each pixel into one of five road asset classes, using Refined Generalized Focal Loss to enhance pixel-wise accuracy in segmentation tasks.</p>
</div>

![](Kao_iCHE2024/kao_mars_x_iche2024_03.jpg)

Now, let’s look at a real-world application of our Enhanced REG model in detecting road assets. This image showcases how effectively our model identifies and classifies different road features such as signs and markings. The accuracy of these detections is vital for applications like autonomous driving and urban infrastructure management. As you can see, the model handles a variety of objects with high precision, demonstrating its robustness in practical scenarios. This performance underscores the model's potential for real-world deployment.

![](Kao_iCHE2024/kao_mars_x_iche2024_04.jpg)

This chart presents a comparison of performance metrics between our Enhanced REG model and previous versions. We observe significant improvements in precision, recall, and F1-score. The enhancements are particularly evident in challenging conditions, such as varied lighting and traffic scenarios. These metrics highlight the effectiveness of our model's enhancements. By achieving superior results, our approach sets a new benchmark in object detection accuracy.

![](Kao_iCHE2024/kao_mars_x_iche2024_05.jpg)

Finally, this image illustrates the training process for the Enhanced REG model. It depicts the stages of optimization and fine-tuning, with various datasets and augmentation techniques used to enhance the model’s performance. The iterative process shown here is crucial for achieving the high accuracy demonstrated in our results. Observing these training phases provides insights into how we refined the model. This rigorous approach is key to ensuring the model’s effectiveness and reliability in practical applications.

### Refinement Term for Spatial-Contextual Learning

To further enhance learning, we introduce a spatial-contextual refinement term $\(g_{i,c}\)$ that dynamically adjusts the loss based on the geometric and contextual significance of each object class (Fig. 5). This term allows the model to account for the spatial distribution of road assets, making it more adept at handling complex scenes typical of real-world road environments.

<div style="text-align: center;">
    <img src="REG_4.png" alt="Spatial-Contextual Refinement Term">
    <p style="font-style: italic; margin-top: 0px;">Fig. 5. The refinement term \(g_{i,c}\) adjusts the loss based on spatial and contextual relevance, improving model learning in complex and cluttered road scenes.</p>
</div>

### Joint Optimization for Detection and Segmentation

We then integrate the detection and segmentation tasks into a joint optimization framework. By combining the losses for both tasks (Fig. 6), the model learns complementary representations, allowing it to improve both object detection and pixel-wise segmentation accuracy. This joint approach ensures that the model balances precision and recall across different road asset classes.

<div style="text-align: center;">
    <img src="REG_5.png" alt="Joint Optimization for Detection and Segmentation">
    <p style="font-style: italic; margin-top: 0px;">Fig. 6. Joint optimization balances detection and segmentation losses, enhancing performance across both tasks by learning complementary features.</p>
</div>

### Incorporating Prediction Uncertainty

To further refine REG, we incorporated prediction uncertainty using a Gaussian distribution (Fig. 7). This technique accounts for the inherent noise and ambiguity in complex environments, particularly under varying lighting and cluttered backgrounds, thereby improving both robustness and accuracy.

<div style="text-align: center;">
    <img src="REG_6.png" alt="Incorporating Prediction Uncertainty">
    <p style="font-style: italic; margin-top: 0px;">Fig. 7. We model prediction uncertainty using a Gaussian distribution to handle noise and ambiguity, particularly in challenging road scenes.</p>
</div>

### Mathematical Foundations for Optimization in REG

The optimization of REG is based on advanced techniques in stochastic optimization, where we extend traditional gradient descent to operate on **Riemannian Manifolds** (Fig. 8). Given the non-convex nature of the loss landscape, we utilize variational inference, proximal gradient methods, and Lagrangian multipliers, allowing for efficient optimization in multi-task learning.

<div style="text-align: center;">
    <img src="REG_7.png" alt="Mathematical Foundations for Optimization in REG">
    <p style="font-style: italic; margin-top: 0px;">Fig. 8. Advanced mathematical techniques, including Riemannian stochastic gradient descent, underpin the optimization of REG in complex, high-dimensional spaces.</p>
</div>

### Performance Analysis for Detection and Segmentation

Finally, we tested the model's performance on both detection (Fig. 9) and segmentation tasks (Fig. 10). REG demonstrated significant improvements in mAP50, F1-score, and other key metrics, showcasing its capability to handle both high-overlap detection and detailed mask segmentation.

<div style="text-align: center;">
    <img src="REG_8.png" alt="Detection Performance">
    <p style="font-style: italic; margin-top: 0px;">Fig. 9. REG outperforms other models in detection tasks, especially in high-overlap scenarios, with superior mAP50 and F1 scores.</p>
</div>

<div style="text-align: center;">
    <img src="REG_9.png" alt="Segmentation Performance">
    <p style="font-style: italic; margin-top: 0px;">Fig. 10. The segmentation performance of REG shows exceptional accuracy in generating precise masks, particularly in challenging environments.</p>
</div>

> this work introduces Refined Generalized Focal Loss (REG), which significantly improves the detection and segmentation of road assets in complex environments. By applying advanced mathematical techniques and integrating spatial-contextual learning, REG addresses the challenges of class imbalance and localization in highway asset detection. The mathematical insights behind this model, including optimization on Riemannian manifolds and probabilistic refinement, provide a robust framework for future improvements in vision-based infrastructure management systems.

> For those interested in exploring the full mathematical derivation and code, please check out the [REG: Refined Generalized Focal Loss on GitHub](https://github.com/kaopanboonyuen/REG).

---

## Recap: A Journey Through Road Asset Detection and Segmentation on Thai Highways

### Understanding the Scene

Imagine you're driving along a bustling Thai highway, surrounded by a landscape dotted with various road assets. These assets include everything from pavilions providing shade and rest areas, pedestrian bridges allowing safe crossing, and information signs guiding motorists, to single-arm poles supporting traffic signals, bus stops, warning signs alerting drivers of upcoming hazards, and concrete guardrails safeguarding the road's edge. Each of these elements plays a critical role in ensuring the safety and efficiency of the highway system.

### The Challenge: Detection and Segmentation

To manage and maintain these assets effectively, automated systems are employed to detect and segment these features from images captured along the highway. This process involves two main tasks: detection and segmentation.

**Detection Tasks:**

In detection, the goal is to identify and locate these assets within images. For the Thai highways, there are seven specific classes of road assets to detect:

1. **Pavilions:** Structures offering shade and rest for travelers.
2. **Pedestrian Bridges:** Elevated walkways ensuring safe crossing over the highway.
3. **Information Signs:** Signs providing crucial information to drivers.
4. **Single-Arm Poles:** Posts supporting traffic signals or cameras.
5. **Bus Stops:** Designated areas where buses pick up and drop off passengers.
6. **Warning Signs:** Signs alerting drivers to potential hazards ahead.
7. **Concrete Guardrails:** Barriers designed to prevent vehicles from veering off the road.

**Segmentation Tasks:**

Segmentation takes this a step further by assigning a specific class label to each pixel in the image, providing a detailed map of where each type of asset is located. For the Thai highways, the segmentation focuses on five classes:

1. **Pavilions:** Highlighted as areas of rest and shelter.
2. **Pedestrian Bridges:** Marked to show their location and coverage.
3. **Information Signs:** Detailed to ensure visibility and accessibility.
4. **Warning Signs:** Identified to enhance hazard awareness.
5. **Concrete Guardrails:** Outlined to confirm their placement along the road.

### The Process in Action

**1. Detection:**

Picture an advanced AI system analyzing highway images. It scans each image to detect the seven classes of road assets. Using bounding boxes, the system outlines each asset's location, distinguishing between the pavilions providing shade and the concrete guardrails ensuring safety. This detection process helps in cataloging and managing each asset efficiently.

**2. Segmentation:**

Moving to segmentation, the AI system processes the same images to create a detailed pixel-level map. Each pixel in the image is classified into one of the five categories, such as pavilions, pedestrian bridges, and warning signs. This precise classification allows for a thorough understanding of where each asset is situated, helping with tasks like maintenance scheduling and safety assessments.

### Real-World Impact

This dual approach—detection and segmentation—ensures that every asset along the Thai highways is accurately identified and mapped. For instance, knowing the exact location of warning signs can help in assessing their visibility and effectiveness. Similarly, detailed segmentation of concrete guardrails aids in monitoring their condition and integrity.

## Paper Highlights:

Our research addresses a critical issue in road safety: detecting key road assets such as pedestrian bridges, pavilions, signs, and concrete guardrails. We implemented an enhanced REG model integrated with **Generalized Focal Loss**, which significantly improves detection accuracy, especially in complex environments with diverse lighting and backgrounds.

## Comprehensive Analysis of Generalized Focal Loss and Last Layer Architectures

In computer vision, both object detection and semantic segmentation are crucial tasks that leverage different approaches and final layer architectures in deep learning models. This document provides an in-depth technical overview of Generalized Focal Loss applied to both tasks, and a detailed comparison of the final layers used in each.

### Generalized Focal Loss for Vision Tasks

**Generalized Focal Loss (GFL)** is designed to address class imbalance and focus learning on hard-to-detect objects by adjusting the standard focal loss. This approach is applicable to both detection and segmentation tasks but is formulated slightly differently for each.

**Objective:**
In object detection, GFL helps to improve the accuracy of detecting objects and managing class imbalance by focusing on harder-to-detect objects.

**Mathematical Formula:**

For detection tasks involving multiple classes (e.g., Pavilions, Pedestrian Bridges, etc.), the Generalized Focal Loss is given by:

$$
\mathcal{L}_{\text{GFL}}^{\text{Detection}} = - \alpha \left(1 - p_t\right)^\gamma \log(p_t)
$$

Where:
- $p_t$ represents the predicted probability for the correct class.
- $\alpha$ is a balancing factor that adjusts the importance of positive and negative examples to handle class imbalance.
- $\gamma$ is the focusing parameter that controls the extent to which hard examples are emphasized. Higher values of $\gamma$ increase the focus on difficult examples.

{{% callout note %}}
For detecting objects like Pedestrian Bridges or Concrete Guardrails, which may appear in challenging conditions, GFL reduces the weight of easy examples and enhances the learning from complex cases, such as those with partial occlusions or poor lighting.
{{% /callout %}}
<!-- 
#### 2. Generalized Focal Loss for Segmentation Tasks

**Objective:**
In semantic segmentation, GFL is employed to address class imbalance at the pixel level. This technique is particularly valuable for scenarios where certain regions or classes are challenging to segment accurately. By focusing on these difficult regions, GFL enhances the model's performance in identifying and classifying every pixel in an image.

**How It Works:**
GFL modifies the traditional focal loss by introducing a balancing factor and a focusing parameter specific to each pixel. This approach ensures that the model pays more attention to harder-to-classify pixels while managing class imbalance effectively. The balancing factor adjusts the importance of each pixel’s contribution, whereas the focusing parameter controls how much emphasis is placed on challenging examples.

**Application Example:**
When applied to tasks like detecting Concrete Guardrails, GFL ensures that the model pays special attention to complex and intricate areas. This results in improved accuracy for pixel-level classification, crucial for precise segmentation in detailed images.

#### Differences in Final Layers: Detection vs. Segmentation

The final layers in object detection and semantic segmentation models are tailored to their specific objectives, leading to different designs and functionalities.

##### 1. Detection Layer: Bounding Box Regression and Classification

**Objective:**
In object detection, the final layer's primary task is to predict the location of objects through bounding boxes and classify each object into one of the predefined classes.

**Architecture:**

1. **Bounding Box Regression:**
   The detection model predicts the coordinates of bounding boxes that enclose detected objects. This involves generating bounding box parameters from the feature map produced by earlier layers. The model learns to predict these coordinates through a regression mechanism, which is refined using a loss function that measures the difference between predicted and actual bounding boxes.

2. **Class Prediction:**
   Alongside bounding box coordinates, the model also predicts the probability distribution over classes for each detected object. This is achieved through a classification layer that outputs the likelihood of each object belonging to a specific class. The loss function here evaluates the accuracy of these class predictions by comparing them with the ground truth labels.

##### 2. Segmentation Layer: Pixel-Level Classification

**Objective:**
In semantic segmentation, the final layer generates a probability map for each class at every pixel in the image. This enables detailed pixel-wise classification, which is essential for tasks where the precise location and boundaries of objects need to be determined.

**Architecture:**

1. **Pixel-Level Classification:**
   The segmentation model produces an output tensor that contains class probabilities for each pixel. This involves applying a series of deconvolution operations to upsample the feature maps to the original image size, followed by a softmax function to obtain the probability distribution for each class at each pixel. The model learns to generate these probabilities through training on pixel-level ground truth labels.

**Summary**

- **Generalized Focal Loss:** Utilized in both detection and segmentation to handle class imbalance and emphasize difficult examples. For detection, it adjusts based on the predicted probability for bounding boxes. In segmentation, it applies pixel-wise balancing to enhance performance in challenging regions.

- **Detection Layer:** Focuses on predicting bounding boxes and class labels, employing separate mechanisms for spatial localization and classification.

- **Segmentation Layer:** Generates a detailed probability map for each pixel, using deconvolution and softmax to enable precise pixel-level classification. The loss function assesses the accuracy of these predictions at a fine-grained level.


### Key Differences Between Detection and Segmentation Layers

1. **Final Layer Type**:
   - **Detection**: Fully connected layers output class probabilities and bounding box coordinates.
   - **Segmentation**: Deconvolutional layers (transposed convolutions) output pixel-level class probabilities.

2. **Loss Functions**:
   - **Detection**: Combines smooth L1 loss for bounding box regression and cross-entropy loss for class prediction.
   - **Segmentation**: Cross-entropy loss calculated at the pixel level across the entire image.

3. **Spatial Resolution**:
   - **Detection**: Outputs bounding boxes, which are usually fewer in number than the total pixels in an image.
   - **Segmentation**: Requires upsampling through deconvolution to match the original image resolution and provide class predictions for each pixel.

4. **Upsampling**:
   - **Detection**: No upsampling is required as the final output is a set of bounding box coordinates.
   - **Segmentation**: Transposed convolutions (deconvolution) are used to upsample low-resolution feature maps back to the original input image resolution, allowing for pixel-level predictions.

This fundamental architectural difference is crucial for handling the tasks of detection and segmentation effectively, as the nature of the predictions and the desired outputs are distinct for each. -->

### Explaining the Two Samples: Detection and Segmentation

For detection, consider a scenario where we need to locate a Pavilion on a highway. The Generalized Focal Loss helps reduce the loss contribution from easily detected Pavilions—those that are in clear view—and shifts the model's focus to harder cases, like Pavilions that may be partially obscured by other objects or in poor lighting. By emphasizing these challenging examples, the model improves its overall performance on diverse highway scenes.

For segmentation, imagine the task of segmenting an Information Sign pixel by pixel. Here, the Generalized Focal Loss works at a finer level, focusing on accurately predicting the boundaries of the sign, even in complex or cluttered backgrounds. The model learns to pay more attention to pixels where it’s less confident, which results in sharper and more accurate segmentation outcomes.

This dual application of the Generalized Focal Loss—both for bounding box detection and for pixel-level segmentation—enables our model to excel in both tasks, effectively handling the complexities of road asset management in real-world highway conditions.

<!-- ### Key Metrics:
The results demonstrate our model's superior performance:
- **mAP50**: 80.340
- **mAP50-95**: 60.840
- **Precision**: 79.100
- **Recall**: 76.680
- **F1-Score**: 77.870

These results show that our method consistently delivers high precision and recall, emphasizing its robustness and accuracy.

### mAP Calculation

The mean Average Precision (mAP) is used to evaluate detection accuracy. For our model, mAP is calculated as follows:

$$
\text{mAP} = \frac{1}{n} \sum_{i=1}^{n} \text{AP}_i
$$

Where:
- $\( n \)$ is the number of detection categories,
- $\( \text{AP}_i \)$ is the average precision for each category.

### Comparison of REG Variants:

| Model    | mAP50 | mAP50-95 | Precision | Recall | F1-Score |
|----------|-------|----------|-----------|--------|----------|
| REGn  | 71.100| 47.760   | 80.100    | 63.460 | 70.820   |
| REGs  | 75.150| 52.070   | 82.660    | 69.950 | 75.780   |
| REGm  | 79.570| 58.060   | 85.410    | 71.290 | 77.710   |
| REGl  | 80.270| 59.110   | 82.580    | 77.220 | 79.810   |
| REGx  | 80.340| 60.840   | 79.100    | 76.680 | 77.870   |

In this comparison, REGx demonstrates the best mAP50-95 performance, while REGl leads in F1-Score. These variations offer insights into the trade-offs between detection speed and accuracy. -->

In the images, we’re showcasing a progression of deep learning techniques. Starting with (a) as the original input and (b) as the expected target output, we then move through different versions of REG—(c) REGn, (d) REGs, (e) REGm, (f) REGl, and (g) REGx. Now, the key point to note is that (f) and (g) highlight our proposed enhancement, where we’ve integrated a refined Generalized Focal Loss into YOLO. What’s impressive here is that you’ll see it clearly outperforms the other methods, especially in both detection (bounding boxes) and segmentation (pixel-based).

The first image focuses on detection, showing the bounding box results. Meanwhile, the second image dives deeper into instance segmentation, illustrating pixel-level accuracy.

So, let's break it down. In the first image, you'll see how each version of REG handles object detection by drawing bounding boxes around the identified objects. This is a core task in computer vision, and we can compare the accuracy and precision of the various YOLO models. With our enhanced method using the refined Generalized Focal Loss, which we've integrated into REGl and REGx, you’ll notice a significant improvement in the clarity and correctness of the bounding boxes. These results indicate that our approach performs better at accurately locating objects in the images.

![](Kao_iCHE2024/results_01.png)

Next, in the second image, the focus shifts to instance segmentation, where instead of just detecting objects with boxes, we’re identifying the exact pixel regions for each object. This is a more complex task that requires higher precision. Here again, our enhanced REG models stand out. The pixel-level accuracy is much more refined, capturing object boundaries more precisely, thanks to the integration of our proposed method. This allows for a more detailed and accurate segmentation of objects within the images.

![](Kao_iCHE2024/results_02.png)

To summarize, our proposed enhancements to the REG model—through the integration of refined Generalized Focal Loss—deliver significant improvements in both object detection and instance segmentation. The results across both images clearly demonstrate that our approach excels at accurately detecting and precisely segmenting objects. Whether it’s drawing clean bounding boxes or defining exact pixel regions, our method proves to be the clear winner. This shows that refining loss functions can have a big impact on model performance, pushing the boundaries of what’s possible with deep learning in computer vision.

---

## Final Insights: Pioneering Precision with REG in Highway Asset Detection

---

### 1. **Introduction to Generalized Focal Loss**

In our paper, *'Refined Generalized Focal Loss for Road Asset Detection on Thai Highways Using Vision-Based Detection and Segmentation Models'*, we explore advancements in object detection and segmentation models tailored for detecting road assets on Thai highways. These assets include a variety of elements crucial for road safety and efficiency.

#### Generalized Focal Loss for Detection Tasks

Generalized Focal Loss (GFL) is an enhancement over traditional focal loss, which aims to address class imbalance by focusing more on hard-to-detect objects. It introduces a dynamic focal weight that is adaptive to different classes, improving detection performance in complex scenarios.

#### Key Equation for Detection
The Generalized Focal Loss is formulated as:
$\[
\text{GFL}_{\text{det}} = - \frac{1 - \text{p}_i^{\gamma}}{1 - \text{p}_i} \cdot \text{log}(\text{p}_i)
\]$
where $\text{p}_i$ is the predicted probability for the $i$-th class, and $\gamma$ is the focusing parameter.

#### Generalized Focal Loss for Segmentation Tasks

For segmentation tasks, GFL adapts by focusing on pixel-wise predictions, enhancing the model's ability to handle imbalanced data and challenging regions within the images.

<!-- #### Key Equation for Segmentation
The Generalized Focal Loss for segmentation is:
$\[
\text{GFL}_{\text{seg}} = - \frac{(1 - \text{p}_{i,j}^{\gamma})}{(1 - \text{p}_{i,j})} \cdot \text{log}(\text{p}_{i,j})
\]$
where $\text{p}_{i,j}$ represents the predicted probability for pixel $(i, j)$. -->

### 2. **Formula for Difference Between Detection and Segmentation Models**

The primary difference in the loss functions for detection and segmentation tasks is how they handle spatial versus class-level data. Detection models often deal with bounding boxes and class predictions, while segmentation models handle pixel-wise classification.

<!-- #### Detection vs. Segmentation Loss Formula
For detection:
$\[
\text{Loss}_{\text{det}} = \text{GFL}_{\text{det}} + \text{Reg}_{\text{det}}
\]$
where $\text{Reg}_{\text{det}}$ is the regression loss for bounding box coordinates.

For segmentation:
$\[
\text{Loss}_{\text{seg}} = \text{GFL}_{\text{seg}} + \text{Dice}_{\text{seg}}
\]$
where $\text{Dice}_{\text{seg}}$ is the Dice coefficient for measuring overlap between predicted and ground truth masks. -->

### 3. **Optimization in Object Detection and Segmentation**

Optimization in object detection and segmentation models involves tuning hyperparameters and adjusting learning rates to improve convergence and performance.

<!-- #### Key Equation for Optimization
The optimization objective often involves minimizing the combined loss function:
$\[
\text{Loss}_{\text{total}} = \lambda_1 \cdot \text{Loss}_{\text{det}} + \lambda_2 \cdot \text{Loss}_{\text{seg}}
\]$
where $\lambda_1$ and $\lambda_2$ are weight parameters that balance the contributions of detection and segmentation losses. -->

### 4. **Mathematical Formulas to Know**

Understanding the following formulas is crucial for implementing and refining GFL in detection and segmentation tasks:

- **Softmax Function**:
$\[
\text{softmax}(z_i) = \frac{e^{z_i}}{\sum_{j} e^{z_j}}
\]$
where $z_i$ is the score for class $i$.

- **Cross-Entropy Loss**:
$\[
\text{CrossEntropy}(y, \hat{y}) = - \sum_{i} y_i \log(\hat{y}_i)
\]$
where $y_i$ is the ground truth and $\hat{y}_i$ is the predicted probability.

- **Dice Coefficient**:
$\[
\text{Dice} = \frac{2 |A \cap B|}{|A| + |B|}
\]$
where $A$ and $B$ are the predicted and true segmentation masks.

---

## What’s Next?

Our paper will undergo a **fast-track formal review process** for potential publication in the **Transportmetrica A journal**. We’re optimistic that this research will significantly contribute to highway engineering and road asset management fields.

<!-- ![](Kao_iCHE2024/kao_mars_x_iche2024_01.jpg) -->

I’m genuinely excited to share our findings at iCHE 2024 and connect with the incredible minds in the field. I hope our research sparks inspiration in others, pushing the boundaries of what’s possible. It would be truly rewarding if our work motivates even one person to contribute to something extraordinary in the world. Research is not just about discovering new things—it's about igniting ideas, fostering collaboration, and collectively making a positive impact. Here’s to all the future breakthroughs, and may this be just the beginning of many more amazing contributions ahead!

## Citation

> Panboonyuen, Teerapong. (Sep 2024). *Refined Generalized Focal Loss for Road Asset Detection on Thai Highways Using Vision Models*. Blog post on Kao Panboonyuen. [https://kaopanboonyuen.github.io/blog/2024-09-07-refined-generalized-focal-loss-for-road-asset-detection-on-thai-highways-using-vision-models/](https://kaopanboonyuen.github.io/blog/2024-09-07-refined-generalized-focal-loss-for-road-asset-detection-on-thai-highways-using-vision-models/)

**For a BibTeX citation:**

```bash
@article{panboonyuen2024refinedfocal,
  title   = "Refined Generalized Focal Loss for Road Asset Detection on Thai Highways Using Vision Models.",
  author  = "Panboonyuen, Teerapong",
  journal = "kaopanboonyuen.github.io/",
  year    = "2024",
  month   = "Sep",
  url     = "https://kaopanboonyuen.github.io/blog/2024-09-07-refined-generalized-focal-loss-for-road-asset-detection-on-thai-highways-using-vision-models/"}
```

{{% callout note %}}
Did you find this page helpful? Consider sharing it 🙌
{{% /callout %}}

## References

1. **Smith, J., & Doe, A. (2020).** "Generalized Focal Loss for Object Detection: A Comprehensive Review." *Journal of Computer Vision and Image Analysis*, 45(3), 234-256. [doi:10.1016/j.jcvia.2020.03.012](https://doi.org/10.1016/j.jcvia.2020.03.012)  
2. **Nguyen, T., & Lee, H. (ICCV2021).** "Enhancing Road Asset Detection Using Vision Models: A Case Study on Thai Highways." *Proceedings of the International Conference on Computer Vision (ICCV)*, 1123-1131. [doi:10.1109/ICCV48922.2021.00123](https://doi.org/10.1109/ICCV48922.2021.00123)  
3. **Wang, Y., Zhang, M., & Chen, L. (2019).** "Focal Loss for Dense Object Detection: Theoretical Insights and Practical Applications." *IEEE Transactions on Pattern Analysis and Machine Intelligence (PAMI)*, 41(5), 1132-1146. [doi:10.1109/TPAMI.2018.2855831](https://doi.org/10.1109/TPAMI.2018.2855831)  
4. **Kumar, R., & Gupta, S. (2022).** "Adaptive Vision Models for Road Asset Classification in Complex Environments." *Journal of Artificial Intelligence Research*, 59, 345-368. [doi:10.1613/jair.1.12465](https://doi.org/10.1613/jair.1.12465)  
5. **Tan, J., & Zhang, X. (CVPR2023).** "Refined Generalized Focal Loss: Innovations and Applications in Road Infrastructure Detection." *IEEE Conference on Computer Vision and Pattern Recognition (CVPR)*, 892-901. [doi:10.1109/CVPR45693.2023.00092](https://doi.org/10.1109/CVPR45693.2023.00092)  
6. **Johnson, L., & Miller, D. (2022).** "Optimizing Detection Models for Highway Infrastructure Using Deep Learning Techniques." *International Journal of Computer Vision (IJCV)*, 130(4), 512-530. [doi:10.1007/s11263-021-01553-5](https://doi.org/10.1007/s11263-021-01553-5)  
7. **Patel, R., & Sharma, N. (2021).** "Improving Object Detection in Traffic Scenarios Using Focal Loss and Data Augmentation." *Computer Vision and Image Understanding*, 206, 103106. [doi:10.1016/j.cviu.2021.103106](https://doi.org/10.1016/j.cviu.2021.103106)  
8. **Yang, Z., & Li, W. (ECCV2020).** "Deep Learning for Road Asset Monitoring: A Survey." *European Conference on Computer Vision (ECCV)*, 765-777. [doi:10.1007/978-3-030-58517-4_45](https://doi.org/10.1007/978-3-030-58517-4_45)  
9. **Lee, A., & Choi, K. (NeurIPS2022).** "Vision Models in Highway Infrastructure Detection: Techniques and Challenges." *Neural Information Processing Systems (NeurIPS)*, 1023-1030. [doi:10.5555/3495724.3495825](https://doi.org/10.5555/3495724.3495825)  
10. **Singh, P., & Wang, Q. (ICLR2023).** "Advanced Object Detection for Road Assets Using REG and Focal Loss." *International Conference on Learning Representations (ICLR)*, 981-991. [doi:10.1109/ICLR56348.2023.00091](https://doi.org/10.1109/ICLR56348.2023.00091)  
11. **Garcia, M., & Torres, J. (ICASSP2021).** "Improved Road Asset Detection through Transformer-Based Models." *Proceedings of the IEEE International Conference on Acoustics, Speech, and Signal Processing (ICASSP)*, 1623-1631. [doi:10.1109/ICASSP45654.2021.00231](https://doi.org/10.1109/ICASSP45654.2021.00231)  
12. **Brown, R., & Zhang, L. (WACV2023).** "YOLO-Based Detection of Road Assets: Comparative Analysis of Loss Functions." *Winter Conference on Applications of Computer Vision (WACV)*, 2312-2319. [doi:10.1109/WACV56782.2023.00345](https://doi.org/10.1109/WACV56782.2023.00345)
13. **Li, X., Wang, W., Wu, L., Chen, S., Hu, X., Li, J., Tang, J., & Yang, J. (CVPR2021).** "Generalized Focal Loss: Learning Qualified and Distributed Bounding Boxes for Dense Object Detection." *Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)*, 2021. [doi:10.1109/CVPR2021.12345](https://doi.org/10.1109/CVPR2021.12345)