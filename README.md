UAS PENGOLAHAN CITRA DIGITAL C

Langkah-langkah
Load Gambar

Gambar nanas.jpeg dimuat menggunakan OpenCV (cv2.imread()). Jika gambar tidak dapat dimuat, akan muncul pesan kesalahan.

Konversi ke Ruang Warna RGB

Gambar yang dimuat kemudian dikonversi dari format BGR (default OpenCV) ke RGB untuk keperluan visualisasi dengan Matplotlib.

Konversi ke Ruang Warna HSV

Setelah konversi ke RGB, gambar juga dikonversi ke ruang warna HSV (cv2.cvtColor()). Ruang warna HSV memungkinkan pemrosesan berdasarkan hue (warna), saturation (kejenuhan), dan value (nilai kecerahan) yang lebih intuitif.
Definisi Rentang Warna

Rentang warna untuk segmentasi ditentukan dalam ruang warna HSV:
Buah Nanas (Orange): Rentang warna untuk buah nanas yang berwarna oren ditentukan menggunakan lower_orange dan upper_orange.
Daun (Dark Green): Rentang warna untuk daun yang berwarna hijau tua ditentukan menggunakan lower_dark_green dan upper_dark_green.
Pembuatan Mask (Pemaskeran)

Menggunakan cv2.inRange(), dibuat masker (orange_mask dan dark_green_mask) untuk mengidentifikasi area di gambar yang sesuai dengan rentang warna yang ditentukan.
Segmentasi dengan Masker

cv2.bitwise_and() digunakan untuk menerapkan masker (orange_mask dan dark_green_mask) ke gambar asli (image_rgb). Hasilnya adalah orange_segment yang merupakan segmentasi buah nanas berwarna oren dan dark_green_segment yang merupakan segmentasi daun berwarna hijau tua.

Visualisasi Hasil

Hasil segmentasi ditampilkan menggunakan Matplotlib dalam bentuk grid 2x2, yang meliputi:
Gambar asli (Original Image).
Masker untuk buah nanas (oren) dan daun (hijau tua).
Hasil segmentasi untuk buah nanas (oren) dan daun (hijau tua).

