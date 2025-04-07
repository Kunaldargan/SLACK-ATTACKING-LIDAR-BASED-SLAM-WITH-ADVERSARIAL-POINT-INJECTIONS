---

# SLACK: Attacking LiDAR-Based SLAM with Adversarial Point Injections

This repository contains the official implementation of **SLACK: Attacking LiDAR-Based SLAM with Adversarial Point Injections**, a novel approach to attack LiDAR-based SLAM systems using adversarial point injections.

📄 **Paper:**  
[Kumar, Prashant et al. "SLACK: Attacking LiDAR-Based SLAM with Adversarial Point Injections"](https://doi.org/10.48550/arXiv.2504.03089)  
*Presented at the 2024 IEEE International Conference on Image Processing Challenges and Workshops (ICIPCW).*

---

## 🧠 Overview

Simultaneous Localization and Mapping (SLAM) is a critical component in autonomous navigation. SLACK demonstrates a vulnerability in LiDAR-based SLAM pipelines by injecting carefully crafted adversarial points that can degrade localization accuracy and even cause catastrophic failure of SLAM systems.

The widespread adoption of learning-based methods for the LiDAR makes autonomous vehicles vulnerable to adversarial attacks through adversarial \textit{point injections (PiJ)}. It poses serious security challenges for navigation and map generation. Despite its critical nature, no major work exists that studies learning-based attacks on LiDAR-based SLAM. Our work proposes SLACK, an end-to-end deep generative adversarial model to attack LiDAR scans with several point injections without deteriorating LiDAR quality. To facilitate SLACK, we design a novel yet simple autoencoder that augments contrastive learning with segmentation-based attention for precise reconstructions. SLACK demonstrates superior performance on the task of \textit{point injections (PiJ)} compared to the best baselines on KITTI and CARLA-64 dataset while maintaining accurate scan quality. We qualitatively and quantitatively demonstrate PiJ attacks using a fraction of LiDAR points. It severely degrades navigation and map quality without deteriorating the LiDAR scan quality. 

Key highlights:
- Attacks both feature-based and dense-mapping SLAM algorithms.
- Evaluated on popular open-source SLAM systems like LOAM and Cartographer.
- Introduces a black-box and white-box attack strategy.
- Utilizes contrastive learning to improve adversarial point generation.

---

## 📁 Project Structure

```bash
SLACK-ATTACKING-LIDAR-BASED-SLAM-WITH-ADVERSARIAL-POINT-INJECTIONS/
│
├── data/                   # Sample datasets and LiDAR sequences
├── slam_attack/           # Core attack logic and model code
├── configs/               # Configuration files
├── utils/                 # Helper scripts for visualization, evaluation, etc.
├── results/               # Precomputed outputs and evaluation logs
├── requirements.txt       # Python dependencies
└── README.md              # This file
```

---

## ⚙️ Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/SLACK-ATTACKING-LIDAR-BASED-SLAM-WITH-ADVERSARIAL-POINT-INJECTIONS.git
   cd SLACK-ATTACKING-LIDAR-BASED-SLAM-WITH-ADVERSARIAL-POINT-INJECTIONS
   ```

2. **Set up a virtual environment (optional)**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

---

## 🚀 Usage

Run the main attack pipeline with:

```bash
python slam_attack/run_attack.py --config configs/attack_loam.yaml
```

You can modify the config file to select between LOAM, Cartographer, or other SLAM systems.

---

## 🧪 Evaluation

To evaluate the impact of the adversarial attack on SLAM accuracy:

```bash
python slam_attack/evaluate.py --results_dir results/loam_attack/
```

Metrics include:
- Trajectory error (ATE, RPE)
- Point cloud consistency
- SLAM failure rates

---

## 📚 Citation

If you use this code or refer to the ideas in your research, please cite:

```bibtex
@INPROCEEDINGS{10769168,
  author={Kumar, Prashant and Vattikonda, Dheeraj and Bhat, Kshitij and Dargan, Kunal and Kalra, Prem},
  booktitle={2024 IEEE International Conference on Image Processing Challenges and Workshops (ICIPCW)}, 
  title={SLACK: Attacking LiDAR-Based SLAM with Adversarial Point Injections}, 
  year={2024},
  pages={4082-4088},
  keywords={Learning systems;Laser radar;Simultaneous localization and mapping;Accuracy;Navigation;Conferences;Contrastive learning;Security;Image reconstruction;Autonomous vehicles},
  doi={10.1109/ICIPCW64161.2024.10769168}
}
```

---

## 📬 Contact

For questions, please reach out to the corresponding authors from the [paper](https://doi.org/10.48550/arXiv.2504.03089).

---

