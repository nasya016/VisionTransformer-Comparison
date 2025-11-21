# Tugas Deep Learning – Vision Transformer Comparison

Nama: Nasya Aulia

NIM: 122140016

Mata Kuliah: Deep Learning

Topik: Perbandingan Model DeiT Small dan Swin Tiny pada Dataset CIFAR-10


## 1. Deskripsi Singkat

Proyek ini bertujuan membandingkan dua model Vision Transformer, yaitu DeiT Small dan Swin Tiny, dengan pendekatan transfer learning menggunakan dataset CIFAR-10. Proses dilakukan menggunakan Google Colab, dengan dataset disimpan pada Google Drive.

Analisis yang dilakukan meliputi:
1. Training dan validasi model
2. Plot grafik loss dan akurasi
3. Perhitungan confusion matrix
4. Classification report
5. Ringkasan performa tiap model
6. Penyimpanan model ke Google Drive

Hasil akhirnya menunjukkan perbedaan akurasi serta tingkat kesalahan masing-masing model dalam mengenali kelas CIFAR-10.

## 2. Dataset

Dataset yang digunakan adalah CIFAR-10, yang terdiri dari 60.000 gambar berwarna berukuran 32×32 dengan 10 kelas airplane, automobile, bird, cat, deer, dog, frog, horse, ship, dan truck. Karena Vision Transformer membutuhkan ukuran input 224×224, seluruh gambar dilakukan resize sebelum masuk ke model. Dataset kemudian disimpan ke Google Drive.

## 3. Model yang Digunakan
a. DeiT Small (deit_small_patch16_224)

    - Vision Transformer ringan
    - Efisien saat dilatih ulang
    - Cocok untuk transfer learning
    - Input wajib 224×224

b. Swin Tiny (swin_tiny_patch4_window7_224)

    - Model hierarkis berbasis windows
    - Lebih stabil pada gambar resolusi tinggi
    - Akurasi biasanya lebih baik dari ViT biasa
    - Input 224×224

Kedua model dimodifikasi untuk num_classes = 10 (sesuai CIFAR-10).

## 4. Tahapan Proyek
  1. Download dan Setup Dataset

     - CIFAR-10 diunduh langsung ke Google Drive
     - Melakukan transformasi (resize, normalize, augmentasi flip)
     - Batch size digunakan 16

  2. Training Model

      Setiap model melalui:

      - Training loss
      - Training accuracy
      - Validation loss
      - Validation accuracy
      - Scheduler Cosine Annealing LR

      Training dilakukan selama 5 epoch agar lebih cepat di Colab.

  3. Evaluasi Model

      Evaluasi mencakup:
      - Confusion matrix
      - Akurasi per kelas
      - Total benar dan salah
      - Classification report (precision, recall, f1-score)

  4. Visualisasi

      - Grafik training vs validation loss
      - Grafik training vs validation accuracy
      - Confusion matrix DeiT
      - Confusion matrix Swin

  5. Penyimpanan Model

      Model disimpan ke folder Google Drive dengan nama file `deit_small_cifar10.pth` dan `swin_tiny_cifar10.pth`

## 5. Hasil Utama
  1. Hasil Evaluasi DeiT Small
      Ringkasan Utama:
      - Total Data: 10.000
      - Total Benar: 9.596
      - Total Salah: 404
      - Akurasi: 95.96%
      - Precision rata-rata: 0.96
      - Recall rata-rata: 0.96
      - F1-score rata-rata: 0.96
      Akurasi per kelas sudah ditampilkan pada terminal

      Model DeiT menghasilkan akurasi tinggi hampir 96%. Performa terbaik terlihat pada kelas frog dan horse, sementara kelas yang paling sulit adalah dog. Variasi pose hewan kemungkinan mempengaruhi hasil prediksi.

  2. Hasil Evaluasi Swin Tiny
      Ringkasan Utama
      - Total Data: 10.000
      - Total Benar: 9.623
      - Total Salah: 377
      - Akurasi: 96.23%
      - Precision rata-rata: 0.96
      - Recall rata-rata: 0.96
      - F1-score rata-rata: 0.96
      Akurasi per kelas sudah ditampilkan pada terminal

      Swin Tiny sedikit lebih unggul dengan akurasi 96.23%. Model ini memiliki performa stabil pada kelas kendaraan seperti automobile dan truck, serta sangat baik pada kelas frog. Kesalahan paling banyak terdapat pada kelas cat dan dog.

## 6. Cara Menjalankan Kode
      - Buka file .py atau notebook di Google Colab
      - Mount Google Drive
      - Load dataset CIFAR-10 ke direktori Google Drive
      - Jalankan semua sel sampai selesai
      - Training akan menghasilkan:
        - Grafik loss dan akurasi
        - Confusion matrix
        - Classification report
      - Model (.pth) akan otomatis tersimpan ke Google Drive
