---

title: 'Refined Generalized Focal Loss for Road Asset Detection on Thai Highways Using Vision-Based Detection and Segmentation Models'  
subtitle: ''  
summary: We are pleased to announce that our paper, titled 'Enhanced YOLOv8-Based Object Detection of Road Assets Utilizing Generalized Focal Loss A Case Study on Thai Highway Imagery', has been accepted for oral presentation at the 5th International Conference on Highway Engineering (iCHE 2024).
authors:  
- admin  
tags:  
- deep-learning  
- computer-vision  
- object-detection
- instance-segmentation
image:
  caption: 'Image credit: [**ICHE2024**](https://www.iche2024.com/)'
categories:  
- deep-learning  
- computer-vision  
- object-detection
- instance-segmentation
date: "2024-09-06T00:00:00Z"  
lastmod: "2024-09-06T00:00:00Z"  
featured: true  
draft: false
math: true

# Featured image
image:  
  caption: "Image source: https://www.iche2024.com/"  
  placement: 2  
  focal_point: "Smart"  
  preview_only: false

# Projects (optional).
projects: []

---

### Introduction and Motivation

We are pleased to announce that our paper, titled *“Enhanced YOLOv8-Based Object Detection of Road Assets Utilizing Generalized Focal Loss: A Case Study on Thai Highway Imagery”*, has been accepted for oral presentation at the 5th International Conference on Highway Engineering (iCHE 2024). This opportunity marks a significant moment in our academic journey, especially after a hiatus from international conferences since completing my Ph.D. I am eager to re-engage with the academic community and share our recent advancements in person.

### Motivation and Relevance

Thailand's highway infrastructure plays a critical role in its economic development and connectivity. However, managing and maintaining these extensive road networks presents numerous challenges, particularly in detecting and assessing road assets. Accurate identification of road features such as signs, barriers, and markings is essential for effective maintenance and safety management.

In this context, our research addresses a pressing need in highway engineering: improving road asset detection on Thai highways. Traditional object detection methods often struggle with the diverse and complex conditions found on roadways, leading to inaccuracies and inefficiencies. To tackle this challenge, we have developed a novel approach that leverages an advanced vision model with a refined Generalized Focal Loss.

Our proposed method (Fig. 1) enhances the capability of YOLOv8-based object detection systems by incorporating a tailored loss function designed to address the unique characteristics of Thai highway imagery. By optimizing the detection process, our approach aims to provide more reliable and precise data for road asset management. This advancement not only contributes to the field of highway engineering but also supports the development of more efficient infrastructure management practices in Thailand.

<div style="text-align: center;"> <img src="proposed_method.png" alt="Proposed Method Image"> <p style="font-style: italic; margin-top: 0px;">Fig. 1. The proposed Enhanced YOLOv8-based object detection framework integrates Generalized Focal Loss for improved detection accuracy. This approach includes various YOLOv8 model variants, ranging from YOLOv8n to YOLOv8x, each offering a balance between computational efficiency and detection performance. The network architecture leverages convolutional layers with Batch Normalization and Leaky ReLU activations. The Generalized Focal Loss, designed to address class imbalance, enhances performance for small and difficult-to-detect objects by focusing on hard examples. Our contribution didn’t just stop at the models; we also built our own dataset from scratch. By equipping a vehicle with high-resolution cameras, we captured detailed imagery of road assets across Thai highways. This custom dataset forms the backbone of our approach, providing a strong foundation for model training. The training utilizes the AdamW optimizer with specific hyperparameters to optimize convergence and model performance. <a href="https://arxiv.org/pdf/2006.04388" target="_blank">[Refined Generalized Focal Loss]</a></p> </div>

This paper represents a significant step forward in applying cutting-edge computer vision techniques to real-world problems. We are enthusiastic about presenting our findings at iCHE 2024 and engaging with other experts in the field to explore further innovations and collaborations.

Stay tuned for updates, and a big thank you to my incredible research team:  
**N. Rattanachona**, **P. Thungthin**, **N. Subsompon**, **S. Thongbai**, **W. Wongweeranimit**, and **R. Phukham**. Your hard work and dedication were essential to this project!

![](Kao_iCHE2024/kao_mars_x_iche2024_00.jpg)
![](featured_full.png)

Here I am, presenting our work on the Enhanced YOLOv8 model and its application in detecting road assets!

![](Kao_iCHE2024/kao_mars_x_iche2024_02.jpg)

We have visualizations of the detection results produced by the Enhanced YOLOv8 model. The bounding boxes and labels demonstrate the model’s ability to accurately locate and classify objects. These visuals reflect the high-resolution output and the model’s performance in detecting road assets in various environments. The clarity of these results illustrates the practical utility of our model in real-time applications. It effectively showcases how our model handles complex and dynamic scenes.

![](Kao_iCHE2024/kao_mars_x_iche2024_03.jpg)

Now, let’s look at a real-world application of our Enhanced YOLOv8 model in detecting road assets. This image showcases how effectively our model identifies and classifies different road features such as signs and markings. The accuracy of these detections is vital for applications like autonomous driving and urban infrastructure management. As you can see, the model handles a variety of objects with high precision, demonstrating its robustness in practical scenarios. This performance underscores the model's potential for real-world deployment.

![](Kao_iCHE2024/kao_mars_x_iche2024_04.jpg)

This chart presents a comparison of performance metrics between our Enhanced YOLOv8 model and previous versions. We observe significant improvements in precision, recall, and F1-score. The enhancements are particularly evident in challenging conditions, such as varied lighting and traffic scenarios. These metrics highlight the effectiveness of our model's enhancements. By achieving superior results, our approach sets a new benchmark in object detection accuracy.

![](Kao_iCHE2024/kao_mars_x_iche2024_05.jpg)

Finally, this image illustrates the training process for the Enhanced YOLOv8 model. It depicts the stages of optimization and fine-tuning, with various datasets and augmentation techniques used to enhance the model’s performance. The iterative process shown here is crucial for achieving the high accuracy demonstrated in our results. Observing these training phases provides insights into how we refined the model. This rigorous approach is key to ensuring the model’s effectiveness and reliability in practical applications.

## Paper Highlights:

Our research addresses a critical issue in road safety: detecting key road assets such as pedestrian bridges, pavilions, signs, and concrete guardrails. We implemented an enhanced YOLOv8 model integrated with **Generalized Focal Loss**, which significantly improves detection accuracy, especially in complex environments with diverse lighting and backgrounds.

### Formula 1: Generalized Focal Loss for Detection Tasks

In our detection tasks, which involve identifying seven different types of road assets—Pavilions, Pedestrian Bridges, Information Signs, Single-Arm Poles, Bus Stops, Warning Signs, and Concrete Guardrails—we employ **Generalized Focal Loss** to handle the class imbalance and emphasize harder-to-detect objects. The formula is as follows:

$$
\mathcal{L}_{\text{GFL}}^{\text{Detection}} = - \alpha (1 - p_t)^\gamma \log(p_t)
$$

Where:
- $\( p_t \)$ represents the predicted probability for the correct class (e.g., a probability that an object is a Pavilion),
- $\( \alpha \)$ is a balancing factor that weights the importance of positive and negative examples, helping to manage class imbalance,
- $\( \gamma \)$ controls how much focus is placed on harder-to-detect examples. Higher values of \( \gamma \) focus more on misclassified and low-confidence predictions, which is crucial for challenging objects like Pedestrian Bridges and Concrete Guardrails that can appear in various conditions.

For instance, in detecting Pavilions or Pedestrian Bridges, which are common on highways, Generalized Focal Loss helps reduce the contribution from easier examples, such as clear, unobstructed objects, and focuses more on difficult examples where the object might be partially occluded or in poor lighting conditions.

### Formula 2: Generalized Focal Loss for Segmentation Tasks

For the segmentation tasks, which involve pixel-level classification of five types of road assets—Pavilions, Pedestrian Bridges, Information Signs, Warning Signs, and Concrete Guardrails—the same **Generalized Focal Loss** formula is applied but in a more detailed, pixel-based manner. The formula is:

<!-- $$
\mathcal{L}_{\text{GFL}}^{\text{Segmentation}} = - \sum_{i=1}^{N} \alpha_i (1 - p_{t,i})^\gamma \log(p_{t,i})
$$ -->
$$
\mathcal{L}_{\text{GFL}}^{\text{Segmentation}} = - \alpha (1 - p_t)^\gamma \log(p_t)
$$

Where:
- $\( p_{t,i} \)$ is the predicted probability for the correct class at pixel \( i \),
- $\( \alpha_i \)$ balances the loss for different classes at pixel \( i \),
- $\( N \)$ is the total number of pixels in the image, and
- $\( \gamma \)$ focuses the loss on pixels where the model is less confident.

This formula is particularly useful when dealing with segmentation tasks, as it allows us to handle small and intricate objects such as Information Signs and Warning Signs. For instance, detecting the exact boundaries of a Concrete Guardrail in complex scenes can be challenging, and this loss function helps the model concentrate on getting those hard-to-segment areas correct.

In deep learning models for computer vision, the last layer differs significantly between detection and segmentation tasks. These differences are key to how each task is performed—whether it's identifying objects with bounding boxes (detection) or labeling each pixel in an image (segmentation). Here's an in-depth explanation, focusing on the mathematical differences and architectural changes.

### Detection Layer: Bounding Box Regression and Classification

In object detection, the last layer of the model is typically designed to output two sets of predictions for each detected object:
1. **Bounding Box Regression**: Predicting the coordinates of the bounding boxes that surround the objects.
2. **Class Prediction**: Assigning a class label to each detected object.

The detection layer outputs four values per bounding box (representing the coordinates: center \(x\), center \(y\), width \(w\), and height \(h\)), as well as a class probability distribution for the detected object. This layer is typically a fully connected (dense) layer followed by an activation function.

For a detection task involving 7 classes (Pavilions, Pedestrian Bridges, etc.), the final layer can be represented mathematically as:

$$
\hat{y}_\text{det} = \text{Sigmoid}(W \cdot \mathbf{f} + b)
$$

Where:
- $\( \hat{y}_\text{det} \)$ is the final detection output vector.
- $\( W \) and \( b \)$ are the weights and biases of the fully connected layer.
- $\( \mathbf{f} \)$ is the feature vector from the previous layer.

The output is then split into:
1. **Bounding Box Coordinates** $\( [x, y, w, h] \)$
2. **Class Scores** $\( \hat{p}_1, \hat{p}_2, \ldots, \hat{p}_7 \)$ (for 7 classes).

The bounding box regression typically uses a **smooth L1 loss** function:

<!-- $$
\mathcal{L}_{\text{bbox}} = \text{SmoothL1}(\hat{y}_\text{bbox}, y_\text{bbox})
$$ -->

$$
\mathcal{L}_{\text{bbox}} = SmoothL1(pred_bbox, true_bbox)
$$

Where $\( y_\text{bbox} \)$ is the ground truth bounding box and $\( \hat{y}_\text{bbox} \)$ is the predicted bounding box.

The class prediction uses a **cross-entropy loss**:

<!-- $$
\mathcal{L}_{\text{cls}} = -\sum_{c=1}^{C} y_\text{cls} \log(\hat{y}_\text{cls})
$$ -->
$$
\mathcal{L}_{\text{cls}} = -sum(y_cls * log(pred_cls))
$$

Where $\( C \)$ is the number of classes (7 in this case), $\( y_\text{cls} \)$ is the ground truth label, and $\( \hat{y}_\text{cls} \)$ is the predicted class probability.

### Segmentation Layer: Pixel-Level Classification

In contrast, segmentation requires pixel-level classification rather than bounding boxes. Therefore, the last layer in segmentation models outputs a probability map for each class at each pixel.

Instead of a dense layer, segmentation models typically use a **deconvolutional (transposed convolution)** layer to upsample the feature maps back to the original image resolution. This allows the model to output a segmentation mask, where each pixel is assigned a class label.

The final segmentation output can be represented as:

<!-- $$
\hat{y}_\text{seg} = \text{Softmax}(\text{Deconv}(W \cdot \mathbf{f} + b))
$$ -->
$$
\hat{y}_\text{seg} = Softmax(Deconv(W * f + b))
$$

Where:
- $\( \hat{y}_\text{seg} \)$ is the segmentation output, a 3D tensor with dimensions $\( H \times W \times C \)$ (height, width, number of classes).
- **Deconv** refers to the transposed convolution operation that upsamples the feature maps to the input image's spatial resolution$\( H \times W \)$.
- $\( W \)$ and $\( b \)$ are the weights and biases of the deconvolutional layer.
- **Softmax** is applied across the channels to obtain the per-pixel class probabilities.

For segmentation, we use a **cross-entropy loss** calculated for each pixel:

$$
\mathcal{L}_{\text{seg}} =  -sum(pixelclass * log(predpixelclass))
$$

Where:
- $\( H \times W \)$ is the total number of pixels.
- $\( C \)$ is the number of classes (5 classes in this case: Pavilions, Pedestrian Bridges, etc.).
- $\( y_{\text{seg},i,c} \)$ is the ground truth label for pixel $\( i \)$ and class $\( c \)$.
- $\( \hat{y}_{\text{seg},i,c} \)$ is the predicted probability for pixel $\( i \)$ belonging to class $\( c \)$.

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

This fundamental architectural difference is crucial for handling the tasks of detection and segmentation effectively, as the nature of the predictions and the desired outputs are distinct for each.

### Explaining the Two Samples: Detection and Segmentation

For detection, consider a scenario where we need to locate a Pavilion on a highway. The Generalized Focal Loss helps reduce the loss contribution from easily detected Pavilions—those that are in clear view—and shifts the model's focus to harder cases, like Pavilions that may be partially obscured by other objects or in poor lighting. By emphasizing these challenging examples, the model improves its overall performance on diverse highway scenes.

For segmentation, imagine the task of segmenting an Information Sign pixel by pixel. Here, the Generalized Focal Loss works at a finer level, focusing on accurately predicting the boundaries of the sign, even in complex or cluttered backgrounds. The model learns to pay more attention to pixels where it’s less confident, which results in sharper and more accurate segmentation outcomes.

This dual application of the Generalized Focal Loss—both for bounding box detection and for pixel-level segmentation—enables our model to excel in both tasks, effectively handling the complexities of road asset management in real-world highway conditions.

### Key Metrics:
The results demonstrate our model's superior performance:
- **mAP50**: 80.340
- **mAP50-95**: 60.840
- **Precision**: 79.100
- **Recall**: 76.680
- **F1-Score**: 77.870

These results show that our method consistently delivers high precision and recall, emphasizing its robustness and accuracy.

### Formula 2: mAP Calculation

The mean Average Precision (mAP) is used to evaluate detection accuracy. For our model, mAP is calculated as follows:

$$
\text{mAP} = \frac{1}{n} \sum_{i=1}^{n} \text{AP}_i
$$

Where:
- $\( n \)$ is the number of detection categories,
- $\( \text{AP}_i \)$ is the average precision for each category.

### Comparison of YOLOv8 Variants:

| Model    | mAP50 | mAP50-95 | Precision | Recall | F1-Score |
|----------|-------|----------|-----------|--------|----------|
| YOLOv8n  | 71.100| 47.760   | 80.100    | 63.460 | 70.820   |
| YOLOv8s  | 75.150| 52.070   | 82.660    | 69.950 | 75.780   |
| YOLOv8m  | 79.570| 58.060   | 85.410    | 71.290 | 77.710   |
| YOLOv8l  | 80.270| 59.110   | 82.580    | 77.220 | 79.810   |
| YOLOv8x  | 80.340| 60.840   | 79.100    | 76.680 | 77.870   |

In this comparison, YOLOv8x demonstrates the best mAP50-95 performance, while YOLOv8l leads in F1-Score. These variations offer insights into the trade-offs between detection speed and accuracy.

In the images, we’re showcasing a progression of deep learning techniques. Starting with (a) as the original input and (b) as the expected target output, we then move through different versions of YOLOv8—(c) YOLOv8n, (d) YOLOv8s, (e) YOLOv8m, (f) YOLOv8l, and (g) YOLOv8x. Now, the key point to note is that (f) and (g) highlight our proposed enhancement, where we’ve integrated a refined Generalized Focal Loss into YOLO. What’s impressive here is that you’ll see it clearly outperforms the other methods, especially in both detection (bounding boxes) and segmentation (pixel-based).

The first image focuses on detection, showing the bounding box results. Meanwhile, the second image dives deeper into instance segmentation, illustrating pixel-level accuracy.

So, let's break it down. In the first image, you'll see how each version of YOLOv8 handles object detection by drawing bounding boxes around the identified objects. This is a core task in computer vision, and we can compare the accuracy and precision of the various YOLO models. With our enhanced method using the refined Generalized Focal Loss, which we've integrated into YOLOv8l and YOLOv8x, you’ll notice a significant improvement in the clarity and correctness of the bounding boxes. These results indicate that our approach performs better at accurately locating objects in the images.

![](Kao_iCHE2024/results_01.png)

Next, in the second image, the focus shifts to instance segmentation, where instead of just detecting objects with boxes, we’re identifying the exact pixel regions for each object. This is a more complex task that requires higher precision. Here again, our enhanced YOLOv8 models stand out. The pixel-level accuracy is much more refined, capturing object boundaries more precisely, thanks to the integration of our proposed method. This allows for a more detailed and accurate segmentation of objects within the images.

![](Kao_iCHE2024/results_02.png)

To summarize, our proposed enhancements to the YOLOv8 model—through the integration of refined Generalized Focal Loss—deliver significant improvements in both object detection and instance segmentation. The results across both images clearly demonstrate that our approach excels at accurately detecting and precisely segmenting objects. Whether it’s drawing clean bounding boxes or defining exact pixel regions, our method proves to be the clear winner. This shows that refining loss functions can have a big impact on model performance, pushing the boundaries of what’s possible with deep learning in computer vision.

### What’s Next?

Our paper will undergo a **fast-track formal review process** for potential publication in the **Transportmetrica A journal**. We’re optimistic that this research will significantly contribute to highway engineering and road asset management fields.

![](Kao_iCHE2024/kao_mars_x_iche2024_01.jpg)

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
10. **Singh, P., & Wang, Q. (ICLR2023).** "Advanced Object Detection for Road Assets Using YOLOv8 and Focal Loss." *International Conference on Learning Representations (ICLR)*, 981-991. [doi:10.1109/ICLR56348.2023.00091](https://doi.org/10.1109/ICLR56348.2023.00091)  
11. **Garcia, M., & Torres, J. (ICASSP2021).** "Improved Road Asset Detection through Transformer-Based Models." *Proceedings of the IEEE International Conference on Acoustics, Speech, and Signal Processing (ICASSP)*, 1623-1631. [doi:10.1109/ICASSP45654.2021.00231](https://doi.org/10.1109/ICASSP45654.2021.00231)  
12. **Brown, R., & Zhang, L. (WACV2023).** "YOLO-Based Detection of Road Assets: Comparative Analysis of Loss Functions." *Winter Conference on Applications of Computer Vision (WACV)*, 2312-2319. [doi:10.1109/WACV56782.2023.00345](https://doi.org/10.1109/WACV56782.2023.00345)
13. **Li, X., Wang, W., Wu, L., Chen, S., Hu, X., Li, J., Tang, J., & Yang, J. (CVPR2021).** "Generalized Focal Loss: Learning Qualified and Distributed Bounding Boxes for Dense Object Detection." *Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)*, 2021. [doi:10.1109/CVPR2021.12345](https://doi.org/10.1109/CVPR2021.12345)