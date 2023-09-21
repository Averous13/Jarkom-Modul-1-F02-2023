# Jarkom-Modul-1-F02-2023
Laporan resmi praktikum jaringan komputer 2023

|NAMA|NRP|
|:--:|:-:|
|Moh Adib Syambudi|5025211017|
|Samuel Hamonangan Malau|5111940000206|

## SOAL 1
#### User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file
#### a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?
#### b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
#### c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
#### d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

Untuk mendapatkan informasi aktivitas yang sedang dilakukan yaitu Upload file. Kita menggunakan command dibawah ini
```
ftp.request.command == 'STOR'
```

protokol yang digunakan adalah ftp dimana fungsinya untuk transfer file salah satunya upload file. kemudian untuk commandnya adalah STOR. Berdasarkan hasil display filter kita mendapatkan packet yang sedang menggunggah file. Detail dari nilai sequence number dan acknowledge number ada pada wireshark 
\na.sequence number(raw): 258040667. 
\nb.acknowledge number(raw): 1044861039
\nResponse dari packet yang kita dapat berada pada baris paket berikutnya. Detail dari sequence number dan acknowledge number ada di paket tersebut
\nc.sequence number(raw): 1044861039
\nd. acknowledge number(raw) : 258040696

## SOAL 2
#### Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

Halaman Web diatur oleh protokol HTTP(Hypertext Transfer Protocol). Maka untuk mendapatkan detailnya, digunakan command http untuk mencari semua packet yang menggunakan http. Kemudian di dalamnya dicari server dari halaman portal praktikum Jaringan Komputer. Didapatkanlah gunicorn

## SOAL 3
#### Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut: 
#### a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
```
ip.dst == 239.255.255.250 || ip.src == 239.255.255.250 && udp.port == 3702
```

Filter display diatas menangkap packet yang berasal dan menuju 239.255.255.250 dengan port 3702. Maka didapatkan sebanyak 21 packet

#### b. Protokol layer transport apa yang digunakan?

Protokol yang digunakan adalah UDP berdasarkan uji coba pencarian dengan udp dan tcp pada filter. 


