# WRITE UP PRAKTIKUM MODUL 01 KOMUNIKASI DATA DAN JARINGAN KOMPUTER
## Kelompok IT40
### Anggota Kelompok :
|             Nama              |     NRP    |
|-------------------------------|------------|
| Revalina Fairuzy Azhari Putri | 5027231001 |
| Kevin Anugerah Faza           | 5027231027 |

# Advance Sanity Check
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

# Pegawai Negeri Sebelah
Kita masuk ke nc yang telah diberikan, dan diberikan pertanya tentang siapa yang memiliki password "nNnM%coQuF"
Metode mencari saya menggunakan fitur filter yang ada, dengan melihat protokol terbanyak pada packets yang ada, yang paling banyak adalah protokol TCP. Sehingga saya mencoba filter "tcp.stream eq" dengan angka dari 0 - 5 (sesuai yang tersediah pada references search bar nya) dan menemukan data para pns nya pada pengaturan filter tcp.stream eq 1. Setelah itu saya scroll di tiap packetsnya hingga menemukan orang yang memiliki password tersebut. Dan orang tersebut adalah Vero Tampubolon
![image](https://github.com/user-attachments/assets/811d9816-56c0-4a9d-976c-adaa59b2f963)

Lalu kita diminta untuk memasukkan jabatan dari Taufan Kuswandari, dari data yang ada beliau memiliki jabatan sebagai Analis Kebijakan. Kemudian ditanya list di nama paling atas, yaitu Cici Mustofa. Lalu juga ada pertanyaan password user paling akhir, yaitu Harjasa Suryatmi dengan password "RyxaJPv^yF"
![image](https://github.com/user-attachments/assets/342ac181-711e-4b88-97b8-d2743d9aa3ac)
![image](https://github.com/user-attachments/assets/3a2a39fc-7063-4ebb-a34f-c1df4782dea1)
![image](https://github.com/user-attachments/assets/b727392d-172c-445a-9596-acf5de32ef2a)

Setelah kita masukkan semua, flag telah ditemukan yaitu "flag-mu: JarkomIT{Tum8eN_p45SnYa_Ku4t_B1aS4Nya_kimJpa34YhWNGeYZnikzQzuapL3lFfJXYuOEhf65YYjDOcWAFQo8M4h}"
![image](https://github.com/user-attachments/assets/5e7d8cc5-68ce-4518-8825-b564d016de2f)

# FTP Login

Pertama kita masuk pada port nc yang telah disediakan. Lalu saat membuka file di wireshark, terlihat mayoritas packets dengan info tentang login ada di FTP, pada search langsung saja kita tulis ftp untuk memfilter, lalu kita pilih packets yang info nya login succesfull
![image](https://github.com/user-attachments/assets/26ddd5b0-66b7-44b8-bf9a-cf3473f8fffb)

Pada terminal kita ditanya usn yang berhasil digunakan ftp login, setelah kita analyze terlihat bahwa usn yang sukses untuk login adalah sn34ky. Setelah itu kita juga diminta untuk memasukkan password dari usn tersebut, yaitu sup3rsn1ff3r
![image](https://github.com/user-attachments/assets/4580b87c-40ae-4fc1-9a7a-d80d40f45851)

Setelah itu kita telah mendapatkan flag nya, yaitu JarkomIT{n0t_s0_s3cur3_ftp_OCPBE5WVpOGa7l4nQFeYfJ1nNL0nyFHu9cZmu59LKXaYnGhny8d9G1N}
![image](https://github.com/user-attachments/assets/8bc93abd-93d1-40a4-88f4-4e2a76466f4e)

# EZ

Pertama kita masuk ke IP yang telah tersedia pada soal, lalu pada terminal kita diminta untuk memasukkan jawaban dari log tersebut. Awalnya saya gapaham itu maksudnya apa, lalu saya iseng buat anaylze > follow > tcp di packets paling pertama sendiri, karena coba-coba siapa tahu dapet hint, dan akhirnya ternyata dapet. Disitu ada kata yang lumayan sus tulisannya "jawabannya jawaban", saya iseng masukin ternyata bener. Lalu kita ditanyain itu ada di port berapa, bisa kita cek di bagian left bottom section, disana tertera port nya yaitu "1234"
![image](https://github.com/user-attachments/assets/51d9dc45-b66c-4de5-a085-1f950397b722)
![image](https://github.com/user-attachments/assets/966d9b9c-9099-4b2b-9038-87c7234d09e0)

Setelah itu munculah flag nya, yaitu JarkomIT{BiAr_aman_Pake_sSh_OQxo9eKh1mEbBEy0lgBnVj5mM3zST4VbIhRbt6fi2zrXqEYwlFkiEZ}
![image](https://github.com/user-attachments/assets/cf00bd05-6e1e-4ed8-837f-0bf12f93a53b)

# Surprise

Pertama kita masuk pada port nc yang disediakan, dan file nya menggunakan file yang sama seperti FTP Login. Setelah itu pada terminal muncul kita disuruh masuk ke servie yang digunakan pada FTP. Langkah awal tadi saya mencoba masuk ke packets yang sama seperti pada soal FTP Login sebelumnya. Setelah saya cari line ke-1 sepeti mempunyai format yang sama dengan yang diminta, saya coba masukkan dan ternyata benar. Lalu kita diminta untuk mengirim nama file yang dikirim oleh attacker. Saya coba cari masih di tempat yang sama, dan menemukan suatu kata dengan format. Saya coba masukkan dan ternyata berhasil. Setelah itu kita disuruh mencari pesan rahasia dari attacker. Saya mulai scroll dari atas hingga bawah dan menemukan suatu packets dengan status info yang sama dengan nama file yang tadi dimasukkan. Setelah saya lihat ada seperti code bahasa c++ lalu coba saya masukkan ke compiler, dan hasilnya ditemukan sesuatu. Lalu hal itu saya masukkan pada terminal dan ternyata benar.
![image](https://github.com/user-attachments/assets/b99a584a-e629-4a45-bd9c-862ebd1e6d46)
![image](https://github.com/user-attachments/assets/aca397fc-4255-4baf-a850-df580a6b3478)
![image](https://github.com/user-attachments/assets/3e593890-79d7-4400-80d5-5d8a4dbd3374)

Setelah itu didapatkan flagnya, yaitu JarkomIT{l1ttl3_m0us3_1n_th3_h0us3_IhONCrqxbE6Ke7OVwi5xojhDwG0Pm5i0iNeTFrW6UP5HhVEqGF9tTCHU}
![image](https://github.com/user-attachments/assets/7794a84a-2cef-418a-ab05-e2f121c097a4)

# Rizzset

Kita masuk sesuai port yang disediakan pada question section, dan muncul pada terminal ditanya nama domain. Saat pertama kali membuka wireshark, mata saya langsung ditujukan pada domain www.its.ac.id. Saya coba masukkan dan ternyata benar. Lalu kita ditanya port IP dari domain tersebut. Awalnya saya juga gatau, jadi saya saya coba satu satu aja port IP nya yang tertampil mulai dari 172.24.141.242 karena paling banyak dan lainnya. Sampai akhirnya benar pada port 103.94.189.5.
![image](https://github.com/user-attachments/assets/8fcd809d-b41f-45e5-b4cb-45bdcaf2d006)
![image](https://github.com/user-attachments/assets/7440fa56-64b2-4b45-88b6-330ff898c484)

Lalu pada terminal ditanya apa JARM Fingerprint yang dihasilkan domain. Awalnya saya juga gatau maksudnya apa, terus saya coba cari di google cara cari JARM, lalu diarahkan buat clone suatu repo dan membuka salah satu file.py nya. Disana saya mencoba mengikuti langkah-langkah nya, hingga akhirnya menemukan JARM nya, yaitu 2ad2ad16d2ad2ad22c2ad2ad2ad2ad74aaecca9f9c4a3303863dfee62b241e
![image](https://github.com/user-attachments/assets/868a8979-72c8-4ba1-b0e9-f2d8b38032bc)

Setelah itu tertampil flag nya, yaitu JarkomIT{Dn5_C0rR34t10n_aj8nQT92JcBYHlDYNRV5huoU7r1zZ0lpUdILyAtZ1yeF3f4A3giU7C1T5}
![image](https://github.com/user-attachments/assets/be33bf23-5fbe-4078-ae31-5eaefad7c468)

# Gajah Terbang (Server Recon)

Setelah masuk pada port IP yang tersedia, pada terminal muncul DBMS apa yang digunakan pada server. Awalnya saya gatau harus masukin apa, cuman setelah dilihat-lihat lagi ada yang namanya PGSQL itu dan dia ada banyak banget. Setelah saya coba cari ternyata dia juga merupakan salah satu jenis DBMS seperti MySQL, MariaDB, dan lainnya. Tetapi saat saya mengetik PGSQL, dia ternyata salah. Saat saya coba iseng masukkan PostgreSQL, yang mana merupakan kepanjangan dari PGSQL, ternyata benar. Lalu kita disuruh untuk memasukkan port nya PGSQL itu, disini saya juga coba satu-satu mulai dari 5432 dan lainnya, hingga akhirnya benar di port 6969. Setelah itu kita diminta untuk memasukkan OS apa yang digunakan pada server tersebut, saat iseng-iseng coba mencari sebelumnya, saya menemukan ada sebuah kata yaitu Debian dimana dia sangat sering sekali muncul di UDP. Setelah 1st try saya coba masukkan, ternyata benar. Setelahnya, kita disuruh untuk memasukkan credentials username DBMS valid yang digunakan. Saya juga awalnya gapaham kredensial yang bagaimana, tapi setelahnya saya coba-coba semua yang ada pada packets yang memuat info-info user, saya menemukan jawabannya di "s1gm4". Setelah itu saat selanjutnya disuruh memasukkan nama databasenya, juga berawal dari coba-coba hingga akhirnya benar pada "sigmaskibidigyatrizzzz. Saat ditanya berikutnya nama user, saya menjawab"4" karena disana tertampil 4 nama info user dari jojo, kevin, siska, kunto aji. Saat ditanya email admin, pada packets tertera informasi admin adalah jojo, jadi saya masukkan email jojo. Dan saat diminta password, saya menhashing code dari jojo selaku admin, karena waktu di decode gabisa dan format maunya string. 
![image](https://github.com/user-attachments/assets/1a00b129-00ad-4437-a27f-d24ca39892ea)
![image](https://github.com/user-attachments/assets/a384657e-f03f-47ce-8cba-ee1b606b1ab7)
![image](https://github.com/user-attachments/assets/5b3cf790-3ac8-4684-a53d-b272f0798126)
![image](https://github.com/user-attachments/assets/5d5cd229-754c-437a-8a42-5a537294c775)

Dan munculah flag, yaitu JarkomIT{Gy4tT_M5g_4U_LBuvgaosrMezITmL5dAvR8L535k1woCEvE2mc05OfNGbB8nANxCKsBiD1}
![image](https://github.com/user-attachments/assets/513130d1-673c-4bce-b91f-d3e2361ecf11)

# Gajah Terbang (Attacker Recon)

Setelah memasukkan port IP nc sesuai yang ada pada soal, dan menggunakan file yang sama seperti soal Gajah Terbang yang lalu, kita mendapat pertanyaan di terminal tentang email akun penyerang. Awalnya saya gatau mana yang attacker, lalu saya coba satu-satu dan berhasil di kunto aji. Lalu untuk password penyerangnya saya juga meng-hashing password kunto seperti pada step soal sebelumnya dan menemukan passwordnya adalah "kissme". Lalu ditanya tanggal banned, dan saya memasukkan 2024-06-09 dari info. Lalu ditanyakan tabel apa yang telah diubah penyerang, dan dari info yang didapat yang diubah adalah users dan banned_users. Setelah itu ditanyakan barang apa yang telah dibeli, saya coba langsung 1st try di rokok dan es krim akhirnya berhasil. Lalu ditanyakan total transaksi, saya menjumlahkan harga dari rokok dan es krim pada info data, dan didapat hasilnya adalah 18.000 + 6.500 yaitu 24.500 dan hasilnya benar. 

![image](https://github.com/user-attachments/assets/32d6651f-2dcb-4e4b-93af-a1fb80aaebb9)

Lalu muncullah flag nya yaitu JarkomIT{G4jaH_K0k_t3RbaNG_0DA7g5WyN4KciJaUVVo0ZN2DPYntwWJAyLDA4hWx3F5XVOReTg5FZKt5}
![image](https://github.com/user-attachments/assets/a9c91386-a1ae-4adb-b2f7-a4e47ed1b428)

# Illegal Breakthrough
- Langkah pertama langsung saja follow tcp stream yang paling atas sehingga ditemukan ip server nya.
![image](https://github.com/user-attachments/assets/d694ad4a-c11b-4275-b50d-9f48812fcabc)
- Langkah kedua adalah dengan memperhatikan line host pada hal yang sama
![image](https://github.com/user-attachments/assets/15c9523b-e2ce-4fc3-97f6-467f0811627e)
- Langkah selanjutnya dengan memperhatikan endpoint /ww1.php pada gambar di langkah pertama pada akhir host
- jawabannya adalah dengan menyingkat User-Agent menjadi ffuf-v2.1.0-dev
- Kemudian cari yang memiliki kredensial dengan tidak memiliki keterangan "salah" (cari 1 1 dengan stream 1917)
![image](https://github.com/user-attachments/assets/a4fb9f9e-5d86-43c9-8676-c07ce526dc13)
Flag ditemukan!
![image](https://github.com/user-attachments/assets/bf21d273-1889-48df-83e6-145265f7efac)


# Packets Barrage
- Langsung ditemukan dengan memasukkan ip address yang ada pada source wireshark paling atas
- Menggunakan filter "http contains "404"" untuk menemukan fail nya berapa kemudian ditambah 1 untuk bagian suksesnya (somehow it works)
![image](https://github.com/user-attachments/assets/42392916-4809-4bed-97e6-3382338f187c)
- Kemudian pilih file di wireshark -> export object -> HTTP -> dan slide kepaling bawah hingga menemukan download dan Regev.zip
![image](https://github.com/user-attachments/assets/539371c0-8ec4-43a6-8bf2-7f9b0057684d)
Lakukan save dan kemudian extract filenya untuk kemudian menemukan file bernama Albatros.txt
- Copy isi file Albatros.txt
![image](https://github.com/user-attachments/assets/8b06a0c8-3eab-4c43-ab59-b3258ac941f6)


# Corporate Breach
- Langkah pertama adalah dengan langsung membuka stream paling awal sehingga ditemukan nama pelaku
- Bruteforce dan cari stream 207 untuk menemukan kredensial yang dibutuhkan
![image](https://github.com/user-attachments/assets/fce48d4b-4f81-4107-ba0f-becd206edaae)


# Malicious Code
- Langkah pertama dengan melakukan filter http contains "GET" dan tulis jumlah displayed nya
- lakukan filterisasi "jarkom" karena pada soal sebelumnya telah ditemukan
![image](https://github.com/user-attachments/assets/7014f39d-5fca-45f4-b635-802c5d0abcd8
- Lakukan filterisasi frame contains "gmail.com"
![image](https://github.com/user-attachments/assets/8789fe87-a79c-4756-acbc-54f5042fa9b8)
kurangi jumlah displayed dengan 10 (karena 10 dari bawah sukses)
- Bruteforce ke stream 221, kemudian search ASCII translator untuk diartikan menggunakan web dcode.fr
- Kenali MAS AJI.
![image](https://github.com/user-attachments/assets/fd823458-1fd4-4170-b08f-18eaad46de9a)

# InneRCE
- Temukan idzoyyshell.php pada stream 27 kemudian jamnya ditambah 7
- Bruteforce hingga stream 55 (menemukan server-app)
- idzoyyshell.php
- Ada pada stream 49 bakuls, perhatikan line whoami paling atas
- Bruteforce hingga stream 52 terus copas line %20(bagian yang harus dicopas)%20 dan decode dengan base 64
- ![image](https://github.com/user-attachments/assets/ba8f190c-2f43-42f2-85e4-a7b1ac8738e4)
- Done
![image](https://github.com/user-attachments/assets/27d07fcf-66c8-448e-b46e-4bed01a975a4)

# 22 Nightmare
- Cari tcp stream dan temukan langsung Sh1k4.jpg
- Export file dengan cara sebelumnya
- Lakukan extract
- ![image](https://github.com/user-attachments/assets/8a83d4e6-8a3a-49a7-8c1e-9df65d947387)
- filter dengan frame contains "noko.py" (karena sempat terlihat pada saat download)
- Buka file py, copas binernya, masukkan ke decryptor pakai kunci biner NUN yang diubah ke biner, dan langsung decrypt ke text
![image](https://github.com/user-attachments/assets/6ab98660-0d1f-40d3-9bb5-ad35c7328a09)


# Stegography
- Packets no. 10 mengindikasikan adanya sebuah file PNG yang dikirimkan
- Lakukan extract objects based on FTP-DATA, disana akan terdapat banyak sekali .png yang tersedia, lakukan save all dan simpan pada 1 folder khusus images untuk memudahkan step selanjutnya
- Lakukan modifikasi pada reverse.py untuk menemukan pesan yang ada
```
import os

from glob import glob

from PIL import Image



def decode_image_reversed(image_path):

    img = Image.open(image_path)

    img = img.convert("RGB")

    pixels = img.load()



    binary_message = ""

    for i in range(img.width):

        for j in range(img.height):

            r, g, b = pixels[i, j]

            r_bin = format(r, '08b')

            binary_message += r_bin[-1]



    message = ""

    for i in range(0, len(binary_message), 8):

        byte = binary_message[i:i + 8]

        char = chr(int(byte, 2))

        

        if message.endswith("EOF"):

            break

        message += char



    message = message.replace("EOF", "")

    reversed_message = message[::-1]

    return reversed_message



folder_path = "/home/azrael/Downloads/14/images/"



png_files = glob(os.path.join(folder_path, "*.png"))



for png_file in png_files:

    decoded_message_reversed = decode_image_reversed(png_file)

    print(f"Pesan terbalik yang diambil dari {os.path.basename(png_file)}: {decoded_message_reversed}")
```
- Eksekusi dengan reverse.py dan ditemukan message "pahlawan keamanan siber" namun terbalik
![image](https://github.com/user-attachments/assets/477572de-3616-4b07-9cea-c3c1b394eef3)

![image](https://github.com/user-attachments/assets/c76a1f04-bf7f-472a-9388-6e4cf59b156d)

# Revisi

# Baby Hengker
- Langkah pertama buka streams yang berisi ```GET DESCRIPTOR``` untuk menemukan Arrival Time dari input pertama kali
![image](https://github.com/user-attachments/assets/14f0febc-a07f-4417-a184-dc64123788e9)
- Karena fokus kita adalah pada keystrok maka lakukan filter pada wireshark. Disini menggunakan filter
```((usb.transfer_type == 0x01) && (frame.len == 35))```
- Penggunaan length 35 dikarenakan terdapat informasi HID DATA pada setiap streams yang memiliki length 35
- Setelah lakukan filter, lakukan export packages tersebut kedalam file .csv
- Setelahnya gunakan command
```
cat innerchild.csv | cut -d "," -f 7 | cut -d '"' -f 2 | grep -vE "Leftover Capture Data" > innerchildhex.txt
```
untuk melakukan 

# Adult Hengker
- Langkah pertama mirip dengan soal Baby Hengker yakni dengan membuka file pcap dan buka pada line paling atas. Kemudian pada device descriptor akan terungkap jenis device apa yang tersambung pada USB
![image](https://github.com/user-attachments/assets/6b05b870-5018-469d-a3c9-649cc23496c1)
- Kemudian mungkin terjadi kesalahan pada soal sehingga format jawaban yang diminta soal berbeda dengan maksud soal itu sendiri. Namun dari format jawaban yang diminta yakni 
```
Apakah device yang digunakan oleh seorang mahasiswa tersebut?
Format: STRING .ex AKU INGIN JADI SEORANG BATMAN
```
Dapat disimpulkan bahwa yang diminta adalah apa yang dilakukan oleh mouse tersebut
- Menggunakan bantuan USBPcap Mouse Visualizer yang ada pada GitHub seseorang, kita dapat memvisualisasikan input mouse tersebut sehingga muncul pesan
![image](https://github.com/user-attachments/assets/4b82f3fa-3f2b-4ab0-b91e-553f80f3a85e)
```
HALO MAS KEVIN SALKEN
```
- Dan Flag telah ditemukan!
![image](https://github.com/user-attachments/assets/530605ab-8fce-4e8d-b53a-60c7e4a8c298)

# Simba

Pertama kita masukkan port IP yang ada pada soal di terminal, dan mendownload file yang ada. Pada soal pertama kita disuruh untuk mencari service apakah yang compromise? Langkah yang saya lakukan adalah dengan mengecek lewat section protocol yang ada. Setelah mencoba beberapa service seperti TCP, MDNS, dan ARP, jawaban yang benar adalah pada "SMB", karena termasuk yang paling banyak juga. Setelah itu kita disuruh untuk menyebutkan user yang compromise. Pada soal ini, saya mulai memfilter service untuk tertuju pada SMB, setelah itu saya scroll satu-satu packets yang ada hingga menemukan "mmeyers". Soal terakhir kita ditanya ada berapa file yang berhasil ter-leak dari hasil enumerasi protokol/service tersebut. Setelah mencoba banyak angka, kami menggunakan langkah Export Objects > SMB > menghitung banyaknya file yang tertampil, tetapi dengan mengesampingkan yang memiliki size 0 bytes. Dan hasilnya adalah 14
![image](https://github.com/user-attachments/assets/59081d9e-6751-4e15-8426-df082676e2a7)
![WhatsApp Image 2024-09-22 at 20 14 50_b33c34a7](https://github.com/user-attachments/assets/b4839745-853e-43da-8f69-b43462fb51ad)
![image](https://github.com/user-attachments/assets/00b36a94-ea87-436d-88f0-a9a26a859231)

Setelah itu tertampil hasil flag pada soal ini, yaitu JarkomIT{4PaK4h_M3nD1nG_p4K3_SFTP_qraXu2kUiSO1OMCxL8qtb6CA1AaXyif0BaygBwb5vNWn9dCWE6KgSMB}
![image](https://github.com/user-attachments/assets/c752f53c-5c98-497f-abe6-d2f7c405dfd0)

# Encrypted World
- Langkah oertama dapat dengan melakukan save pada file yang ada pada pcap dengan melakukan export objects via FTP-DATA
![image](https://github.com/user-attachments/assets/b5c13e43-0170-4607-abda-08019d63ab4f)
- Setelahnya lakukan decrypt AES yang ada pada AES.txt menggunakan hint yang ada pada pcap. Berdasarkan hint tersebut dapat diambil setiap huruf yang ada didepan setiap kata. Sehingga muncul key dan IV untuk AES nya
- Key
```
aof9ai78939riahofhfiasfiayaiapsg
```
- IV
```
kbalfahwrsiabisg
```
- Ketika keduanya dimasukkan akan memunculkan password untuk c1pher.rar yakni `jarkomasik`
- setelahnya akan muncul 3 folder berbeda dan  masing-masing akan memiliki 10 file txt. Hint nya terdapat pada soal yakni pada bagian DES, AES, dan Base64
- Ketika menggunakan AI untuk menemukan enkripsinya, terlihat bahwa enkripsinya berupa Base64. Oleh karena itu maka diformulasikanlah sebuah python script untuk memecahkannya
```
import os
import base64

# Set the base directory where the folders are located
base_directory = '/home/azrael/Documents/chall13'

def correct_base64_padding(data):
    # Pad the Base64 string with '=' if necessary
    missing_padding = len(data) % 4
    if missing_padding:
        data += '=' * (4 - missing_padding)
    return data

def decode_base64(data):
    try:
        data = correct_base64_padding(data)
        decoded_data = base64.b64decode(data).decode('utf-8')
        return decoded_data
    except UnicodeDecodeError as ue:
        return f"Non-UTF-8 data or invalid Base64 content detected: {ue}"
    except Exception as e:
        return f"Base64 decoding failed: {e}"

def decode_file(file_path):
    try:
        with open(file_path, 'r') as f:
            file_content = f.read().strip()

            # Attempt base64 decoding with corrected padding
            decoded = decode_base64(file_content)
            return f"Decoded (Base64): {decoded}\n"
    except Exception as e:
        return f"Error processing {file_path}: {e}\n"

def process_all_files_in_folders(base_directory):
    # List of folders to process
    folders = ["UGVydGFueWFhbiAx", "UGVydGFueWFhbiAy", "UGVydGFueWFhbiAz"]

    for folder in folders:
        folder_path = os.path.join(base_directory, folder)
        print(f"\nProcessing folder: {folder}\n")
        
        for filename in sorted(os.listdir(folder_path)):
            if filename.endswith('.txt'):
                file_path = os.path.join(folder_path, filename)
                print(f"{filename} = ", end="")
                result = decode_file(file_path)
                print(result)

# Start processing all files in all folders
process_all_files_in_folders(base_directory)
```
- Hasil dari code tersebut sebagai berikut
![image](https://github.com/user-attachments/assets/21ffabf5-61f1-49d2-95ad-08e9858d9fc9)
- Berdasarkan berbagai clue tersebut maka jawab pertanyaannya dan flag akan ditemukan.
![image](https://github.com/user-attachments/assets/2bd0fb2f-69ab-45c5-9fab-3902dd71948e)

# Netware
- Terlihat bahwa file pcap memiliki protocol TLS. Pada file soal ketika diextract terdapat 2 file yang berisi .txt dan .pcap
- Masuk ke bagian edit -> preferences -> pilih protocol TLS
- Kemudian masukkan txt tadi pada (Pre)-Master-Secret log filename
![image](https://github.com/user-attachments/assets/e15dce33-ff5f-4f82-8c2a-3b93fb604b67)
- Setelahnya terlihat bahwa terdapat beberapa protocol HTTP. Dari situ karena yang diminta soal ialah filename dan extension maka bisa melakukan export objects based on HTTP (invest_20.dll merupakan file yang diminta)
- Kemudian diminta untuk menemukan SHA-256 hash sehingga dapat gunakan command berikut untuk mengetahuinya
![image](https://github.com/user-attachments/assets/4beb5ea4-c272-42de-a366-9792f0d89f7d)
- And the practicum is Done!
![image](https://github.com/user-attachments/assets/b8cf0365-1702-442c-bfb0-81b31b9f7ec2)
(playing Love In The Dark - Adele)
