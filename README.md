# Klasifikasi Mobil dan Motor Menggunakan ResNet-50

Natasyahratu Zulharni | 4222401005 | RET503 Computer Vision and Deep Learning

https://colab.research.google.com/drive/1oWGbW20Y4GdG8AgjkQBGSWdqjFfJFWIw?usp=sharing

## Deskripsi

Security Patrol Robot membutuhkan kemampuan untuk mengenali objek di lingkungan sekitar saat melakukan patroli. Salah satu objek yang perlu dibedakan adalah mobil dan motor.

Pada proyek ini digunakan metode transfer learning menggunakan model **ResNet-50 pretrained ImageNet** untuk melakukan klasifikasi gambar menjadi dua kelas, yaitu **car** dan **motorcycle**.

Beberapa metode training dibandingkan untuk melihat perbedaan performanya, yaitu:

- **Feature Extraction** — seluruh layer ResNet-50 dibekukan dan hanya fully connected layer (fc) yang dilatih.
- **Partial Fine-Tuning** — sebagian layer ResNet-50, yaitu `layer4` dan fully connected layer (fc), yang dilatih.
- **Full Fine-Tuning** — seluruh layer ResNet-50 pretrained dilatih kembali.
- **Training from Scratch** — ResNet-50 dilatih dari awal tanpa menggunakan bobot pretrained ImageNet.

Perbandingan dilakukan berdasarkan akurasi training, akurasi validation, akurasi test, waktu training, dan epoch pertama ketika akurasi validation mencapai 90%.

## Dataset

Dataset terdiri dari **114 gambar** yang terbagi menjadi dua kelas:

- `car`
- `motorcycle`

Dataset tidak dipisahkan dalam folder Train, Validation, dan Test. Seluruh gambar disimpan dalam satu folder, kemudian dibagi secara acak menggunakan seed `42` agar hasil pembagian dapat direproduksi.

Pembagian dataset:

| Dataset | Jumlah |
|---------|-------:|
| Train | 92 |
| Validation | 11 |
| Test | 11 |
| **Total** | **114** |

Struktur dataset:

```text
dataset_patrol/
├── car/
└── motorcycle/
