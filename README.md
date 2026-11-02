<div align="center">

# 🚀 RakitanManager-RebornX

### Modern USB Modem Management for OpenWrt

[![Release](https://img.shields.io/github/v/release/rtaserver/RakitanManager-Reborn?style=for-the-badge&logo=github&color=blue)](https://github.com/rtaserver-wrt/RakitanManager-Reborn/releases)
[![License](https://img.shields.io/github/license/rtaserver/RakitanManager-Reborn?style=for-the-badge&logo=opensourceinitiative&logoColor=white)](LICENSE)
[![Stars](https://img.shields.io/github/stars/rtaserver/RakitanManager-Reborn?style=for-the-badge&logo=github)](https://github.com/rtaserver-wrt/RakitanManager-Reborn/stargazers)
[![Issues](https://img.shields.io/github/issues/rtaserver/RakitanManager-Reborn?style=for-the-badge&logo=github)](https://github.com/rtaserver-wrt/RakitanManager-Reborn/issues)

**RakitanManager-Reborn** adalah platform manajemen modem USB/4G/5G yang ringan dan modular, dirancang khusus untuk perangkat OpenWrt. Kelola multiple modem dengan mudah melalui antarmuka web yang intuitif.

[Dokumentasi](https://github.com/rtaserver-wrt/RakitanManager-Reborn/wiki) • [Laporkan Bug](https://github.com/rtaserver-wrt/RakitanManager-Reborn/issues) • [Request Fitur](https://github.com/rtaserver-wrt/RakitanManager-Reborn/issues)

</div>

---

## ✨ Fitur Unggulan

<table>
<tr>
<td width="50%">

### 🔌 Multi-Vendor Support
- Dukungan modem dari berbagai vendor
- Arsitektur modular untuk penambahan modem baru
- Konfigurasi per-modem yang fleksibel

</td>
<td width="50%">

### 🎛️ Manajemen Terpusat
- Konfigurasi centralized di `modems.json`
- Skrip otomasi untuk setup cepat
- Monitoring real-time via web interface

</td>
</tr>
<tr>
<td width="50%">

### 🌐 Web Interface
- Dashboard berbasis PHP yang responsif
- Monitoring status modem secara visual
- Konfigurasi mudah tanpa CLI

</td>
<td width="50%">

### ⚡ Lightweight & Fast
- Footprint minimal untuk embedded devices
- Optimized untuk OpenWrt
- Resource-efficient operations

</td>
</tr>
</table>

---

## 🎯 Quick Start

### Instalasi Satu Baris

```bash
bash -c "$(wget -qO - 'https://raw.githubusercontent.com/rtaserver-wrt/RakitanManager-Reborn/main/install.sh')"
```

---

## 📋 System Requirements

| Component | Requirement |
|-----------|-------------|
| **OS** | OpenWrt 21.x atau lebih baru |
| **Shell** | bash / sh |
| **Web Server** | PHP 7.x+ (untuk web interface) |
| **Python** | Python 3.x (untuk modul tertentu) |
| **Storage** | ~10MB ruang kosong |

---

## 📁 Struktur Proyek

```
├── 📂 RakitanManager-Reborn/
│   ├── 📄 CHANGELOG.md
│   ├── 📄 install.sh
│   ├── 📄 LICENSE
│   ├── 📄 README.md
│   └── 📄 version
│   
└── 📂 rakitanmanager
    ├── 📂 config
    │   └── 📄 rakitanmanager
    │
    ├── 📂 core
    │   ├── 📄 core-manager.sh
    │   ├── 📄 modem-hilink.sh
    │   ├── 📄 modem-hp.sh
    │   ├── 📄 modem-mf90.sh
    │   ├── 📄 modem-orbit.py
    │   ├── 📄 modem-rakitan.sh
    │   ├── 📄 modems.json
    │   ├── 📄 rakitanmanager.log
    │   └── 📄 update.sh
    │
    ├── 📂 init.d
    │    └── 📄 rakitanmanager
    │
    └── 📂 web
        ├── 📄 index.php
        ├── 📄 update.php
        │
        └── 📂 assets
            ├── 📄 download.png
            │
            ├── 📂 css
            │   └── 📄 all.min.css
            │
            ├── 📂 fonts
            │   ├── 📄 inter-bold.woff
            │   ├── 📄 inter-bold.woff2
            │   ├── 📄 inter-medium.woff
            │   ├── 📄 inter-medium.woff2
            │   ├── 📄 inter-regular.woff
            │   ├── 📄 inter-regular.woff2
            │   ├── 📄 inter-semibold.woff
            │   ├── 📄 inter-semibold.woff2
            │   ├── 📄 poppins-bold.woff
            │   ├── 📄 poppins-bold.woff2
            │   ├── 📄 poppins-medium.woff
            │   ├── 📄 poppins-medium.woff2
            │   ├── 📄 poppins-regular.woff
            │   ├── 📄 poppins-regular.woff2
            │   ├── 📄 roboto-bold.woff
            │   ├── 📄 roboto-bold.woff2
            │   ├── 📄 roboto-regular.woff
            │   └── 📄 roboto-regular.woff2
            │
            ├── 📂 js
            │   ├── 📄 all.min.js
            │   └── 📄 tailwind.js
            │
            └── 📂 webfonts
                ├── 📄 fa-brands-400.woff2
                ├── 📄 fa-regular-400.woff2
                ├── 📄 fa-solid-900.woff2
                └── 📄 fa-v4compatibility.woff2
```

---

## 🔧 Penggunaan

### Web Interface

1. Buka browser dan akses: `http://[IP_ADDRESS]/rakitanmanager`
3. Kelola modem dari dashboard visual

---

## 🐛 Troubleshooting

<details>
<summary><b>Modem tidak terdeteksi</b></summary>

- Pastikan modem terpasang dengan benar di port USB
- Restart service: `rakitanmanager restart`
- Periksa log: `/usr/share/rakitanmanager.log`

</details>

<details>
<summary><b>Web interface tidak dapat diakses</b></summary>

- Verifikasi PHP terinstall: `php -v`
- Cek web server status: `service httpd status`
- Pastikan firewall mengizinkan akses ke port 80/443

</details>

<details>
<summary><b>Permission denied errors</b></summary>

```bash
# Fix permissions
chmod +x /usr/share/rakitanmanager/.*
chmod -R 755 /www/rakitanmanager/
```

</details>

---

## 🤝 Kontribusi

Kami sangat terbuka untuk kontribusi dari komunitas! Berikut cara berkontribusi:

1. **Fork** repository ini
2. Buat **feature branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit** perubahan Anda (`git commit -m 'Add some AmazingFeature'`)
4. **Push** ke branch (`git push origin feature/AmazingFeature`)
5. Buka **Pull Request**

---

## 📜 Lisensi

Proyek ini dilisensikan di bawah **MIT License** - lihat file [LICENSE](LICENSE) untuk detail lengkap.

---

## 🌟 Acknowledgments

- Terima kasih kepada semua [contributors](https://github.com/rtaserver-wrt/RakitanManager-Reborn/graphs/contributors)
- Inspired by komunitas OpenWrt
- Built with ❤️ for embedded enthusiasts

---

<div align="center">

### 📞 Kontak & Support

[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github)](https://github.com/rtaserver-wrt/RakitanManager-Reborn)
[![Issues](https://img.shields.io/badge/Issues-Report%20Bug-red?style=for-the-badge&logo=github)](https://github.com/rtaserver-wrt/RakitanManager-Reborn/issues)
[![Discussions](https://img.shields.io/badge/Discussions-Join%20Chat-blue?style=for-the-badge&logo=github)](https://github.com/rtaserver-wrt/RakitanManager-Reborn/discussions)

**Dibuat dengan 💙 oleh [RTASERVER-WRT](https://github.com/rtaserver-wrt)**

⭐ Jika proyek ini membantu Anda, berikan **star** untuk mendukung pengembangan!

</div>
