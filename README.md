# Exercise-7
Exercise 7 – Demonstrate that the sharing of resources in a multitasking design can lead to a deterioration in system performance

## 📦 Komponen yang Digunakan

- **Mikrokontroler**: STM32 (dapat disesuaikan dengan STM32F103 atau STM32F407)
- **LED**: LED Hijau, Merah, Oranye, dan Biru
- **Perangkat Lunak**: STM32CubeMX, Keil uVision, atau IDE lain yang mendukung STM32
- **Library HAL**: Digunakan untuk akses GPIO dan delay
- **RTOS**: FreeRTOS atau RTOS lain yang kompatibel

## ✨ Fitur Utama

1. **Demonstrasi Multitasking**: Menunjukkan bagaimana beberapa tugas dijalankan secara bersamaan.
2. **Resource Sharing**: Menampilkan dampak dari penggunaan resource bersama oleh beberapa tugas.
3. **Mutual Exclusion**: Implementasi kontrol akses resource dengan **taskENTER_CRITICAL()** dan **taskEXIT_CRITICAL()**.
4. **Pengujian Performa**: Menampilkan perbandingan performa sistem dengan dan tanpa kontrol akses resource.

## ⚙️ Pengaturan

### Konfigurasi Prioritas Tugas
- **Tugas LED Hijau dan Merah**: Prioritas normal
- **Tugas LED Oranye**: Prioritas di atas normal (prioritas tertinggi)

### Pola Nyala LED
- **LED Hijau**: Menyala setiap 200 ms
- **LED Merah**: Menyala setiap 550 ms
- **LED Oranye**: Berkedip dengan frekuensi 10 Hz (setiap 50 ms)

## 🚀 Cara Menggunakan

1. **Persiapan Perangkat Keras**:  
   Sambungkan LED Hijau, Merah, Oranye, dan Biru ke pin GPIO mikrokontroler sesuai dengan konfigurasi proyek.

2. **Konfigurasi Perangkat Lunak**:  
   - Buka proyek di STM32CubeMX atau IDE pilihan Anda.
   - Pastikan library HAL dan RTOS telah diaktifkan.
   - Atur pin GPIO untuk masing-masing LED.

3. **Implementasi Kode**:  
   - Tambahkan kode tugas LED sesuai dengan pola nyala yang dijelaskan.
   - Implementasikan fungsi `AccessSharedData()` dengan simulasi operasi baca/tulis selama satu detik.
   - Uji sistem dengan langkah berikut:
     - **Langkah 1**: Jalankan satu tugas saja, periksa apakah perilaku sesuai prediksi.
     - **Langkah 2**: Jalankan semua tugas tanpa mutual exclusion, perhatikan pola nyala LED.
     - **Langkah 3**: Tambahkan mekanisme mutual exclusion, ulangi pengujian dan perhatikan perubahan pola nyala LED.

4. **Kompilasi dan Flashing**:  
   - Kompilasi proyek dan unggah ke mikrokontroler.
   - Amati pola nyala LED untuk melihat dampak resource sharing.

## 📚 Kesimpulan

Proyek ini menunjukkan pentingnya kontrol akses resource dalam sistem multitasking, di mana pengabaian kontrol dapat menyebabkan degradasi performa atau bahkan kegagalan sistem. Melalui simulasi ini, kita belajar bahwa menjaga waktu akses resource seminimal mungkin dan mengurangi jumlah tugas dapat mengurangi ketidakpastian waktu dan meningkatkan keandalan sistem.

---

💡 **Catatan Penting**: Jangan menonaktifkan interupsi dalam waktu yang lama, karena dapat menyebabkan gangguan serius pada performa sistem.

## **Diagram System**
<img src="system%20task%20diagram7.png" alt="Pinout Diagram" style="max-width: 600px; height: auto;">
