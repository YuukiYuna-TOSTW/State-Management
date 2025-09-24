# 📝 Perbedaan Ephemeral State vs App State di Flutter

Flutter menyediakan dua cara utama untuk mengelola state: **Ephemeral State** dan **App State**.  
Perbedaan ini penting dipahami agar aplikasi lebih mudah dikembangkan, terutama pada skala besar.

---

## 1️⃣ Ephemeral State (Local / State Sementara)

### 🔹 Lingkup
Data yang hanya digunakan di **satu widget** saja.

### 🔹 Umur State
Hilang saat widget dibuang atau direbuild.

### 🔹 Contoh
- Status sebuah tombol (aktif / nonaktif)  
- Input sementara pada `TextField`  
- Posisi scroll pada halaman tertentu  

### 🔹 Manajemen
Disimpan langsung di `StatefulWidget` melalui kelas `State`.

### ✅ Kelebihan
- Sederhana dan cepat  
- Tidak butuh sistem besar atau library tambahan  

### ❌ Kekurangan
- Tidak bisa dibagikan ke widget lain  
- Hilang saat widget tidak aktif  

> **Kesimpulan:** Ephemeral state cocok untuk elemen UI sederhana yang **tidak memerlukan persistensi data lintas widget**.

---

## 2️⃣ App State (Global / State Aplikasi)

### 🔹 Lingkup
Data penting yang digunakan di berbagai widget atau **seluruh aplikasi**.

### 🔹 Umur State
Tetap ada selama aplikasi berjalan (persisten).

### 🔹 Contoh
- **User Authentication:** Status login, token akses, data profil pengguna  
- **Shopping Cart:** Item yang ditambahkan user harus muncul di halaman checkout, ringkasan pesanan, dll.  
- Tema aplikasi (dark/light mode)  

### 🔹 Manajemen
Menggunakan state management global seperti **Provider**, **Riverpod**, **Bloc**, atau lainnya.

### ✅ Kelebihan
- Data konsisten di banyak widget  
- Mudah dikelola dan diperbarui di seluruh aplikasi  
- Lebih mudah mengimplementasikan fitur besar seperti login, keranjang belanja, dll  

### ❌ Kekurangan
- Butuh setup / arsitektur tambahan (sedikit lebih kompleks di awal)

> **Kesimpulan:** App state ideal untuk data yang **perlu dibagikan secara global**, memastikan konsistensi di seluruh aplikasi.

---

## 💡 Kenapa App State Management Penting di Aplikasi Flutter yang Besar?

Pada aplikasi sederhana, **ephemeral state** sudah cukup.  
Namun, untuk aplikasi skala besar dengan banyak halaman atau komponen yang berbagi data, penggunaan **App State Management** menjadi sangat penting.

### 🎯 Keuntungan Utama
- **Konsistensi Data:** Data user, keranjang belanja, dan pengaturan lainnya tetap sinkron di semua halaman  
- **Kemudahan Maintenance:** Lebih mudah melakukan perubahan atau debugging karena state dikelola secara terpusat  
- **Skalabilitas:** Struktur aplikasi lebih siap untuk berkembang menjadi besar  
- **Dukungan Fitur Kompleks:** Autentikasi pengguna, mode offline/online, sinkronisasi data real-time, dll  
