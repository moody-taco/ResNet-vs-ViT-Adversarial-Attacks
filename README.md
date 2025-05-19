# 🛡️ Adversarial Robustness: ResNet18 vs ViT-tiny

This project benchmarks the adversarial robustness of two popular architectures — **ResNet18** (CNN) and **ViT-tiny** (Vision Transformer) — on the CIFAR-10 dataset. The models are tested under white-box adversarial attacks to understand how different inductive biases influence robustness.

---

## 📌 Project Highlights

- ✅ ResNet18 trained from scratch
- ✅ ViT-tiny (DeiT) pretrained on ImageNet
- ✅ Dataset: CIFAR-10
- ✅ Adversarial Attacks: FGSM, BIM, PGD
- ✅ Evaluated across `ε ∈ {0.00, 0.01, 0.03, 0.05}`

---

## 🧪 How to Run

Clone the repo and install dependencies:

```bash
git clone https://github.com/YOUR_USERNAME/adv_robustness_resnet_vit.git
cd adv_robustness_resnet_vit
pip install -r requirements.txt
```

Run the Jupyter Notebook:
```bash
jupyter notebook notebook.ipynb
```

---

## 📦 Dependencies

To run this project, you'll need the following Python libraries:

- `torch` – Deep learning framework (PyTorch)
- `torchvision` – Datasets and model zoo
- `timm` – Access to pretrained Vision Transformers
- `matplotlib` – Visualization of accuracy curves
- `tqdm` – Progress bars during training and evaluation

Install them with:

```bash
pip install -r requirements.txt
```

---

## 📊 Results Summary

| Epsilon | Model     | FGSM Acc | BIM Acc | PGD Acc |
|---------|-----------|----------|---------|---------|
| 0.00    | ResNet18  | 73.39%   | 73.39%  | 73.39%  |
| 0.00    | ViT-tiny  | 77.88%   | 77.88%  | 77.88%  |
| 0.01    | ResNet18  | 29.53%   | 0.03%   | 22.64%  |
| 0.01    | ViT-tiny  | 7.62%    | 0.00%   | 2.03%   |
| 0.03    | ResNet18  | 4.36%    | 0.03%   | 0.59%   |
| 0.03    | ViT-tiny  | 0.83%    | 0.00%   | 0.00%   |
| 0.05    | ResNet18  | 1.59%    | 0.03%   | 0.03%   |
| 0.05    | ViT-tiny  | 1.85%    | 0.00%   | 0.00%   |

📈 See the full plot in [`results/accuracy_plot.png`](results/accuracy_plot.png)

---

## 🧠 Insights

- **ViT-tiny achieves higher clean accuracy**, but suffers significantly under adversarial attacks.
- **ResNet18 shows better adversarial robustness**, especially under single-step attacks like FGSM.
- ViTs, despite their power, require extra care (e.g., adversarial training) to handle perturbed inputs.

---

## 📜 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).  