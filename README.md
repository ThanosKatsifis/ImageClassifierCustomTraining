<img width="1536" height="1024" alt="Modern tech banner" src="https://github.com/user-attachments/assets/bb842fcc-bcbc-4462-b45e-5a3585b782cf" />

# 🧠 Custom Image Classifier  
*A modern Tkinter desktop app for training your own image‑classification model using PyTorch + ResNet‑18.*

---

## 📌 Overview

This project is a fully interactive desktop application that lets anyone train a custom image classifier **without writing machine‑learning code**.  
It uses a **pretrained ResNet‑18 backbone** as a frozen feature extractor and trains a lightweight linear head on top — making training fast, efficient, and CPU‑friendly.

The UI is built with **Tkinter + ttk**, styled with a modern dark theme inspired by macOS Sonoma.

---

## ✨ Features

### 🔧 Custom Training
- Add and remove classes dynamically  
- Import training images per class  
- Automatic dataset organization  
- Data augmentation (crop, flip, color jitter)

### 🧠 Model Architecture
- ResNet‑18 pretrained on ImageNet  
- Backbone frozen for speed  
- Custom linear classification head  
- Softmax prediction with confidence score

### 🖥️ Modern UI
- Dark, card‑based layout  
- Live image preview  
- Real‑time training logs  
- Progress bar + ETA  
- Activity log with auto‑scroll  
- Non‑blocking threads for training & inference
- <img width="1082" height="832" alt="Στιγμιότυπο οθόνης 2026-05-06 183618" src="https://github.com/user-attachments/assets/9bc60a2d-6100-4c28-93d0-5b65bca86d2a" />


### 📂 Classification Modes
- **Single image classification**  
- **Batch folder classification** with ETA  
- Automatic saving/loading of:
  - `custom_head.pth` (model weights)  
  - `custom_classes.json` (class index mapping)

---

## 🏗️ How It Works

### 1. Add Classes  
Each class gets its own folder inside `custom_classes/`.  
You select a folder of images, and the app copies them automatically.

### 2. Train  
The app:
- Extracts features using ResNet‑18  
- Trains a linear classifier for `EPOCHS`  
- Logs progress and loss  
- Saves the model + metadata  

### 3. Classify  
You can classify:
- A single image  
- An entire folder  
Results appear in the log and UI.

---

## 📦 Installation

### 1. Clone the repo
```bash
git clone https://github.com/yourusername/custom-image-classifier.git
cd custom-image-classifier
```

### 2. Install dependencies
```bash
pip install torch torchvision pillow
```

### 3. Run the app
```bash
python main.py
```

---

## 📁 Project Structure

```
├── custom_classes/        # Auto-created class folders
├── images/                # Default folder for batch classification
├── custom_head.pth        # Saved classifier head (auto-generated)
├── custom_classes.json    # Saved class index mapping
├── main.py                # Full application code
└── README.md
```

---

## 🧩 Code Highlights

### ✔️ Preprocessing  
Uses torchvision transforms with normalization and augmentation.

### ✔️ Model  
ResNet‑18 backbone with frozen weights:
```python
self.backbone = models.resnet18(weights=models.ResNet18_Weights.DEFAULT)
self.backbone.fc = nn.Identity()
```

### ✔️ Training Loop  
Mini‑batch training with Adam optimizer and cross‑entropy loss.

### ✔️ UI  
Modern ttk styling with:
- Cards  
- Muted labels  
- Accent buttons  
- Progress bars  

---

## 🛠️ Requirements

- Python 3.8+
- PyTorch
- Torchvision
- Pillow
- Tkinter (included with most Python installations)

---

## 🧪 Example Workflow

1. Launch the app  
2. Add two or more classes  
3. Import training images  
4. Click **Train**  
5. Browse or drag a single image → classify  
6. Or select a folder → classify all images  

---

## 📝 Roadmap

- [ ] Add GPU support (optional)  
- [ ] Add confusion matrix after training  
- [ ] Add exportable training metrics  
- [ ] Add drag‑and‑drop support  
- [ ] Add light mode  

---

## 🤝 Contributing

Pull requests are welcome.  
If you have ideas for UI improvements, new features, or model upgrades, feel free to open an issue.

---

## 📜 License

This project is released under the **MIT License**.

---

## 🙋 About the Developer

Built by **Thanos Katsifis** — passionate about clean UI, practical machine learning tools, and making AI accessible to everyone.

---

