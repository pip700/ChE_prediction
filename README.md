

# 🧠 **ChEpred**: Cholinesterase Inhibitor Prediction Using AttentiveFP

**ChEpred** is a Graph Neural Network (GNN)-based tool designed to predict the inhibitory activity of chemical compounds against **acetylcholinesterase (AChE)** and **butyrylcholinesterase (BuChE)**. Using molecular structures provided in **SMILES format**, the tool performs binary classification (Inhibitor vs. Non-inhibitor) as well as multi-classification for potency of inhibitors and provides **atom-level and bond-level interpretability** through importance graphs and visualizations.

**ChEpred** is distributed as a user-friendly **Docker container**, making it easy to use without any setup. Whether you're a researcher, developer, or student, the web interface and containerized environment ensure accessible and reproducible predictions.

---

## 📚 Table of Contents

* [Features](#-features)
* [Installation](#-installation)
* [Usage](#-usage)
* [Output Results](#-output-results)
* [Troubleshooting](#-troubleshooting)
* [Contributors](#-contributors)
* [Citation](#-citation)

---

## 🚀 Features

* ✅ Predicts whether a molecule is an **AChE or BuChE Inhibitor**
* ⚙️ Provided as a **Docker container** for portability
* 🧠 Supports both **CPU** and **GPU** inference
* 🔍 Provides **atom-level and bond-level interpretability**
* 💾 Saves results and visualizations in **timestamped directories**
* 🖼️ Outputs visual plots for easier interpretation of predictions

---

## 📦 Installation

### 1. Install Docker

#### For Windows (PowerShell)

```powershell
wsl --install
```

Then inside WSL:

```bash
sudo apt-get update
sudo apt-get install docker.io -y
```

#### For Linux

```bash
sudo apt-get update
sudo apt-get install docker.io -y
```

### 📦 Dependencies

All dependencies are pre-installed in the Docker image. You only need Docker installed on your system.

---

## 🧪 Usage

### 2. Run the Docker Container

Navigate to your working directory and launch the container:

#### CPU-only version:

```bash
sudo docker run -it --rm -v ${PWD}:/workspace ghcr.io/pip700/chepred:cpu
```

#### GPU-enabled version:

```bash
sudo docker run --gpus all -it --rm -v ${PWD}:/workspace ghcr.io/pip700/chepred:gpu
```

### 3. Input File Selection

Once inside the Docker container, choose input format:

* Enter `1` to input a **SMILES** string directly:

  ```scores
  CC(C)OC(=O)N1CCC(CC1)CN2C=NC3=CC=CC=C3C2=O
  ```

* Enter `2` to upload a **CSV** file containing SMILES:

  ```
  inhibitors.csv
  ```

> The CSV file **must contain a column** with valid SMILES strings.

---

## 📤 Output Results

All output files are saved in a **timestamped folder** in your working directory.

### Outputs Include:

* `Prediction.csv` — Predicted class [Is Active (True): Inhibitor / Is Active (False): Non-inhibitor) and probabilities
* `Atom & Bond-level.png` — Visualization of atom and bond significance
* `Feature importance.png` — Visualization of histogram of node features

---

## 🛠️ Troubleshooting

| Issue                 | Solution                                                               |
| --------------------- | ---------------------------------------------------------------------- |
| **Docker not found**  | Ensure Docker is installed and in your system PATH                     |
| **Permission denied** | Run Docker with `sudo`                                                 |
| [**GPU not detected**](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)  | Make sure NVIDIA drivers and Docker GPU support are properly installed |

---

## 👥 Contributors

* [pip700](https://github.com/pip700)

---

## 📑 Citation

If you use **ChEpred** in your research or publication, please cite:

```bibtex
@article{,
  author    = {Dhairiya Agarwal, Anju Sharma, and Prabha Garg},
  title     = {ChEpred: A Graph Neural Network Approach for Predicting AChE and BuChE Inhibitors},
  journal   = {...},
  volume    = {},
  year      = {2025},
  url       = {https://pubmed.ncbi.nlm.nih.gov/...},
  doi       = {...},
  issn      = {}
}
```

