## 🧠 Dasar Teori

Cron adalah layanan penjadwalan otomatis pada Linux.
Crontab adalah tabel konfigurasi perintah yang dijalankan cron.

Format crontab:

```
* * * * * perintah
| | | | |
| | | | └─ Hari (0–7)
| | | └── Bulan (1–12)
| | └─── Tanggal (1–31)
| └──── Jam (0–23)
└────── Menit (0–59)
```

---

## 1. Mengecek & Mengaktifkan Cron

Cek status cron:

```bash
sudo systemctl status cron
```

Menjalankan cron:

```bash
sudo systemctl start cron
```

Mengaktifkan cron saat boot:

```bash
sudo systemctl enable cron
```

---

## 2. Mengedit Crontab

Edit crontab user:

```bash
crontab -e
```

Melihat cronjob yang aktif:

```bash
crontab -l
```

Menghapus seluruh cronjob:

```bash
crontab -r
```

---

## 3. Contoh Cronjob Langsung

Menjalankan perintah setiap menit (log percobaan):

```bash
* * * * * echo "Percobaan cron" >> /home/user/cron.log
```

Update jam setiap 1 menit:

```bash
*/1 * * * * date >> /home/user/jam.log
```

Restart service SSH setiap 3 menit (butuh sudo):

```bash
*/3 * * * * sudo systemctl restart ssh
```

---

## 4. Menjalankan Script `.sh` Melalui Cron

### Backup Direktori dengan Script

Membuat folder backup:

```bash
mkdir /home/user/backup
```

Membuat file script:

```bash
nano /home/user/backup.sh
```

Isi script:

```bash
#!/bin/bash
tanggal=$(date +"%Y-%m-%d_%H-%M")
cp -r /home/user/pertemuan4 /home/user/backup/pertemuan4_$tanggal
echo "Backup selesai pada $tanggal" >> /home/user/backup/backup.log
```

Memberi izin eksekusi:

```bash
chmod +x /home/user/backup.sh
```

Menjadwalkan cronjob tiap jam:

```bash
0 * * * * /home/user/backup.sh
```

---

### Redirect Output Cron

Menyimpan output dan error:

```bash
*/2 * * * * /home/user/backup.sh >> /home/user/backup/cron_output.log 2>&1
```

---

## 5. Menampilkan Informasi Sistem dengan Script

Membuat script info sistem:

```bash
nano /home/user/info.sh
```

Isi script:

```bash
#!/bin/bash
echo "Informasi sistem pada: $(date)" >> /home/user/sistem/sistem.log
df -h >> /home/user/sistem/sistem.log
```

Beri izin dan buat folder:

```bash
chmod +x /home/user/info.sh
mkdir /home/user/sistem
```

Jalankan via cron:

```bash
*/3 * * * * /home/user/info.sh
```

Cek hasil log:

```bash
cat /home/user/sistem/sistem.log
```

---

## 6. Troubleshooting Cron

Mengecek log cron:

```bash
grep CRON /var/log/syslog
```

---

