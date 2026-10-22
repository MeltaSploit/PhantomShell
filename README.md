# C2 Client GUI - Generator & Listener

---

## 📌 Daftar Isi
1. [Deskripsi](#-deskripsi)
2. [Fitur Utama](#-fitur-utama)
3. [Persyaratan Sistem](#-persyaratan-sistem)
4. [Cara Compile](#-cara-compile)
5. [Cara Menggunakan](#-cara-menggunakan)
6. [Struktur File](#-struktur-file)
7. [Panduan Fitur](#-panduan-fitur)
8. [Troubleshooting](#-troubleshooting)
9. [Catatan Keamanan](#-catatan-keamanan)

---

## 📝 Deskripsi

**C2 Client GUI** adalah sebuah *Command & Control* (C2) framework sederhana berbasis GUI Windows. Tools ini memiliki dua fungsi utama:

1. **Payload Generator** — Membuat file `.exe` (reverse shell) yang bisa dijalankan di komputer target.
2. **Listener / Server** — Menerima koneksi dari payload, lalu memberikan akses shell, upload/download file, screenshot, dan fitur lainnya.

Dibangun dengan **C++ murni**, **Win32 API**, dan **Winsock2** — tanpa framework berat, tanpa dependensi eksternal selain compiler `gcc`.

---

## ✨ Fitur Utama

### 🖥️ Payload Generator
- ✅ Generate payload `.exe` dengan nama kustom
- ✅ Konfigurasi IP dan Port target via GUI
- ✅ Auto-compile menggunakan `gcc` (MinGW)
- ✅ Payload berjalan *silent* (`-mwindows`, tanpa console)

### 🎧 Listener & Shell
- ✅ Multi-target (bisa handle banyak koneksi sekaligus)
- ✅ Pilih target aktif via listbox
- ✅ Auto-restart listener jika crash
- ✅ Command history dengan panah `↑` / `↓`
- ✅ Warna console hijau di background hitam

### 📁 File Transfer
- ✅ Upload file ke target
- ✅ Download file dari target
- ✅ Auto-rename jika file sudah ada (avoid overwrite)

### 🛠️ Tools Tambahan
- ✅ **Screenshot** — Capture layar target via PowerShell
- ✅ **Port Scan** — Scan 16 port umum di IP target
- ✅ **Clear Console** — Bersihkan log

---

## 💻 Persyaratan Sistem

### Untuk Compile (Development)
| Komponen | Versi Minimum |
|----------|---------------|
| OS | Windows 7 / 8 / 10 / 11 |
| Compiler | MinGW-w64 (GCC) atau MSYS2 |
| Library | `ws2_32`, `comctl32`, `ole32`, `comdlg32` |

### Untuk Menjalankan `test.exe`
| Komponen | Keterangan |
|----------|------------|
| OS | Windows 7 ke atas |
| Runtime | Tidak perlu (static-linked) |
| Network | Port listener harus terbuka di firewall |

### Instalasi MinGW (jika belum ada)
1. Download **MSYS2** dari [msys2.org](https://www.msys2.org/)
2. Install, lalu buka terminal MSYS2:
   ```bash
   pacman -S mingw-w64-x86_64-gcc# PhantomShell
