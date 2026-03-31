# CITRA-DIGITAL-4
Transformasi gray, statistics dalam image enhancement
Jurnal : 
Kusnadi, “Implementation of Grayscale Image Transformation and Histogram Equalization Methods”
Note :
KETERANGAN SETIAP POIN
1. Konversi RGB ke Grayscale
Kode:
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

Penjelasan:
Grayscale mengubah gambar berwarna menjadi abu-abu dengan menggabungkan nilai RGB menjadi satu intensitas (0–255). Tujuannya untuk menyederhanakan data agar lebih mudah diproses.

--------------------------------------------------

2. Konversi Grayscale ke Biner
Kode:
_, binary = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)

Penjelasan:
Mengubah gambar grayscale menjadi hitam-putih. Pixel dengan nilai >127 menjadi putih (255), sedangkan ≤127 menjadi hitam (0). Digunakan untuk memisahkan objek dari latar belakang.

--------------------------------------------------

3. Konversi Grayscale ke M-bit
Kode:
m = 3
m_bit = np.floor(gray / (256 / (2**m))) * (256 / (2**m))
m_bit = m_bit.astype(np.uint8)

Penjelasan:
Mengurangi jumlah level keabuan dari 256 level (8-bit) menjadi lebih sedikit, misalnya 3-bit (8 level). Hasilnya gambar terlihat lebih kasar dan biasanya digunakan untuk kompresi.

--------------------------------------------------

4. Image dengan Brightness
Kode:
brightness = cv2.convertScaleAbs(img_rgb, alpha=1, beta=50)

Penjelasan:
Brightness mengatur tingkat kecerahan gambar dengan menambahkan nilai pixel. Semakin besar nilai beta, gambar akan semakin terang.

--------------------------------------------------

5. Image dengan Contrast
Kode:
contrast = cv2.convertScaleAbs(img_rgb, alpha=1.5, beta=0)

Penjelasan:
Contrast mengatur perbedaan antara terang dan gelap. Semakin besar nilai alpha, maka perbedaan kontras akan semakin jelas.

--------------------------------------------------

6. Grayscale ke Histogram
Kode:
hist = cv2.calcHist([gray],[0],None,[256],[0,256])

Penjelasan:
Histogram adalah grafik yang menunjukkan distribusi intensitas pixel (0–255). Digunakan untuk mengetahui apakah gambar cenderung gelap atau terang.

--------------------------------------------------

7. Histogram Equalization
Kode:
equalized = cv2.equalizeHist(gray)

Penjelasan:
Histogram equalization digunakan untuk meningkatkan kontras gambar dengan meratakan distribusi intensitas pixel sehingga detail gambar menjadi lebih jelas.

PENJELASAN TEORI APAKAH SAMA 

Secara konsep, teori di kelas dan implementasi kode di Google Colab adalah sama, tetapi secara proses terdapat perbedaan.

Persamaan:
- Keduanya menggunakan konsep dasar pengolahan citra digital seperti grayscale, thresholding, histogram, dan histogram equalization.
- Rumus matematis yang digunakan tetap sama, misalnya perhitungan intensitas pixel dan distribusi histogram.

Perbedaan:
- Pada teori di kelas, proses dilakukan secara manual menggunakan rumus dan perhitungan langkah demi langkah.
- Pada kode di Google Colab, proses dilakukan secara otomatis menggunakan library seperti OpenCV dan NumPy.
- Di kelas lebih fokus pada pemahaman konsep, sedangkan di coding lebih fokus pada implementasi dan hasil.

Kesimpulan:
Kode program di Google Colab merupakan implementasi langsung dari teori yang dipelajari di kelas. Library seperti OpenCV hanya membantu mempercepat proses, tetapi tetap menggunakan konsep yang sama.







