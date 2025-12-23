## Nama : M. Fajar Sholehuddin Maulana Putra
# NIM : 202311420008

## 1. Utilitas Informasi Sistem

Menampilkan penggunaan disk:

```bash
df -h
```
<img width="661" height="252" alt="Screenshot 2025-12-23 201512" src="https://github.com/user-attachments/assets/e03abb4d-5faf-4a59-bd54-3da64dfdaf70" />

Menghitung ukuran direktori atau file:

```bash
du -sh <direktori>
```
<img width="321" height="52" alt="image" src="https://github.com/user-attachments/assets/b68d1677-0eb2-4c1b-8d50-d075a1086e70" />

Menampilkan penggunaan memori dan swap:

```bash
free -h
```
<img width="663" height="94" alt="image" src="https://github.com/user-attachments/assets/ce72e79b-9a18-46da-ad0e-72e8114a75ad" />

---

## 2. Utilitas Pencarian File

Mencari file `hosts` di direktori `/etc`:

```bash
find /etc -name "hosts"
```
<img width="439" height="141" alt="image" src="https://github.com/user-attachments/assets/8676c602-5774-44ca-b9fb-f6be107c7491" />

Menampilkan lokasi binary perintah:

```bash
which <command>
```
<img width="245" height="54" alt="image" src="https://github.com/user-attachments/assets/08681d43-0a1d-4849-bbda-f48e454aaff3" />

Menampilkan lokasi binary, source, dan manual:

```bash
whereis <command>
```
<img width="555" height="65" alt="image" src="https://github.com/user-attachments/assets/dc5a2955-df8c-48c3-bfa5-7854d68948b9" />

---
## 3. Utilitas Jaringan

Cek koneksi jaringan:

```bash
ping google.com
```
<img width="699" height="232" alt="image" src="https://github.com/user-attachments/assets/6d2b5dbd-89ee-419e-b06f-ff8b664f593c" />

Melihat port dan service aktif:

Alternatif netstat:

```bash
ss -tulnp
```
<img width="930" height="259" alt="image" src="https://github.com/user-attachments/assets/996b8bbb-410a-43d5-8d2f-dbd6920a9e54" />

Mengambil data dari URL:

```bash
curl https://example.com
```
<img width="819" height="212" alt="image" src="https://github.com/user-attachments/assets/011a068a-d8a8-42fd-8b64-38318d97ec62" />

---
