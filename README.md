# Device Insight Suite — Deep Scan v2.0

Versi ini mengganti spesifikasi contoh dengan pembacaan runtime dari Android menggunakan `react-native-device-info`, Expo Device, Expo Battery, dan Expo Sensors.

## Yang dibaca
- Identitas model/build Android (manufacturer, model, API, fingerprint, board, hardware, bootloader, security patch, ABI).
- RAM total/terpakai dan kapasitas penyimpanan total/kosong.
- CPU core count dan arsitektur ABI yang dilaporkan sistem.
- Baterai, status hemat daya, dan ketersediaan accelerometer/gyroscope/magnetometer.
- Informasi jaringan tertentu jika API Android mengizinkan.

## Batasan penting
Ini bukan root scanner. Android membatasi akses aplikasi biasa terhadap IMEI/serial, MAC, proses aplikasi lain, /proc/net, partisi sistem, dan informasi kernel tertentu. Sebagian API bisa mengembalikan kosong/terbatas tergantung versi Android, pabrikan, dan izin. Aplikasi sengaja tidak meminta izin sensitif yang tidak diperlukan dan tidak mencoba melewati keamanan OS. RAM terpakai merupakan estimasi yang dilaporkan library/API, bukan pembacaan semua proses. Sensor ditampilkan sebagai tersedia/tidak tersedia, bukan diagnosis kalibrasi.

## Build APK
1. Install Node.js dan EAS CLI pada komputer/cloud build.
2. `npm install`
3. `npx expo prebuild` (atau EAS Build akan menyiapkan native project).
4. `npx eas build --platform android --profile preview`

Perlu EAS account. File ini adalah source project, bukan APK. Belum dikompilasi atau dites pada perangkat fisik. Sebelum rilis, jalankan build dan uji hasil di HP Android.
