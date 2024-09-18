# WRITE UP PRAKTIKUM MODUL 01 ETHICAL HACKING
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


