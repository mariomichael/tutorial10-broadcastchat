# REFLEKSI

##  2.1: Original code, and how it run
![ss1](images/1server_3client.png)

Cara menjalankan program tersebut adalah membuka direktori program di empat windows terminal, lalu menjalankan `cargo run --bin server` di salah satu terminal dan menjalankan `cargo run --bin client` di ketiga terminal lainnya. Yang terjadi ketika saya mengetik suatu teks pada clients adalah teks tersebut akan diterima oleh server dan server akan mengirimkannya ke setiap client yang terhubung dengannya (broadcast). Oleh karena itu pesan yang dikirim oleh satu client bisa sampai dan dilihat oleh client lainnya. Semua client tersebut dihubungkan oleh server.

## 2.2: Modifying port
![ss2](images/change_port.png)

Seperti yang bisa dilihat pada gambar, pengubahan port pada kedua sisi berhasil dan tetap bisa berjalan pada port baru. Pengubahan port dari `2000` menjadi `8080` dilakukan pada `client.rs` (sisi klien) dan `server.rs` (sisi server). Pengubahan pada sisi klien dilakukan pada `ClientBuilder` di line 10, sedangkan perubahan pada sisi server dilakukan pada pernyataan variabel `listener` dan `println` di line 44-45. File lain yang perlu dimodifikasi (server.rs) menggunakan websocket yang sama yaitu `tokio_websockets`.