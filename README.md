![image](https://github.com/user-attachments/assets/ca51f12d-5f85-4779-b43d-649fd3c9642f)# WRITE UP PRAKTIKUM MODUL 01 ETHICAL HACKING
## Kelompok IT40
### Anggota Kelompok :
|             Nama              |     NRP    |
|-------------------------------|------------|
| Revalina Fairuzy Azhari Putri | 5027231001 |
| Kevin Anugerah Faza           | 5027231027 |

### Advance Sanity Check
Langkah pertama yaitu mendownload sanity.pcapng pada web dan masuk ke dalam IP yang tersedia pada question box section
![WhatsApp Image 2024-09-18 at 23 33 59_05e0f750](https://github.com/user-attachments/assets/e780e4f7-070e-4185-93a8-33b4e2e72907)

Lalu kita diminta untuk memasukkan username pada terminal, hal ini bisa didapati dengan melihat pada packets 85 dan melihat pada right bottom section
![WhatsApp Image 2024-09-18 at 23 36 04_30babebf](https://github.com/user-attachments/assets/8e730ebe-e12f-414a-a932-7da1d0a2d921)

Setelah itu kita diminta juga untuk memasukkan nama file yang dikirim dengan format penamaan seperti yang diberikan. Hal ini bisa didapat dari packets 85 juga, dan kita lihat pada nama pada file.name
![image](https://github.com/user-attachments/assets/83283238-5122-493a-80bd-0a505875d764)
![image](https://github.com/user-attachments/assets/58661f32-b58d-444e-b60b-0c35a85a74b4)

Setelah itu terdapat pesan kita diminta untuk mengikuti petunjuk untuk mendapatkan pesan rahasia. Petunjuk itu dapat kita temui dengan mencari pada salah satu packets yang ada, bertuliskan seperti gambar di bawah ini
![image](https://github.com/user-attachments/assets/7ea82ed7-eea5-4b94-963a-9e037ef9f82c)
disitu tertulis kita harus mengikuti peraturan pada soal shift. Disini saya membuka file soal shift yang ada pada https://jarkomprak2024.carrd.co/ dan menemukan hal ini
![image](https://github.com/user-attachments/assets/bf218b8b-2b19-4859-85fe-971092f2f55c)

dari code yang didapat tersebut, kita decode kata yang berwarna merah itu agar dia menjadi string. Karena format yang diminta adalah string. Setelah di decode menghasilkan kata "penword"
![image](https://github.com/user-attachments/assets/9339488e-d24c-4532-b973-63c66e2fd540)

Setelah dimasukkan, muncul flagnya
![image](https://github.com/user-attachments/assets/545639e2-c98a-413a-a29b-1c05dc1765b0)

flagnya adalah, JarkomIT{8uK4n_S4n1ty_b1a5A_cEuEzhKl6Gjd9qxpQizw3AAEOSu5PujqyAsJVJbnudESvOEhPp4mXIKK}

### Pegawai Negeri Sebelah
Kita masuk ke nc yang telah diberikan, dan diberikan pertanya tentang siapa yang memiliki password "nNnM%coQuF"
Metode mencari saya menggunakan fitur filter yang ada, dengan melihat protokol terbanyak pada packets yang ada, yang paling banyak adalah protokol TCP. Sehingga saya mencoba filter "tcp.stream eq" dengan angka dari 0 - 5 (sesuai yang tersediah pada references search bar nya) dan menemukan data para pns nya pada pengaturan filter tcp.stream eq 1. Setelah itu saya scroll di tiap packetsnya hingga menemukan orang yang memiliki password tersebut. Dan orang tersebut adalah Vero Tampubolon
![image](https://github.com/user-attachments/assets/811d9816-56c0-4a9d-976c-adaa59b2f963)

Lalu kita diminta untuk memasukkan jabatan dari Taufan Kuswandari, dari data yang ada beliau memiliki jabatan sebagai Analis Kebijakan. Kemudian ditanya list di nama paling atas, yaitu Cici Mustofa. Lalu juga ada pertanyaan password user paling akhir, yaitu Harjasa Suryatmi dengan password "RyxaJPv^yF"
![image](https://github.com/user-attachments/assets/342ac181-711e-4b88-97b8-d2743d9aa3ac)
![image](https://github.com/user-attachments/assets/3a2a39fc-7063-4ebb-a34f-c1df4782dea1)
![image](https://github.com/user-attachments/assets/b727392d-172c-445a-9596-acf5de32ef2a)

Setelah kita masukkan semua, flag telah ditemukan yaitu "flag-mu: JarkomIT{Tum8eN_p45SnYa_Ku4t_B1aS4Nya_kimJpa34YhWNGeYZnikzQzuapL3lFfJXYuOEhf65YYjDOcWAFQo8M4h}"
![image](https://github.com/user-attachments/assets/5e7d8cc5-68ce-4518-8825-b564d016de2f)

### FTP Login

Pertama kita masuk pada port nc yang telah disediakan. Lalu saat membuka file di wireshark, terlihat mayoritas packets dengan info tentang login ada di FTP, pada search langsung saja kita tulis ftp untuk memfilter, lalu kita pilih packets yang info nya login succesfull
![image](https://github.com/user-attachments/assets/26ddd5b0-66b7-44b8-bf9a-cf3473f8fffb)

Pada terminal kita ditanya usn yang berhasil digunakan ftp login, setelah kita analyze terlihat bahwa usn yang sukses untuk login adalah sn34ky. Setelah itu kita juga diminta untuk memasukkan password dari usn tersebut, yaitu sup3rsn1ff3r
![image](https://github.com/user-attachments/assets/4580b87c-40ae-4fc1-9a7a-d80d40f45851)

Setelah itu kita telah mendapatkan flag nya, yaitu JarkomIT{n0t_s0_s3cur3_ftp_OCPBE5WVpOGa7l4nQFeYfJ1nNL0nyFHu9cZmu59LKXaYnGhny8d9G1N}
![image](https://github.com/user-attachments/assets/8bc93abd-93d1-40a4-88f4-4e2a76466f4e)

###EZ

Pertama kita masuk ke IP yang telah tersedia pada soal, lalu pada terminal kita diminta untuk memasukkan jawaban dari log tersebut. Awalnya saya gapaham itu maksudnya apa, lalu saya iseng buat anaylze > follow > tcp di packets paling pertama sendiri, karena coba-coba siapa tahu dapet hint, dan akhirnya ternyata dapet. Disitu ada kata yang lumayan sus tulisannya "jawabannya jawaban", saya iseng masukin ternyata bener. Lalu kita ditanyain itu ada di port berapa, bisa kita cek di bagian left bottom section, disana tertera port nya yaitu "1234"
![image](https://github.com/user-attachments/assets/51d9dc45-b66c-4de5-a085-1f950397b722)
![image](https://github.com/user-attachments/assets/966d9b9c-9099-4b2b-9038-87c7234d09e0)

Setelah itu munculah flag nya, yaitu JarkomIT{BiAr_aman_Pake_sSh_OQxo9eKh1mEbBEy0lgBnVj5mM3zST4VbIhRbt6fi2zrXqEYwlFkiEZ}
![image](https://github.com/user-attachments/assets/cf00bd05-6e1e-4ed8-837f-0bf12f93a53b)

### Surprise






