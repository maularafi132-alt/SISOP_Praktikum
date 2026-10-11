# SISOP_Praktikum
Laporan Praktikum
# Laporan Praktikum Sistem Operasi

## Modul 1, 2, dan 3: Instalasi, Arsitektur, dan Eksplorasi Xinu OS

### Identitas Praktikan

| Item | Keterangan |
| :--- | :--- |
| **Nama** | Rafi Maula Witjaksono |
| **NIM** | 108072500141 |
| **Kelas** | IF 05 04 |
| **Asisten Praktikum** | Nuevalen Refitra Alswando & Giriputra Galang |
| **Tanggal Praktikum** | Jumat 9 Oktober 2026 |

## 1. Tujuan Praktikum

1. Memahami aturan, tata tertib, dan persiapan *tools* utama praktikum Sistem Operasi (VirtualBox, Ubuntu, Xinu OS, dan Sourcetrail).
2. Memahami arsitektur *cross-development* pada sistem operasi *embedded* Xinu yang memisahkan *Development-System VM* dan *Backend VM*.
3. Mampu melakukan kompilasi *source code* Xinu dan menjalankannya pada *target machine* melalui jaringan (PXE/TFTP).
4. Mampu mengakses dan mengeksplorasi perintah dasar *shell* Xinu menggunakan koneksi *serial port* (Minicom).

---

## 2. Dasar Teori & Arsitektur Sistem
Xinu OS adalah sistem operasi kecil yang dikhususkan untuk lingkungan *embedded*. Pengembangannya menggunakan paradigma **cross-development**, di mana programmer menggunakan komputer standar (*host/development-system*) untuk menulis dan mengompilasi kode, lalu mengunggah *image* OS tersebut ke komputer target (*backend*) untuk dijalankan.

Pada praktikum ini, arsitektur yang digunakan terdiri dari dua *Virtual Machine* (VM):

1. **Development-System VM**: Berisi OS Debian Linux, *source code* Xinu, *compiler*, DHCP Server, dan TFTP Server.
2. **Backend VM**: Komputer target kosong yang akan melakukan *booting* melalui jaringan (PXE), mengambil *image* Xinu dari TFTP server, dan menjalankan Xinu OS. Kedua VM ini dihubungkan melalui *Virtual Serial Port* agar praktikan dapat memberikan perintah ke Xinu dari terminal Development-System.

## 3. Langkah Kerja dan Hasil Eksplorasi

### 3.1 Login dan Kompilasi Source Code Xinu

Langkah pertama dilakukan pada **Development-System VM**. VM dijalankan dan dilakukan *login* ke dalam sistem operasi Debian.

* **Username:** `xinu`
* **Password:** `xinurocks`

Setelah masuk ke terminal, praktikan berpindah ke direktori kompilasi Xinu dan membersihkan *build* sebelumnya agar memastikan *image* yang dikompilasi adalah yang terbaru.

Setelah masuk ke terminal, praktikan berpindah ke direktori kompilasi Xinu dan membersihkan *build* sebelumnya agar memastikan *image* yang dikompilasi adalah yang terbaru.

```bash
$ cd xinu/compile
$ make clean
$ make
<img width="610" height="563" alt="image" src="https://github.com/user-attachments/assets/8127dd42-9fde-4b3d-9977-d0b5647e77ce" />
<img width="269" height="161" alt="image" src="https://github.com/user-attachments/assets/fc25fda8-ba47-4b16-8ebb-4e326e3db09b" />
<img width="566" height="439" alt="image" src="https://github.com/user-attachments/assets/c398d1eb-786e-4001-9681-015a28136ba3" />
<img width="566" height="173" alt="image" src="https://github.com/user-attachments/assets/20c46e0f-851c-417f-b71d-1a1e25aff771" />

**Hasil :** Proses hasil menggunakan 'make' Akan membuat seluruh nya source code nya compile C menjadi 'Xinu.elf' terus sistem dapat membaca otomatis menyalin image ke direktori server TFTP 

<img width="610" height="563" alt="image" src="https://github.com/user-attachments/assets/8127dd42-9fde-4b3d-9977-d0b5647e77ce" />
<img width="269" height="161" alt="image" src="https://github.com/user-attachments/assets/fc25fda8-ba47-4b16-8ebb-4e326e3db09b" />
<img width="566" height="439" alt="image" src="https://github.com/user-attachments/assets/c398d1eb-786e-4001-9681-015a28136ba3" />
<img width="566" height="173" alt="image" src="https://github.com/user-attachments/assets/20c46e0f-851c-417f-b71d-1a1e25aff771" />







