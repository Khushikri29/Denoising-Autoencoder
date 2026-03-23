# 🧹 Denoising Autoencoder with PyTorch

A simple yet effective **Denoising Autoencoder (DAE)** built using PyTorch, trained on the MNIST handwritten digits dataset. The model learns to reconstruct clean images from noisy inputs.

---

## 📌 What is a Denoising Autoencoder?

A **Denoising Autoencoder** is a type of neural network that is trained to remove noise from corrupted data. It works in two stages:

- **Encoder** — Compresses the noisy input into a smaller latent (bottleneck) representation
- **Decoder** — Reconstructs the clean original image from the latent representation

By learning to denoise, the model is forced to learn meaningful features of the data rather than just copying the input.

---

## 🧠 Model Architecture

```
Input (28×28 = 784)
      ↓
  Linear(784 → 128) + ReLU
      ↓
  Linear(128 → 64)        ← Bottleneck (Latent Space)
      ↓
  Linear(64 → 128) + ReLU
      ↓
  Linear(128 → 784) + Sigmoid
      ↓
Output (28×28 = 784)
```

---

## 📂 Dataset

- **MNIST** — 60,000 training images of handwritten digits (0–9), each 28×28 pixels in grayscale
- Downloaded automatically via `torchvision.datasets.MNIST`

---

## ⚙️ Training Details

| Parameter       | Value         |
|----------------|---------------|
| Optimizer       | Adam          |
| Learning Rate   | 0.001         |
| Loss Function   | MSE Loss      |
| Batch Size      | 128           |
| Epochs          | 3             |
| Noise Factor    | 0.5 (Gaussian)|

Gaussian noise is added to each image before passing it to the model. The model is trained to reconstruct the original clean image.

---

## 📊 Results

After 3 epochs, the model produces the following output on a sample image:

| Original | Noisy | Denoised |
|----------|-------|----------|
| Clean MNIST digit | Digit + Gaussian noise | Reconstructed clean digit |

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install torch torchvision matplotlib
```

### Run the Notebook

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/denoising-autoencoder.git
   cd denoising-autoencoder
   ```

2. Open the notebook:
   ```bash
   jupyter notebook Denoising_Autoencoder.ipynb
   ```

3. Run all cells — the MNIST dataset will be downloaded automatically.

> 💡 **Tip:** For faster training, run on Google Colab with a GPU (T4 recommended).

---

## 🛠️ Tech Stack

- **Python** 3.x
- **PyTorch**
- **Torchvision**
- **Matplotlib**

---

## 📁 Project Structure

```
denoising-autoencoder/
│
├── Denoising_Autoencoder.ipynb   # Main notebook
├── README.md                     # Project documentation
└── data/                         # MNIST data (auto-downloaded)
```

---

## 🤝 Contributing

Pull requests are welcome! Feel free to open an issue for bug reports or feature suggestions.
