# Sistem Delivery Order Makanan

Sistem pemesanan makanan online yang memanfaatkan teknologi peta untuk mempermudah proses pemesanan dan pengiriman. Sistem ini memungkinkan pelanggan untuk memilih menu makanan dan minuman, menentukan lokasi mereka secara langsung di peta, menghitung jarak dari restoran, dan menghitung ongkos kirim secara otomatis.

## 🎯 Fitur Utama

### 🍽️ Pilihan Menu Lengkap
- **5 Jenis Makanan**: Nasi Goreng Spesial, Mie Ayam Bakso, Gado-Gado, Sate Ayam (10 tusuk), Rendang
- **5 Jenis Minuman**: Es Teh Manis, Es Jeruk, Jus Alpukat, Es Campur, Kopi Susu
- **Quantity Control**: Tombol +/- untuk mengatur jumlah pesanan dengan mudah
- **Real-time Summary**: Tampilan summary pesanan yang update secara real-time

### 🛒 Keranjang Belanja Interaktif
- **Summary Pesanan**: Menampilkan detail item, quantity, dan harga per item
- **Tombol Cancel**: Fitur untuk menghapus item dari pesanan dengan mudah
- **Total Harga Otomatis**: Perhitungan total harga menu secara otomatis

### 📍 Menentukan Lokasi
- **Peta Interaktif**: Pilih lokasi langsung dari peta dengan klik
- **GPS Integration**: Gunakan lokasi GPS perangkat Anda
- **Koordinat Manual**: Masukkan koordinat secara manual jika diperlukan

### 📏 Perhitungan Jarak & Ongkir
- **Rute Jalan Sebenarnya**: Menggunakan OSRM routing engine untuk menghitung jarak berdasarkan rute jalan yang sebenarnya
- **Ongkir Otomatis**: Perhitungan ongkos kirim otomatis berdasarkan jarak (Rp 500/km)
- **Total Pembayaran**: Menampilkan total pembayaran (menu + ongkir) secara real-time

### 💬 Integrasi WhatsApp
- **Pesan Lengkap**: Mengirim informasi lengkap pesanan ke WhatsApp, termasuk:
  - Detail menu yang dipilih
  - Subtotal menu
  - Lokasi pengiriman (link Google Maps)
  - Koordinat GPS
  - Jarak dan ongkir
  - Total pembayaran
  - Catatan tambahan (opsional)

### 🗺️ Peta Interaktif dengan Rute
- **Visualisasi Rute**: Garis rute biru yang mengikuti jalan sebenarnya
- **Marker Lokasi**: Marker untuk restoran dan lokasi pelanggan
- **Zoom & Pan**: Kontrol penuh untuk melihat detail lokasi

## 🚀 Cara Penggunaan

### Langkah 1: Pilih Menu
1. Pilih makanan dan minuman yang diinginkan
2. Gunakan tombol **+** untuk menambah quantity
3. Gunakan tombol **-** untuk mengurangi quantity
4. Lihat summary pesanan di bagian bawah
5. Gunakan tombol **X** untuk menghapus item jika perlu
6. Klik **"Lanjutkan ke Pilih Lokasi"** setelah selesai memilih menu

### Langkah 2: Tentukan Lokasi
1. Setelah menu dipilih, section lokasi akan muncul
2. Pilih lokasi dengan salah satu cara:
   - **Klik pada peta** untuk menentukan lokasi
   - **Klik "Gunakan Lokasi Saya"** untuk menggunakan GPS
   - **Masukkan koordinat manual** (format: lat, lng)
3. Sistem akan menghitung jarak dan ongkir secara otomatis
4. Lihat menu yang dipilih, jarak, ongkir, dan total pembayaran di panel kanan

### Langkah 3: Konfirmasi & Kirim
1. (Opsional) Tambahkan catatan khusus di textarea
2. Klik **"Kirim ke WhatsApp"** untuk mengirim pesanan
3. Pesan akan terbuka di WhatsApp dengan informasi lengkap
4. Konfirmasi pesanan dengan restoran melalui WhatsApp

### Fitur Tambahan
- **Kembali ke Menu**: Tombol "Kembali ke Menu" untuk mengubah pesanan
- **Update Real-time**: Semua perubahan menu langsung terupdate di section lokasi
- **Validasi Jarak**: Sistem akan menolak lokasi yang terlalu jauh (>50 km)

## 💡 Manfaat

### Untuk Pelanggan
- ✅ **Mudah dan Cepat**: Pilih menu dan lokasi dengan mudah tanpa repot
- ✅ **Transparansi Harga**: Lihat total pembayaran sebelum konfirmasi
- ✅ **Fleksibilitas**: Ubah pesanan kapan saja sebelum konfirmasi
- ✅ **Akurasi**: Perhitungan jarak dan ongkir yang akurat
- ✅ **Kenyamanan**: Kirim pesanan langsung via WhatsApp

### Untuk Restoran/Toko
- ✅ **Efisiensi**: Mengurangi kesalahan komunikasi
- ✅ **Informasi Lengkap**: Menerima informasi lengkap pesanan via WhatsApp
- ✅ **Akurasi Lokasi**: Koordinat GPS yang akurat untuk pengiriman
- ✅ **Perhitungan Otomatis**: Ongkir sudah dihitung otomatis

## 🛠️ Teknologi yang Digunakan

- **HTML5** & **CSS3** untuk tampilan dan styling
- **JavaScript (ES6+)** untuk interaksi dan logika aplikasi
- **Leaflet.js** untuk peta interaktif
- **OSRM Routing Engine** untuk perhitungan rute dan jarak
- **Bootstrap 5** untuk responsive design
- **Font Awesome** untuk ikon
- **WhatsApp API** untuk pengiriman pesan

## 📦 Instalasi

1. Clone repositori ini ke lokal komputer Anda:
   ```bash
   git clone https://github.com/Cwinzer321/gabin.git
   ```

2. Buka folder project:
   ```bash
   cd Sistem_DO_Makanan
   ```

3. Buka file `index.html` di browser web Anda

4. (Opsional) Untuk development, gunakan local server:
   ```bash
   # Menggunakan Python
   python -m http.server 8000
   
   # Menggunakan PHP
   php -S localhost:8000
   
   # Menggunakan Node.js (http-server)
   npx http-server
   ```

5. Akses melalui browser: `http://localhost:8000`

## ⚙️ Konfigurasi

### Mengubah Lokasi Restoran
Edit koordinat restoran di file `index.html`:
```javascript
const restoLatLng = {
    lat: -6.251627,   // Ganti dengan latitude restoran Anda
    lng: 107.246045   // Ganti dengan longitude restoran Anda
};
```

### Mengubah Tarif Ongkir
Edit tarif ongkir per kilometer di file `index.html`:
```javascript
function calculateOngkir(distance) {
    const farePerKm = 500;  // Ganti dengan tarif Anda (dalam rupiah)
    return Math.ceil(distance) * farePerKm;
}
```

### Mengubah Menu
Edit menu di file `index.html`:
```javascript
const menuData = {
    foods: [
        { id: 'food1', name: 'Nasi Goreng Spesial', price: 25000 },
        // Tambahkan menu makanan lainnya
    ],
    drinks: [
        { id: 'drink1', name: 'Es Teh Manis', price: 5000 },
        // Tambahkan menu minuman lainnya
    ]
};
```

### Mengubah Nomor WhatsApp
Edit nomor WhatsApp di file `index.html`:
```javascript
const linkWA = `https://wa.me/6285157204233?text=${encodeURIComponent(pesanWA)}`;
// Ganti 6285157204233 dengan nomor WhatsApp Anda (format: 62XXXXXXXXX)
```

## 📱 Browser Support

- ✅ Chrome (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ⚠️ Internet Explorer (tidak didukung)

## 🔒 Keamanan

- Sistem ini berjalan sepenuhnya di client-side (browser)
- Tidak ada data yang disimpan di server
- Semua perhitungan dilakukan secara lokal
- Koordinat GPS hanya digunakan untuk keperluan pemesanan

## 📝 Lisensi

Proyek ini bebas digunakan untuk keperluan komersial maupun non-komersial.

## 👥 Kontribusi

Kontribusi sangat diterima! Silakan buat pull request atau buka issue untuk diskusi.

## 📞 Kontak

- **WhatsApp**: +62 851-5720-4233
- **Email**: (tambahkan email jika ada)

## 🙏 Terima Kasih

Terima kasih telah menggunakan Sistem Delivery Order Makanan! Semoga sistem ini dapat membantu meningkatkan efisiensi bisnis Anda.

---

**Dibuat dengan ❤️ untuk memudahkan pemesanan makanan online**
