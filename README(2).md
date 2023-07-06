
# UAS Pengloahan Citra

UAS Pengolahan citra kali ini saya membuat sebuat program untuk mendeteksi contour atau garis tepi pada sebuh objek 

# UAS Pengloahan Citra

Code tersebut adalah implementasi dari sebuah program untuk mendeteksi bentuk-bentuk dasar dalam sebuah gambar menggunakan library OpenCV dan scikit-image. Berikut adalah penjelasan mengenai setiap bagian dari code tersebut:


# Berikut adalah teori - teori yang saya gunakan dalama membuat program deteksi contour
Teori:

1.Fungsi detect_shapes(image_path): Fungsi ini digunakan untuk mendeteksi bentuk pada gambar yang diberikan. Proses deteksi dilakukan dengan mengikuti langkah-langkah berikut:

a. Membaca gambar menggunakan cv2.imread(image_path).

b. Mengubah gambar ke skala abu-abu dengan cv2.cvtColor(image, cv2.COLOR_BGR2GRAY).

c. Melakukan thresholding pada gambar menggunakan cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY).

d. Menggunakan metode cv2.findContours() untuk menemukan kontur pada gambar threshold.

e. Melakukan iterasi pada setiap kontur yang ditemukan dan memeriksa jumlah sudutnya:
- Jika jumlah sudut dekat dengan jumlah sudut pada lingkaran, maka bentuknya dianggap sebagai lingkaran.

- Jika kontur memiliki 3 sudut, maka bentuknya dianggap sebagai segitiga.
- Jika kontur memiliki 4 sudut, maka bentuknya bisa berupa persegi atau persegi panjang. Periksa apakah kontur konveks menggunakan cv2.isContourConvex().
- Jika kontur memiliki lebih dari 4 sudut, maka bentuknya dianggap sebagai poligon lainnya.
f. Mengembalikan daftar bentuk yang terdeteksi.

    Visualisasi hasil deteksi bentuk: Setelah fungsi detect_shapes(image_path) dipanggil, hasilnya akan disimpan dalam variabel detected_shapes. Kemudian, blok kode berikut digunakan untuk memvisualisasikan hasil deteksi:
    a. Membaca gambar menggunakan cv2.imread(image_path).
    b. Mengubah mode warna gambar dari BGR ke RGB menggunakan cv2.cvtColor(image, cv2.COLOR_BGR2RGB).
    c. Mengubah gambar ke skala abu-abu menggunakan cv2.cvtColor(image, cv2.COLOR_RGB2GRAY).
    d. Melakukan thresholding pada gambar abu-abu menggunakan cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY).
    e. Menggunakan metode measure.find_contours() dari modul skimage untuk menemukan kontur pada gambar threshold dengan nilai threshold 0.5.
    f. Membuat gambar dengan pola kontur menggunakan cv2.drawContours() dan menyimpannya dalam variabel image_with_contour_pattern.
    g. Membuat gambar dengan kontur saja menggunakan cv2.polylines() dan menyimpannya dalam variabel image_with_contour.
    h. Menampilkan tiga gambar: gambar asli, gambar dengan pola kontur, dan gambar asli dengan kontur menggunakan plt.subplots() dan imshow().

# Berikut adalah langkah-langkah penyelesaian kodingan tersebut:
1.Import library yang diperlukan: 

    - cv2: Digunakan untuk operasi pemrosesan citra.
    - numpy: Digunakan untuk operasi array dan manipulasi data numerik.
    - matplotlib.pyplot: Digunakan untuk menampilkan gambar.
    - skimage.measure: Digunakan untuk mengukur properti pada gambar.
2.Mendefinisikan fungsi detect_shapes(image_path) untuk mendeteksi bentuk pada gambar:

    - Menerima image_path sebagai parameter, yaitu path dari gambar yang akan diproses.
    - Membaca gambar menggunakan cv2.imread() dan menyimpannya dalam variabel image.
    - Mengonversi gambar ke skala abu-abu menggunakan cv2.cvtColor() dan menyimpannya dalam variabel gray.
    - Melakukan thresholding pada gambar menggunakan cv2.threshold() dengan metode cv2.THRESH_BINARY dan menyimpan hasilnya dalam variabel thresh.
    - Mencari kontur pada gambar menggunakan cv2.findContours() dengan mode cv2.RETR_EXTERNAL dan metode cv2.CHAIN_APPROX_SIMPLE, dan menyimpan kontur dan hierarki dalam variabel contours.
    - Menginisialisasi array shapes untuk menyimpan hasil bentuk yang dideteksi.
    - Melakukan loop melalui setiap kontur:
      - Menghitung jumlah titik sudut pada kontur menggunakan len(contour) dan menyimpannya dalam variabel num_corners.
    - Mengecek jumlah sudut untuk mendeteksi bentuk:
            Jika num_corners berada dalam rentang 8 hingga 23, bentuk dianggap sebagai lingkaran dan ditambahkan ke array shapes sebagai "Circle".
            Jika num_corners adalah 3, bentuk dianggap sebagai segitiga dan ditambahkan ke array shapes sebagai "Triangle".
            Jika num_corners adalah 4, bentuk bisa jadi persegi atau persegi panjang. Dilakukan pula pengecekan convexitas menggunakan cv2.isContourConvex(contour). Jika convex, bentuk dianggap sebagai persegi dan ditambahkan ke array shapes sebagai "Square". Jika tidak convex, bentuk dianggap sebagai persegi panjang dan ditambahkan ke array shapes sebagai "Rectangle".
            Jika num_corners lebih besar dari 4, bentuk dianggap sebagai poligon lainnya dan ditambahkan ke array shapes sebagai "Polygon".
    - Mengembalikan array shapes yang berisi hasil deteksi bentuk.
3.Mendefinisikan path gambar yang akan diproses dalam variabel image_path.

4.Memanggil fungsi detect_shapes(image_path) untuk mendeteksi bentuk gambar. Hasil deteksi disimpan dalam variabel detected_shapes.
5.Mencetak hasil deteksi bentuk menggunakan loop for dan print(shape).

6.Membaca gambar menggunakan cv2.imread() dan menyimpannya dalam variabel image. Kemudian, mengubah format warna gambar menjadi RGB menggunakan cv2.cvtColor().

7.Mengonversi gambar ke skala abu-abu menggunakan cv2.cvtColor() dan menyimpannya dalam variabel gray.

8.Melakukan thresholding padagambar menggunakan cv2.threshold() dengan metode cv2.THRESH_BINARY dan menyimpan hasilnya dalam variabel thresh.

9.Menggunakan skimage.measure.find_contours() untuk menemukan kontur pada gambar biner (thresh) dengan batas threshold 0.5. Hasil kontur disimpan dalam variabel contours.

10.Membuat gambar dengan pola kontur menggunakan np.ones_like() untuk membuat array dengan ukuran yang sama seperti image, kemudian mengisi seluruh array dengan warna putih (255). Setiap kontur diberi pola hitam dengan menggunakan cv2.drawContours().

11.Membuat gambar dengan kontur saja menggunakan np.copy() untuk membuat salinan image. Setiap kontur diberi warna biru dengan menggunakan cv2.polylines().

12.Menampilkan tiga gambar secara berdampingan menggunakan plt.subplots(). Gambar pertama adalah gambar asli, gambar kedua adalah gambar dengan pola kontur, dan gambar ketiga adalah gabungan antara gambar asli dan kontur. Setiap gambar ditampilkan dengan menggunakan imshow(). Setiap subplot diberi judul dengan menggunakan set_title(). Akhirnya, plt.show() digunakan untuk menampilkan gambar tersebut.

## Authors

- [@wahyusatrio18](https://github.com/wahyusatrio18)


## Acknowledgements

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)


## API Reference

#### Get all items

```http
  GET /api/items
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Get item

```http
  GET /api/items/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch |

#### add(num1, num2)

Takes two numbers and returns the sum.


## Appendix

Any additional information goes here


## Badges

Add badges from somewhere like: [shields.io](https://shields.io/)

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)

## Color Reference

| Color             | Hex                                                                |
| ----------------- | ------------------------------------------------------------------ |
| Example Color | ![#0a192f](https://via.placeholder.com/10/0a192f?text=+) #0a192f |
| Example Color | ![#f8f8f8](https://via.placeholder.com/10/f8f8f8?text=+) #f8f8f8 |
| Example Color | ![#00b48a](https://via.placeholder.com/10/00b48a?text=+) #00b48a |
| Example Color | ![#00d1a0](https://via.placeholder.com/10/00b48a?text=+) #00d1a0 |


## Contributing

Contributions are always welcome!

See `contributing.md` for ways to get started.

Please adhere to this project's `code of conduct`.


## Deployment

To deploy this project run

```bash
  npm run deploy
```


## Demo

Insert gif or link to demo


## Documentation

[Documentation](https://linktodocumentation)


## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

`API_KEY`

`ANOTHER_API_KEY`


## Features

- Light/dark mode toggle
- Live previews
- Fullscreen mode
- Cross platform


## FAQ

#### Question 1

Answer 1

#### Question 2

Answer 2


## Feedback

If you have any feedback, please reach out to us at fake@fake.com


## 🚀 About Me
I'm a full stack developer...


## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://katherineoelsner.com/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)


## Other Common Github Profile Sections
👩‍💻 I'm currently working on...

🧠 I'm currently learning...

👯‍♀️ I'm looking to collaborate on...

🤔 I'm looking for help with...

💬 Ask me about...

📫 How to reach me...

😄 Pronouns...

⚡️ Fun fact...


## Installation

Install my-project with npm

```bash
  npm install my-project
  cd my-project
```
    
## Lessons Learned

What did you learn while building this project? What challenges did you face and how did you overcome them?


## License

[MIT](https://choosealicense.com/licenses/mit/)


## Optimizations

What optimizations did you make in your code? E.g. refactors, performance improvements, accessibility


## 🛠 Skills
Javascript, HTML, CSS...


![Logo](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/th5xamgrr6se0x5ro4g6.png)


## Related

Here are some related projects

[Awesome README](https://github.com/matiassingers/awesome-readme)


## Used By

This project is used by the following companies:

- Company 1
- Company 2


## Usage/Examples

```javascript
import Component from 'my-project'

function App() {
  return <Component />
}
```


## Running Tests

To run tests, run the following command

```bash
  npm run test
```

