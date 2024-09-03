Deteksi Bentuk pada Gambar Menggunakan OpenCV dan Scikit-Image

Proyek ini mendemonstrasikan sebuah metode untuk mendeteksi dan mengidentifikasi bentuk (seperti lingkaran, segitiga, kotak, persegi panjang, dan poligon lainnya) di dalam gambar menggunakan pustaka OpenCV dan Scikit-Image dari Python. Notebook ini memproses gambar input, mengidentifikasi kontur, dan mengklasifikasikan kontur ini berdasarkan jumlah sudut yang terdeteksi.
Gambaran Umum Proyek

Tujuan utama dari proyek ini adalah untuk menganalisis sebuah gambar, mendeteksi berbagai bentuk di dalamnya, dan memvisualisasikan bentuk-bentuk ini dengan melapisi kontur pada gambar asli. Teknik ini berguna dalam aplikasi visi komputer di mana mengenali dan mengklasifikasikan bentuk dalam gambar sangat penting.
Fitur

    Deteksi Bentuk: Proyek ini menyertakan fungsi detect_shapes () yang membaca gambar input, mengubahnya menjadi skala abu-abu, menerapkan thresholding, dan mengidentifikasi kontur. Berdasarkan jumlah sudut, fungsi ini mengklasifikasikan bentuk yang terdeteksi sebagai lingkaran, segitiga, persegi, persegi panjang, atau poligon lain.
    Visualisasi Kontur: Kontur yang terdeteksi divisualisasikan pada gambar asli, sehingga memudahkan verifikasi proses pendeteksian bentuk.
    Beberapa Output Gambar: Notebook ini menghasilkan beberapa output visual, termasuk:
        Gambar asli.
        Gambar pola kontur yang hanya menunjukkan kontur yang terdeteksi.
        Gambar asli yang dilapis dengan kontur yang terdeteksi.

Ketergantungan

Untuk menjalankan proyek ini, Anda memerlukan pustaka Python berikut ini:

    opencv-python
    numpy
    matplotlib
    scikit-image

Anda dapat menginstal dependensi ini menggunakan pip:

bash

pip install opencv-python numpy matplotlib scikit-image

Cara Menggunakan

    Kloning repositori ke mesin lokal Anda.
    Tempatkan citra masukan Anda pada direktori proyek.
    Perbarui variabel image_path pada buku catatan dengan nama berkas citra Anda.
    Jalankan Jupyter Notebook untuk menjalankan deteksi bentuk dan melihat hasilnya.

Contoh:

python

# Jalur ke gambar Anda
image_path = 'your_image.jpeg'

# Mendeteksi bentuk dalam gambar
detected_shapes = detect_shapes(image_path)

# Melihat hasilnya
for shape in detected_shapes:
    print(shape)

Contoh Keluaran

Notebook akan menampilkan yang berikut ini:

    Gambar asli.
    Gambar skala abu-abu dengan kontur yang terdeteksi.
    Gambar asli dengan kontur yang ditumpangkan untuk menyoroti bentuk yang terdeteksi.

Kesimpulan

Proyek ini menyediakan pendekatan yang mudah namun efektif untuk deteksi bentuk dalam gambar. Dengan memanfaatkan kekuatan OpenCV dan Scikit-Image, memungkinkan untuk mengklasifikasikan dan memvisualisasikan berbagai bentuk yang ada dalam sebuah gambar, yang dapat sangat berguna dalam bidang-bidang seperti visi komputer, analisis gambar, dan inspeksi otomatis.
Pekerjaan di Masa Depan

Peningkatan potensial meliputi:

    Memperluas kemampuan deteksi bentuk untuk menyertakan bentuk yang lebih kompleks.
    Meningkatkan akurasi dengan mengintegrasikan teknik pembelajaran mesin untuk klasifikasi bentuk.
    Membuat GUI untuk interaksi yang lebih mudah dengan alat pendeteksi bentuk.


