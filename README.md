# DatabaseRentalMobil

|**Nama**|**NIM**|**Kelas**|**Matkul**|
|----|---|-----|------|
|ALIYAH ASMARANI|312210203|TI.22.A2|Basis Data|
|ALIFIA ANANDA PUTRI|312210168|TI.22.A2|Basis Data|
|INAYATUS SHOLEKHAWATI|312210200|TI.22.A2|Basis Data|
|FEBRIYANI NURHIDA|312210222|TI.22.A2|Basis Data|
|SAHRUL RIDWANSYAH|312210063|TI.22.A2|Basis Data|


## DAFTAR ISI <br>
| No | Description | Link |
|-----|------|-----|
|1|Perintah|[Click Here](#perintah)|
|2|ER-D Rental Mobil|[Click Here](#er-d-rental-mobil)|
|3|DDL Rental Mobil|[Click Here](#ddl-rental-mobil)|
|4|SQL CURD Rental Mobil|[Click Here](#sql-curd-rental-mobil)|
|5|SQL Join Rental Mobil|[Click Here](#sql-join-rental-mobil)|
|6|Presentasi (Link Youtube)|[Click Here](https://youtu.be/zhFQsQt_oRs)|

# PERINTAH
![image](https://github.com/AnggitaRisqiNC/Rental-Mobil/blob/main/screenshot/Perintah%20Soal.png)

# ERD 
![tugas kelompok rental mobil drawio](https://github.com/Aliyahasmarani/rental_mobilgadungan/assets/115197672/8451e3cd-5ded-4cdf-baaa-f0396a9f88ca)

> #### *Penjelasan*
> * Entitas **Kendaraan** memiliki atribut id_kendaraan (sebagai PRIMARY KEY), merk, warna, harga_sewa, dan status_kendaraan.
>
> * Entitas **Sopir** memiliki atribut id_sopir (sebagai PRIMARY KEY), id_kendaraan (sebagai FOREIGN KEY), nama_sopir, dan status_sopir.
>
> * Entitas **Customer** memiliki atribut id_customer (sebagai PRIMARY KEY), nama_customer, no_hp, dan email.
>
> * Entitas **Transaksi** memiliki atribut id_transaksi (sebagai PRIMARY KEY), id_kendaraan (sebagai FOREIGN KEY), id_sopir (sebagai FOREIGN KEY), id_customer (sebagai FOREIGN KEY), tgl_sewa, tgl_kembali, total_harga, tgl_pembayaran, metode_pembayaran, status_transaksi.

> #### *Kardinalitas*
> 1. Relasi one-to-one antara entitas **Kendaraan** dengan entitas **transaksi**.
>
> 2. Relasi one-to-many antara entitas **Sopir** dengan entitas **Transaksi**.
>
> 3. Relasi one-to-many antara entitas **Customer** dengan entitas **Transaksi**.



