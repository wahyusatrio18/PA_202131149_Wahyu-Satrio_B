
# UAS Pengloahan Citra

UAS Pengolahan citra kali ini saya membuat sebuat program untuk mendeteksi contour atau garis tepi pada sebuh objek 

# UAS Pengloahan Citra

Code tersebut adalah implementasi dari sebuah program untuk mendeteksi bentuk-bentuk dasar dalam sebuah gambar menggunakan library OpenCV dan scikit-image. Berikut adalah penjelasan mengenai setiap bagian dari code tersebut:

# Import library:

    - cv2: Library OpenCV untuk pemrosesan gambar.
    - numpy as np: Library NumPy untuk operasi matriks dan array.
    - matplotlib.pyplot as plt: Library Matplotlib untuk visualisasi   gambar.
    - measure dari skimage: Modul dari library scikit-image untuk mengukur sifat-sifat geometris dalam gambar.

# Fungsi detect_shapes(image_path):

- Menerima path gambar sebagai argumen.

- Membaca gambar menggunakan cv2.imread.

- Mengonversi gambar ke skala abu-abu menggunakan cv2.cvtColor.

- Melakukan thresholding untuk memperoleh gambar biner menggunakan cv2.threshold.

- Menggunakan cv2.findContours untuk menemukan kontur dalam gambar biner.

- Membuat array shapes untuk menyimpan hasil bentuk yang terdeteksi.

- Melakukan iterasi melalui setiap kontur:
    - Menghitung jumlah titik sudut pada kontur menggunakan len (contour).

    - Memeriksa apakah kontur dapat dianggap sebagai lingkaran berdasarkan jumlah titik sudut.

    - Jika jumlah titik sudut dekat dengan jumlah titik sudut pada lingkaran, maka bentuknya adalah "Circle".

    - Jika kontur memiliki 3 sisi, maka bentuknya adalah "Triangle".
    - Jika kontur memiliki 4 sisi, maka bentuknya bisa jadi "Square" (persegi) atau "Rectangle" (persegi panjang) tergantung pada apakah kontur bersifat konveks menggunakan cv2.isContourConvex.
    - Jika kontur memiliki lebih dari 4 sisi, maka bentuknya adalah "Polygon".
    - Mengembalikan array shapes yang berisi hasil bentuk-bentuk yang terdeteksi.

# Mendefinisikan path gambar
(image_path) yang akan diproses.

# Memanggil fungsi 
detect_shapes(image_path) untuk mendapatkan hasil deteksi bentuk gambar.

# Mencetak hasil deteksi bentuk 
menggunakan perulangan for.

# Membaca gambar menggunakan 
cv2.imread dan mengubah mode warna menjadi RGB menggunakan cv2.cvtColor.

# Mengonversi gambar ke skala abu-abu 
menggunakan cv2.cvtColor.

# Melakukan thresholding 
pada gambar abu-abu untuk memperoleh gambar biner menggunakan cv2.threshold.

# Menggunakan measure.find_contours 
dari scikit-image untuk menemukan kontur dalam gambar biner.

# Membuat gambar dengan pola kontur 
menggunakan np.ones_like dan cv2.drawContours untuk mengisi pola kontur dengan warna hitam.

# Membuat gambar dengan kontur saja 
menggunakan np.copy dan cv2.polylines untuk menggambar garis kontur dengan warna biru.

# Fungsi untuk mendeteksi contour
```python
for contour in contours:
        # Hitung jumlah titik sudut pada kontur
        num_corners = len(contour)
        
        if num_corners >= 8 and num_corners <= 23:
            shapes.append("Circle")

        elif num_corners == 3:
            shapes.append("Triangle")
        
        elif num_corners == 4:
            shapes.append("Square" if cv2.isContourConvex(contour) else "Rectangle")
        
        else:
            shapes.append("Polygon")
    
    return shapes

    # Buat gambar dengan pola kontur
    image_with_contour_pattern = np.ones_like(image) * 255
for contour in contours:
    contour = np.around(contour).astype(np.int32)
    cv2.drawContours(image_with_contour_pattern, [contour], -1, (0, 0, 0), thickness=cv2.FILLED)

     # Buat gambar dengan kontur saja
image_with_contour = np.copy(image)
for contour in contours:
    contour = np.around(contour).astype(np.int32)
    cv2.polylines(image_with_contour, [contour], True, (255, 0, 0), thickness=2)

```
# Menampilkan tiga gambar dalam satu figure menggunakan plt.subplots:

    - Gambar asli.
    - Gambar dengan pola kontur.
    - Gambar asli dengan kontur ditampilkan menggunakan transparansi.
    - Menampilkan figure dengan menggunakan plt.show().


## Authors

- [@wahyusatrio18](https://github.com/wahyusatrio18)

