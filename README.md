# 🩻 X-Ray Osteoarthritis Classification with Transfer Learning

Proyek ini membangun model **Transfer Learning** untuk klasifikasi **X-Ray Osteoarthritis (OA)** menggunakan **ResNet18**.  
Model difine-tune untuk 3 kelas: **Healthy, Moderate, Severe**.

---

## 🚀 Demo
Coba aplikasi interaktif langsung di Hugging Face Spaces:  
👉 [Demo Hugging Face](https://huggingface.co/spaces/Monti22/xray-oa)

🖼️



---

## 📂 File Lengkap
Seluruh file deployment (`app.py`, `requirements.txt`, dll.) tersedia di repo Hugging Face:  
👉 [Folder & File HF](https://huggingface.co/spaces/Monti22/xray-oa/tree/main)

---

## 📒 Notebook Training
Notebook utama berisi seluruh proses eksperimen:  
- Import Library  
- Konfigurasi & Seed  
- Persiapan Dataset  
- Arsitektur Model (Transfer Learning)  
- Training & Validasi  
- Evaluasi (Akurasi, F1, Confusion Matrix)  
- Simpan Model & Inference Demo  

📑 Lihat di folder [`notebooks/`](./notebooks/TransferLearning_Xray_RAPI.ipynb)

---

## 🏗️ Arsitektur Model
- **Backbone:** ResNet18 pretrained (ImageNet)  
- **Head:** diganti untuk 3 kelas OA  
- **Optimizer:** AdamW  
- **Loss:** CrossEntropy (dengan class weight imbalance)  
- **Augmentasi:** resize, crop, flip, normalization  



---

## 📊 Hasil Training
Selama training, akurasi train dan validasi meningkat stabil. Tidak ada tanda *overfitting* signifikan.  
- **Best Test Accuracy:** **93.06%**

🖼️ *[Sisipkan grafik training vs validation (accuracy & loss) di sini]*  

(images/grafik-cost.png)
(images/grafik-score.png)

---

## 📑 Evaluasi (Test Set, 1656 gambar)

**Classification Report**
| Class    | Precision | Recall | F1-score | Support |
|----------|-----------|--------|----------|---------|
| Healthy  | 0.9555    | 0.9790 | 0.9671   | 1382    |
| Moderate | 0.7906    | 0.6771 | 0.7295   | 223     |
| Severe   | 0.7551    | 0.7255 | 0.7400   | 51      |
| **Accuracy** |       |        | **0.9306** | 1656 |
| **Macro avg** | 0.8337 | 0.7939 | 0.8122 | 1656 |
| **Weighted avg** | 0.9271 | 0.9306 | 0.9281 | 1656 |

**Interpretasi:**  
- Kelas **Healthy** terprediksi sangat baik (F1 = 0.9671).  
- Kelas **Moderate** paling sulit, banyak salah ke Healthy/Severe.  
- Kelas **Severe** lumayan stabil walau jumlah data kecil.  

(images/confussion-matrix.png)

---

## 📸 Visualisasi Prediksi
Contoh hasil prediksi model di test set (warna hijau = benar, merah = salah).  

🖼️ *[Sisipkan gambar sample prediksi di sini]*  

(images/testing.png)

---

## ✨ Kesimpulan
- Transfer learning dengan ResNet18 efektif untuk klasifikasi X-Ray OA.  
- Akurasi tinggi (**93.06%**) dicapai pada test set.  
- Kelas **Moderate** masih jadi tantangan → butuh data lebih banyak atau augmentasi tambahan.  
- Hasil ini menunjukkan potensi penggunaan deep learning untuk membantu diagnosis OA secara otomatis.

---
