Nama	: Ahmad Atalaraya.S
NIM	    : 202131033
Kelas	: Pengolahan Citra - A

Pada Uas kali ini saya disuruh membuat Deteksi Marka Jalan.

## Divinisi Deteksi Marka Jalan
Pengolahan citra dalam konteks deteksi marka jalan merujuk pada serangkaian teknik dan metode yang digunakan untuk memproses citra digital yang berisi informasi tentang marka jalan. Tujuan pengolahan citra dalam deteksi marka jalan adalah untuk mengidentifikasi, memisahkan, dan menganalisis marka jalan dalam citra tersebut.

Proses pengolahan citra dalam deteksi marka jalan melibatkan langkah-langkah berikut:
1.	Pra-Pemrosesan: Langkah ini melibatkan persiapan citra sebelum dilakukan deteksi marka jalan. Pra-pemrosesan dapat mencakup operasi seperti peningkatan kontras, pengurangan noise, penajaman citra, dan normalisasi intensitas. Tujuannya adalah untuk meningkatkan kualitas citra sehingga marka jalan dapat terlihat lebih jelas dan tajam.
2.	Segmentasi: Langkah ini bertujuan untuk memisahkan marka jalan dari latar belakang citra. Berbagai metode segmentasi dapat digunakan, termasuk thresholding, pemrosesan morfologi, segmentasi berbasis tepi, atau penggunaan model statistik seperti model warna atau model tekstur. Segmentasi dilakukan dengan mengidentifikasi wilayah dalam citra yang berpotensi mengandung marka jalan.
3.	Deteksi Marka Jalan: Setelah segmentasi, langkah selanjutnya adalah mendeteksi marka jalan dalam wilayah yang teridentifikasi. Metode deteksi marka jalan dapat melibatkan algoritma berbasis fitur, seperti Transformasi Hough, Transformasi Radon, filter Gabor, atau deteksi tepi menggunakan operator Sobel atau Canny. Deteksi marka jalan dapat berdasarkan bentuk, tekstur, warna, atau kombinasi fitur lainnya.
4.	Ekstraksi Fitur: Setelah deteksi marka jalan, fitur-fitur relevan dapat diekstraksi untuk mendeskripsikan marka jalan yang terdeteksi. Fitur-fitur ini bisa meliputi panjang, lebar, orientasi, jarak antara marka jalan, atau fitur-fitur tekstur seperti histogram warna atau pola tekstur. Ekstraksi fitur penting untuk membedakan marka jalan yang berbeda dan mengklasifikasikannya dengan benar.
5.	Klasifikasi: Langkah terakhir dalam pengolahan citra deteksi marka jalan adalah klasifikasi marka jalan berdasarkan fitur-fitur yang diekstraksi sebelumnya. Metode klasifikasi yang umum digunakan termasuk klasifikasi berbasis aturan, seperti penggunaan threshold atau aturan heuristik, atau klasifikasi berbasis model, seperti penggunaan jaringan saraf tiruan, Support Vector Machine (SVM), atau algoritma pembelajaran mesin lainnya.

Pengolahan citra dalam deteksi marka jalan memungkinkan pengolahan dan analisis yang lebih lanjut terhadap marka jalan yang terdeteksi, seperti pelacakan, perubahan status, atau pengenalan pola marka jalan. Tujuan utamanya adalah untuk menghasilkan informasi yang akurat dan relevan tentang marka jalan dalam citra

Kelebihan Deteksi Marka Jalan dengan Pengolahan Citra:
-	Non-invasif: Deteksi marka jalan menggunakan pengolahan citra tidak memerlukan intervensi fisik pada infrastruktur jalan. Ini memungkinkan deteksi yang tidak mengganggu lalu lintas dan tidak memerlukan perubahan pada jalan yang ada.
-	Automatisasi: Metode deteksi marka jalan dengan pengolahan citra dapat sepenuhnya diotomatisasi, memungkinkan untuk deteksi secara real-time tanpa keterlibatan manusia.
-	Akurasi: Dengan menggunakan algoritma dan teknik pengolahan citra yang tepat, deteksi marka jalan dapat menghasilkan hasil yang akurat dan konsisten.
-	Efisiensi waktu: Deteksi marka jalan dengan pengolahan citra dapat dilakukan dengan cepat, memungkinkan evaluasi dan pemantauan yang efisien pada jalan raya.
-	Scalability: Metode deteksi marka jalan dengan pengolahan citra dapat diterapkan pada berbagai jenis jalan dan lingkungan lalu lintas.

Kekurangan Deteksi Marka Jalan dengan Pengolahan Citra:
-	Sensitivitas terhadap kondisi lingkungan: Deteksi marka jalan menggunakan pengolahan citra dapat dipengaruhi oleh kondisi lingkungan seperti pencahayaan, kondisi cuaca, dan gangguan visual lainnya. Variabilitas ini dapat mempengaruhi keakuratan deteksi.
-	Pengolahan komputasional yang intensif: Metode deteksi marka jalan dengan pengolahan citra membutuhkan pengolahan komputasional yang intensif. Ini dapat memakan waktu dan memerlukan sumber daya komputasi yang memadai.
-	Kelemahan pada marka jalan yang samar atau rusak: Deteksi marka jalan menggunakan pengolahan citra dapat mengalami kesulitan dalam mendeteksi marka jalan yang samar atau rusak, yang dapat menghasilkan hasil deteksi yang tidak akurat.
-	Ketergantungan pada kondisi penglihatan mesin: Deteksi marka jalan menggunakan pengolahan citra bergantung pada kemampuan mesin untuk memahami dan menginterpretasi citra. Hal ini membuatnya rentan terhadap kesalahan dan interpretasi yang salah dalam kondisi yang kompleks atau tidak biasa.

Menjelaskan tahapan cara menyelesaikan projek secara rinci
1.	Program di atas menggunakan library OpenCV (cv2) untuk melakukan deteksi marka jalan pada sebuah gambar jalan. Berikut adalah penjelasan dari setiap langkah dalam program tersebut:
2.	Membaca gambar jalan: Program membaca gambar jalan yang disimpan dalam file 'marka_jalan.jpg' menggunakan fungsi cv2.imread() dan menyimpannya dalam variabel image.
3.	Mengubah gambar menjadi skala abu-abu: Gambar berwarna pada image diubah menjadi gambar skala abu-abu menggunakan fungsi cv2.cvtColor() dengan parameter cv2.COLOR_BGR2GRAY. Hasilnya disimpan dalam variabel gray.
4.	Menerapkan filter Gaussian: Filter Gaussian dengan ukuran kernel (5, 5) digunakan untuk mengurangi noise pada gambar skala abu-abu (gray). Fungsi cv2.GaussianBlur() digunakan untuk menerapkan filter tersebut. Hasilnya disimpan dalam variabel blur.
5.	Menggunakan transformasi Canny untuk mendeteksi tepi: Fungsi cv2.Canny() digunakan untuk mendeteksi tepi pada gambar yang telah difilter menggunakan filter Gaussian (blur). Parameter 190 dan 100 adalah nilai ambang batas atas dan bawah untuk deteksi tepi. Hasil deteksi tepi disimpan dalam variabel edges.
6.	Menerapkan transformasi Hough untuk mendeteksi garis: Fungsi cv2.HoughLinesP() digunakan untuk mendeteksi garis pada gambar yang telah didapatkan dari deteksi tepi (edges). Parameter-parameter seperti jarak resolusi (1), sudut resolusi (np.pi/150), threshold (60), panjang garis minimum (20), dan jarak maksimum antara garis (50) ditentukan untuk mendapatkan garis yang diinginkan. Hasil deteksi garis disimpan dalam variabel lines.
7.	Menggambar garis-garis yang terdeteksi pada gambar asli: Jika garis-garis berhasil terdeteksi (variabel lines tidak kosong), program akan mengiterasi setiap garis dan menggunakan fungsi cv2.line() untuk menggambar garis pada gambar asli (image). Warna garis ditentukan dengan parameter (0, 0, 255) yang menyatakan warna merah dan ketebalan garis adalah 3 piksel.
8.	Menampilkan gambar hasil deteksi marka jalan: Gambar hasil deteksi marka jalan yang telah digambar garis-garisnya ditampilkan menggunakan fungsi cv2.imshow(). Program akan menunggu hingga pengguna menekan tombol apa pun pada keyboard (cv2.waitKey(0)). Setelah itu, jendela tampilan gambar ditutup menggunakan cv2.destroyAllWindows().

Dengan menggunakan program ini, gambar jalan dapat diproses untuk mendeteksi dan menggambar garis-garis marka jalan yang ada pada gambar tersebut.
