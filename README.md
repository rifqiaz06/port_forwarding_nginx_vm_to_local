Untuk melakukan port forwarding pada Nginx yang berjalan di VirtualBox ke komputer lokal, Anda perlu mengatur penerusan port di pengaturan VirtualBox. Ini akan memungkinkan Anda mengakses server web Nginx di mesin virtual melalui alamat IP komputer lokal Anda. 

# Berikut adalah langkah-langkahnya:
## 1. Buka Pengaturan Mesin Virtual: 
Buka VirtualBox Manager, Pilih mesin virtual yang menjalankan Nginx, Klik tombol "Settings". 
## 2. Konfigurasi Jaringan:
Pilih tab "Network", Pastikan adapter yang terhubung (Attached to) diatur ke "NAT".
## 3. Tambahkan Aturan Penerusan Port:
Klik tombol "Port Forwarding".
Klik ikon "Add new port forwarding rule" (ikon plus).

<img width="658" height="427" alt="Screenshot 2025-07-22 213941" src="https://github.com/user-attachments/assets/99524e44-e4f0-4c75-9a25-b9486d0550ef" />

<img width="658" height="190" alt="Screenshot 2025-07-23 003500" src="https://github.com/user-attachments/assets/504ac2c9-39ef-4a50-a2f4-78f0b0ccdf90" />

<img width="655" height="424" alt="Screenshot 2025-07-22 214733" src="https://github.com/user-attachments/assets/58783d6b-9201-48ad-a0ac-2780133f1402" />

### Isi aturan penerusan port sebagai berikut:
**Host IP:** Bisa diisi dengan `127.0.0.1` (untuk mengakses dari komputer lokal) atau dikosongkan jika ingin menyesuaikan dengan IP yang didapatkan dari DHCP host. 
**Host Port:** Pilih port yang akan digunakan untuk mengakses Nginx dari komputer lokal (misalnya, `8080`).
**Guest IP:** Masukkan alamat IP mesin virtual Anda (misalnya, `10.0.2.15` atau sesuai yang didapatkan dari VM). 
**Guest Port:** Masukkan port tempat Nginx berjalan di mesin virtual (biasanya `80` untuk HTTP atau `443` untuk HTTPS). 
Klik "OK" untuk menyimpan aturan. 

## 4. Mulai Mesin Virtual:
Pastikan mesin virtual sudah berjalan.
Buka browser di komputer lokal Anda.
Akses server Nginx dengan mengetikkan `http://127.0.0.1:8080` (atau port yang Anda pilih) di bilah alamat. 

### Penjelasan Tambahan:
**NAT (Network Address Translation)**: NAT adalah mode jaringan default di VirtualBox yang memungkinkan mesin virtual terhubung ke internet melalui host. Penerusan port adalah cara untuk mengakses layanan di dalam mesin virtual dari luar jaringan. 
**Host IP**: Alamat IP komputer Anda yang digunakan untuk mengakses mesin virtual. Jika dikosongkan, VirtualBox akan menggunakan alamat IP yang diberikan oleh DHCP. 
**Host Port**: Port pada komputer host yang akan meneruskan permintaan ke mesin virtual. 
**Guest IP**: Alamat IP mesin virtual Anda di dalam jaringan virtual. 
**Guest Port**: Port yang digunakan oleh server Nginx di dalam mesin virtual. 

Dengan mengikuti langkah-langkah di atas, Anda seharusnya sudah bisa mengakses server Nginx yang berjalan di VirtualBox dari komputer lokal Anda melalui port forwarding. 
