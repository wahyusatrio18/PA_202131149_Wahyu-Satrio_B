dentification of shapes in images using OpenCV and Scikit-Image

Proyek ini memperlihatkan suatu teknik untuk menemukan dan mengklasifikasi objek-objek geometris seperti lingkaran, segitiga, kotak, persegi panjang, dan bentuk poligon lainnya dari gambar melalui pustaka OpenCV dan Scikit-Image yang telah diberikan dalam bahasa pemrograman Python. Notebook ini berfungsi untuk membaca gambar input, mendeteksi kontur yang ada, dan mengklasifikasi kontur tersebut berdasarkan jumlah sudut yang ditemukan.
Gambaran Umum Proyek

Tujuan khusus dari proyek ini adalah memproses gambar, mendeteksi berbagai bentuk di dalamnya, dan menampilkan bentuk-bentuk tersebut dengan melapisi kontur pada gambar. Teknik ini sangat berguna dalam aplikasi penglihatan komputer di mana deteksi dan klasifikasi bentuk dalam gambar sangat penting.
Fitur

Deteksi Bentuk: Pustaka ini berisi fungsi detect_shapes() yang menganalisis citra input, merubahnya menjadi skala abu-abu, kemudian merubah threshold citra, dan akhirnya menemukan kontur. Berdasarkan jumlah sudut dari kontur, fungsi tersebut mengenali bentuk yang terdeteksi sebagai lingkaran, segitiga, persegi, persegi panjang, atau poligon lainnya.
Kontur terdeteksi diwajah merepresentasikan kontur pada gambar asli, sehingga memperjelas dan mencocokkannya sebagai hasil deteksi bentuk.
Beberapa Hasil Visual: Notebook ini memiliki beberapa output gambar, yaitu:
Crédit image.
Display a contour map that shows only the recorded contours.
Gambar asli yang telah dilapisi dengan kontur yang teridentifikasi.

Addiction

Untuk menjalankan proyek ini, kita membutuhkan beberapa pustaka Python:

PyPI
NUMPY
Matplotlib
scikit-picture

Anda dapat menginstal dependensi ini menggunakan pip.

bash

pip install opencv-python numpy matplotlib scikit-image

Arti Penggunaan

Lakukan kloning repositori ke komputer lokal Anda.
Letakkan gambar masukan Anda di dalam direktori proyek.
Ganti variabel image_path dalam buku catatan dengan nama berkas gambar Anda.
Jalankan Jupyter Notebook untuk menjalankan deteksi bentuk dan melihat hasil.

Ilustrasi:

py

# Rute menuju gambar Anda
image_path = 'your_image.jpeg'

# Deteksi Bentuk pada Gambar
shape_found = detect_shapes(image_path)

# Mengamati Akibatnya

for shape in detected_shapes:

revisar(forma)

Illustrative Outcome

Notebook will display the following information:

Lámina original.

Tampilkan citra skala abu-abu dengan tepi yang terdeteksi.

Menampilkan gambar aslinya dengan garis kontur di atasnya untuk memperlihatkan bentuk yang dikenali. Conclusion Proyek ini memberikan metode sederhana dan efisien dalam pengenalan bentuk dalam citra. Proyek ini mampu mengklasifikasikan serta menampilkan sejumlah bentuk dalam satu citra dengan bantuan kemampuan yang diberikan oleh OpenCV dan Scikit-Image. Ini pada gilirannya, akan mempunyai banyak aplikasi dalam bidang seperti visi komputer, analisis citra, dan inspeksi otomatis. Kerja di Masa Depan. Peluang Berisi Meluas Membangun kepekaan terhadap bentuk sehingga dapat menangkap bentuk-bentuk yang lebih reflektif. Peningkatan dapat dicapai melalui penggabungan teknik pembelajaran mesin dalam klasifikasi bentuk. Buat antarmuka grafis pengguna untuk secara lebih interaktif bekerja dengan tools sensor bentuk.
