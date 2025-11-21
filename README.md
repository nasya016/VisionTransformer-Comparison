# VisionTransformer-Comparison

Percobaan ini dibuat untuk memenuhi Tugas Eksplorasi mata kuliah Deep Learning. Fokus utama proyek ini adalah membandingkan dua model Vision Transformer modern dengan menggunakan dataset CIFAR-10. Metode yang digunakan adalah transfer learning dengan memanfaatkan model pre-train yang tersedia pada library `timm`.

Model yang diuji:
- **DeiT-Small Patch16/224**
- **Swin Transformer Tiny**

## Deskripsi Singkat
Proyek ini bertujuan untuk menganalisis:
- Performansi kedua model (training loss, validation loss, accuracy, confusion matrix)
- Perbedaan jumlah parameter
- Efisiensi proses training
- Kesesuaian model Vision Transformer untuk dataset CITAR-10

Seluruh proses dilakukan di Google Colab, dan dataset disimpan pada Google Drive agar bisa dipakai kembali tanpa mengunduh ulang.

##  Dataset
Dataset yang digunakan adalah **CIFAR-10**, yaitu kumpulan 60.000 gambar RGB berukuran 32×32 piksel dengan 10 kelas.  
Agar kompatibel dengan model Vision Transformer, semua gambar di-resize menjadi 224×224.


##  Instalasi dan Dependensi
Perintah berikut digunakan untuk memastikan semua dependensi tersedia:

pip install timm
pip install matplotlib
pip install scikit-learn

▶️ Cara Menjalankan
1. Mount Google Drive

from google.colab import drive
drive.mount('/content/drive')

2. Load Dataset CIFAR-10
Dataset otomatis di-download ke folder Drive:

/content/drive/My Drive/sem 7/cifar10

Transformasi yang digunakan:
- Resize 224×224
- Random horizontal flip (augmentasi)
- Normalisasi warna

3. Training Model
Notebook menyediakan proses:
- Inisialisasi model DeiT-Small dan Swin-Tiny
- Training menggunakan AdamW optimizer
- Validasi tiap epoch
- Scheduler Cosine Annealing

4. Visualisasi
Notebook menampilkan grafik:
- Training Loss vs Validation Loss
- Training Accuracy vs Validation Accuracy

5. Confusion Matrix
Disediakan untuk dua model, yaitu:
- DeiT Small
- Swin Tiny

6. Penyimpanan Model
Model otomatis disimpan ke:

My Drive/sem 7/saved_models/
