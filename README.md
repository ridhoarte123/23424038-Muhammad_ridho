
# Color Detection Application

Aplikasi Streamlit untuk deteksi warna pada gambar dengan berbagai color space dan metode thresholding.

## Instalasi

```bash
pip install -r requirements.txt
```

## Menjalankan Aplikasi

```bash
streamlit run app.py
```

## Fitur

### Color Space
- **RGB**: Standard RGB color space
- **R-G Color Space**: R-G difference color space
- **Normalized RGB**: Normalized RGB (r=R/(R+G+B))
- **HSV**: Hue-Saturation-Value
- **YCrCb**: YCrCb color space
- **TSL**: Tint-Saturation-Luminance

### Metode Thresholding

1. **Static Threshold**
   - Tentukan range min-max untuk setiap channel
   - Cocok untuk warna yang sudah diketahui range-nya

2. **Dynamic Threshold**
   - Threshold otomatis: mean ± k * standard deviation
   - Parameter: K Factor (0.0 - 5.0)
   - Cocok untuk adaptasi otomatis

3. **Distance Threshold**
   - Deteksi berdasarkan jarak Euclidean dari warna target
   - Parameter: Target color (R, G, B) dan Max Distance
   - Cocok untuk deteksi warna spesifik

## Cara Penggunaan

1. Upload gambar (JPG/PNG)
2. Pilih format warna yang diinginkan
3. Pilih metode threshold
4. Atur parameter sesuai metode:
   - Static: Set min-max untuk setiap channel
   - Dynamic: Set K Factor
   - Distance: Pilih target color dan max distance
5. Lihat hasil di 4 panel:
   - Gambar Asli
   - Gambar Format Terpilih
   - Mask Hasil Deteksi
   - Gambar dengan Mask Applied
6. Download mask sebagai PNG (opsional)

## Struktur File

```
color_detection_app/
├── app.py                 # Main application
├── color_converters.py    # Konversi color space
├── threshold_methods.py  # Metode thresholding
├── utils.py              # Utility functions
├── requirements.txt      # Dependencies
└── README.md            # Dokumentasi
```

## Dependencies

- streamlit
- numpy
- opencv-python
- Pillow

## Tips

- **Static Threshold**: Gunakan untuk warna yang konsisten, atur range secara manual
- **Dynamic Threshold**: Gunakan untuk gambar dengan variasi pencahayaan, K Factor 1.0-2.0 biasanya optimal
- **Distance Threshold**: Gunakan untuk deteksi warna spesifik, mulai dengan max distance 50-100


cara menjalankan
cd C:\Users\angga\color_detection_app
pip install -r requirements.txt
streamlit run app.py
