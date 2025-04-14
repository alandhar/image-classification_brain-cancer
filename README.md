# Brain Cancer Image Classification using CNN

## Deskripsi Proyek

Proyek ini bertujuan untuk mengklasifikasikan citra MRI otak ke dalam tiga kategori utama tumor otak:
- **Glioma**
- **Meningioma**
- **Pituitary Tumor**

Model dikembangkan menggunakan arsitektur **Convolutional Neural Network (CNN)** berbasis TensorFlow, dengan target akurasi minimal 85% baik pada training maupun test set.

---

## Struktur Dataset

Dataset awal terdiri dari folder:
```arduino
Brain_Cancer/
├── glioma/
├── menin/
└── tumor/
```

Dataset dibagi secara otomatis menjadi:
- **Training Set**: 80%
- **Validation Set**: 10%
- **Test Set**: 10%

---

## Alur Proyek

### 1. Preprocessing
- Resize gambar ke 224x224 piksel
- Normalisasi piksel (0–255 menjadi 0–1)
- Label otomatis dari folder
- Pipeline: cache, shuffle, prefetch

### 2. Model
- `Sequential` model
- Layers: `Conv2D`, `MaxPooling2D`, `Flatten`, `Dense`, `Dropout`
- Aktivasi: `ReLU` dan `Softmax`

### 3. Training
- Optimizer: Adam
- Loss: Categorical Crossentropy
- Epoch: 20
- Target akurasi: ≥ 85%

### 4. Evaluasi
- `model.evaluate()` → accuracy & loss
- `classification_report()` → precision, recall, f1-score
- Plot: grafik akurasi & loss per epoch

### 5. Export Model
Model disimpan dalam 3 format:
```arduino
submission/
├── tfjs_model/
│ ├── group1-shard1of1.bin
│ └── model.json ├── tflite/ 
├── model.tflite
│ └── label.txt
├── saved_model/
│ ├── saved_model.pb
│ └── variables/
```

## Hasil Evaluasi

- Akurasi test set: 91%
- F1-score setiap kelas tersedia melalui scikit-learn
- Visualisasi: grafik akurasi & loss

---
