# 📦 Log Archive Tool

CLI tool sederhana untuk mengarsipkan file log dengan otomatis memberi timestamp, mengompresnya dalam format `.tar.gz`, dan menyimpannya dalam direktori arsip terpisah. Cocok untuk menjaga sistem tetap rapi tanpa kehilangan riwayat log penting.

project page URL : https://roadmap.sh/projects/log-archive-tool

## ✨ Fitur

* Mengarsipkan seluruh isi direktori log dalam satu perintah.
* Memberi nama arsip otomatis berdasarkan tanggal & waktu:
  `logs_archive_20251103_143022.tar.gz`
* Menyimpan catatan (log) setiap aktivitas arsip ke file `archive_history.log`.
* Ringan, cepat, dan hanya butuh Bash  tidak perlu dependensi eksternal.

## 🚀 Instalasi

1. Clone repositori ini:

   ```bash
   git clone https://github.com/nama-username/log-archive-tool.git
   cd log-archive-tool
   ```

2. (Opsional) Pasang secara global agar bisa dipanggil dari mana saja:

   ```bash
   sudo cp log-archive /usr/local/bin/
   ```

## 🛠️ Penggunaan

```bash
log-archive <direktori-log>
```

### Contoh:

```bash
# Arsipkan log Nginx
log-archive /var/log/nginx

# Arsipkan log sistem (perlu sudo jika tidak punya akses)
sudo log-archive /var/log
```

> 💡 Pastikan direktori yang diberikan **benar-benar ada** dan berisi file log.

## 📂 Hasil yang Dihasilkan

Setelah dijalankan, tool ini akan membuat:

* Direktori `logs_archive/` (jika belum ada) → berisi file `.tar.gz`
* File `archive_history.log` → berisi riwayat kapan arsip dibuat

Contoh struktur setelah dijalankan:

```
log-archive-tool/
├── log-archive
├── README.md
├── archive_history.log
└── logs_archive/
    └── logs_archive_20251103_143022.tar.gz
```

## 📝 Catatan

* Untuk mengarsipkan direktori sistem seperti `/var/log`, kamu mungkin perlu menjalankan dengan `sudo`.
* Jika ingin otomatisasi harian, pertimbangkan menggunakan `cron`:

  ```bash
  # Jalankan setiap jam 2 pagi
  0 2 * * * /usr/local/bin/log-archive /var/log
  ```
  
---

Dibuat dengan 💻 untuk sistem berbasis Unix/Linux  termasuk WSL!

---
