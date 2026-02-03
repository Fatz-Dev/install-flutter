# install-flutter

# 📱 Dokumentasi Setup Flutter Project (Tanpa Android Studio)

Dokumentasi ini menjelaskan **langkah lengkap setup Flutter** mulai dari **membuat project**, **menjalankan emulator Android**, **menjalankan di HP fisik**, hingga **menjalankan aplikasi Flutter** menggunakan **VS Code / terminal**, **tanpa Android Studio**.

---

## 1️⃣ Prasyarat

### Sistem

* Windows 10 / 11 (64-bit)
* Internet stabil

### Software yang Dibutuhkan

* **Flutter SDK (Stable)**
* **Android SDK Command Line Tools**
* **Java JDK (minimal JDK 17)**
* **VS Code** + ekstensi Flutter

---

## 2️⃣ Install Flutter SDK

### Download

* [https://flutter.dev](https://flutter.dev)

### Install

1. Extract ke folder, contoh:

```
D:\flutter
```

2. Tambahkan ke PATH:

```
D:\flutter\bin
```

### Cek instalasi

```bash
flutter doctor
```

---

## 3️⃣ Install Android SDK (Tanpa Android Studio)

### Download Command Line Tools

* [https://developer.android.com/studio](https://developer.android.com/studio)
* Download **Command line tools only (Windows)**

### Struktur folder (WAJIB)

```
Android\Sdk\cmdline-tools\latest\
```

Isi folder `latest`:

```
bin
lib
source.properties
```

### Tambahkan ke PATH

```
C:\Users\Fatz\AppData\Local\Android\Sdk\cmdline-tools\latest\bin
C:\Users\Fatz\AppData\Local\Android\Sdk\platform-tools
C:\Users\Fatz\AppData\Local\Android\Sdk\emulator
```

---

## 4️⃣ Install SDK Package Penting

```bash
sdkmanager "platform-tools" "emulator" "platforms;android-34" "build-tools;34.0.0"
```

Terima license:

```bash
sdkmanager --licenses
```

Tekan `y` sampai selesai.

---

## 5️⃣ Setup Emulator Android

### Download system image

```bash
sdkmanager "system-images;android-34;google_apis;x86_64"
```

### Buat emulator (AVD)

```bash
avdmanager create avd -n pixel_api_34 -k "system-images;android-34;google_apis;x86_64" -d pixel
```

### Jalankan emulator

```bash
emulator -avd pixel_api_34
```

---

## 6️⃣ Jalankan Flutter di Emulator

### Cek device

```bash
flutter devices
```

### Run project

```bash
flutter run
```

---

## 7️⃣ Run Flutter di HP Fisik

### Di HP Android

1. Aktifkan **Developer Options**
2. Aktifkan **USB Debugging**

### Hubungkan HP ke PC

```bash
adb devices
```

Pastikan status **device** (bukan unauthorized)

### Jalankan Flutter

```bash
flutter run
```

---

## 8️⃣ Membuat Project Flutter Baru

```bash
flutter create my_app
cd my_app
code .
```

Struktur utama:

```
lib/main.dart
pubspec.yaml
```

---

## 9️⃣ Menjalankan Project

### Web

```bash
flutter run -d chrome
```

### Emulator Android

```bash
flutter run
```

### HP Fisik

```bash
flutter run
```

---

## 🔟 Error Umum & Solusi

### ❌ sdkmanager tidak dikenali

➡ PATH cmdline-tools salah

### ❌ emulator tidak dikenali

➡ PATH `Sdk\emulator` belum ditambahkan

### ❌ No pubspec.yaml

➡ Tidak di root project

### ❌ Visual Studio toolchain error

➡ Pilih device Android / Chrome, bukan Windows

---

## ✅ Checklist Akhir

* [x] flutter doctor tanpa error Android
* [x] emulator bisa dijalankan
* [x] adb devices mendeteksi device
* [x] flutter run berhasil

---

🎉 **Setup Flutter selesai — tanpa Android Studio!**

Jika ingin:

* Setup iOS
* Setup Firebase
* Build APK / AAB
* Dokumentasi versi PDF / laporan kampus

👉 Tinggal bilang 👍
