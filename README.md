# Computer Vision and Deep Learning

## Klasifikasi Mobil dan Motor pada Security Patrol Robot Menggunakan ResNet-50

Natasyahratu Zulharni | 4222401005 | RET503 Computer Vision and Deep Learning

## Deskripsi

Security Patrol Robot membutuhkan kemampuan untuk mengenali objek di lingkungan sekitar saat melakukan patroli. Salah satu objek yang perlu dibedakan adalah mobil dan motor.

Pada proyek ini digunakan metode transfer learning dengan model **ResNet-50 pretrained ImageNet** untuk melakukan klasifikasi gambar menjadi dua kelas, yaitu **car** dan **motorcycle**.

Tiga metode training dibandingkan untuk melihat perbedaan performanya:

- **Feature Extraction** — hanya fully connected layer (fc) yang dilatih, sedangkan layer lainnya dibekukan.
- **Partial Fine-Tuning** — layer4 dan fully connected layer (fc) yang dilatih.
- **Full Fine-Tuning** — seluruh layer pada ResNet-50 dilatih kembali.

## Dataset

Dataset terdiri dari **200 gambar** mobil dan motor yang dibagi menjadi:

| Dataset | Jumlah |
|---------|-------:|
| Train | 160 |
| Validation | 20 |
| Test | 20 |
| **Total** | **200** |

Kelas yang digunakan:

- `car`
- `motorcycle`

Dataset disimpan dalam `dataset_patrol.zip` dengan struktur:

```text
dataset_patrol/
├── Train/
│   ├── car/
│   └── motorcycle/
├── Val/
│   ├── car/
│   └── motorcycle/
└── Test/
    ├── car/
    └── motorcycle/
