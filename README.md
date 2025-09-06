# Generative Domain Adaptation for Remote Sensing Object Detection

![BN4](https://github.com/user-attachments/assets/a9456989-b568-46b7-82bd-2678154345c9)



<p align="justify">
This repository contains the official dataset and information for the paper: <strong>"Generative Domain Adaptation for Object Detection in Remote Sensing Imagery through Automated Feature-Driven Exemplar In-painting."</strong>
</p>

<p align="justify">
Our work introduces a novel end-to-end pipeline for generating high-fidelity synthetic data to address the common challenges of data scarcity, geographic bias, and limited background diversity in remote sensing object detection. By leveraging a Generative Adversarial Network (GAN) and an intelligent in-painting strategy, we create a powerful pre-training corpus that significantly enhances the generalization and performance of modern object detection models.
</p>

## 📂 The MEA10K Dataset

<p align="justify">
We provide the MEA10K dataset to facilitate new research in generative modeling, domain adaptation, and robust object detection in the remote sensing domain.
</p>

### **MEA10K: The Complete Synthetic Object Detection Dataset**
<p align="justify">
This is the primary dataset used for the domain adaptation experiments in our paper. It features photorealistic, GAN-generated backgrounds populated with a diverse set of stochastically placed object exemplars.
</p>

*   **Content:** 10,000 synthetic images with object annotations.
*   **Dimensions:** 1024x1024 pixels.
*   **Object Classes:** 19 distinct categories.
*   **Annotations:** Provided in YOLO (<code>.txt</code>) format. Each annotation file contains one line per object with the format: <code>[class_id] [x_center_norm] [y_center_norm] [width_norm] [height_norm]</code>. A <code>data.yaml</code> file is included for class name mapping.
*   **Download Link:** [Google Drive](https://drive.google.com/file/d/1LEqF7NZXnAscYfViFy8eZka3P5vEf0_K/view?usp=sharing)


## 🚀 Pipeline Overview

<p align="justify">
The MEA10K dataset was created using a two-branch pipeline:
</p>

<ol>
  <li>
    <p align="justify">
      <strong>Background Synthesis:</strong> We trained a Generative Adversarial Network (GAN) on a massive collection of over 30,000 globally-sourced Google Earth images. This model learned the underlying distribution of real-world overhead imagery and was used to generate photorealistic backgrounds.
    </p>
  </li>
  <li>
    <p align="justify">
      <strong>Multi-Model Exemplar Selection and In-painting:</strong> We developed an automated method to select a pool of four distinct representative exemplars for each of our 19 classes. Each exemplar was identified by a different 'specialist' vision model (ResNet, ViT, DINOv2, and CLIP) based on its unique feature embeddings. These exemplars were then subjected to stochastic augmentations (rotation, scale, color) and pasted context-agnostically onto the synthetic backgrounds. For each object placed in an image, an exemplar was randomly chosen from its class-specific pool of four, ensuring high visual diversity in the final <code>MEA10K</code> dataset.
    </p>
  </li>
</ol>


<p align="center">
    <img src="https://github.com/user-attachments/assets/57526b46-ca9e-41a2-bcd4-2769bcfe7ae9" alt="DREW" width="65%" />
</p>



---

## 📄 Citation

<p align="justify">
If you use the <strong>MEA10K dataset</strong> or find our work helpful in your research, please cite our paper:
</p>

```bibtex
@article{aghili2025generative,
  title={Generative Domain Adaptation for Object Detection in Remote Sensing Imagery through Automated Feature-Driven Exemplar In-painting},
  author={Aghili, Mohamad Ebrahim and Ghassemian, Hassan and Imani, Maryam},
  journal={Journal Name},
  volume={XX},
  number={Y},
  pages={ZZZ--ZZZ},
  year={2025},
  publisher={Publisher}
}
