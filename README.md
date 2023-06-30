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


### DDL Rental Mobil
#### 1. Membuat Database
```sql
CREATE DATABASE RentalMobil;
```
> Untuk membuat database gunakan perintah: `CREATE DATABASE [nama_database];`.

#### 2. Masuk ke dalam database menggunakan perintah USE
```sql
USE rentalmobil;
```
> Perintah `USE`, digunakan untuk masuk kedalam database, atau
berganti ke database lain.

#### 3. Membuat Tabel
```sql
CREATE TABLE customer (
    id_customer VARCHAR (10) PRIMARY KEY,
    nama_cs VARCHAR (45),
    no_hp INT (15),
    alamat VARCHAR (45),
    email VARCHAR (45));

CREATE TABLE sopir (
    id_sopir VARCHAR (10) PRIMARY KEY,
    id_kendaraan VARCHAR (10),
    nama_sp VARCHAR (45),
    status_sp ENUM ('TERSEDIA', 'TIDAK TERSEDIA') NOT NULL);

CREATE TABLE kendaraan (
    id_kendaraan VARCHAR (10) PRIMARY KEY,
    merk VARCHAR (45),
    warna VARCHAR (45),
    status_kdr ENUM ('TERSEDIA', 'TIDAK TERSEDIA') NOT NULL,
    harga_sewa INT);

CREATE TABLE transaksi (
    id_transaksi VARCHAR (10) PRIMARY KEY,
    id_customer VARCHAR (10),
    id_sopir VARCHAR (10),
    id_kendaraan VARCHAR (10),
    tgl_pembayaran DATE,
    tgl_sewa DATE,
    tgl_kembali DATE,
    status_transaksi VARCHAR (45),
    total_harga INT,
    metode_pembayaran VARCHAR (45));
```

> Sebelum membuat Tabel, pastikan database aktif yang digunakan dengan terlebih dahulu masuk kedalam databasenya, dengan perintah `USE`.
>
> Dalam script di atas, telah dibuat tabel-tabel sesuai dengan skema ERD yang telah disebutkan. Tabel-tabel tersebut antara lain: Kendaraan, Sopir, Customer, Transaksi, dan Laporan_Transaksi.
>
> Setiap tabel memiliki kolom-kolom yang sesuai dengan atribut-atribut yang terdapat dalam skema ERD, dan beberapa di antaranya memiliki tipe data yang sesuai seperti `VARCHAR`, `INT`, `ENUM`, dan `DATE`. Tabel-tabel tersebut juga saling memiliki relasi.


#### 5. Menampilkan Struktur Tabel
```sql
DESC Kendaraan;
DESC sopir;
DESC customer;
DESC transaksi;
```
![image](https://github.com/Aliyahasmarani/rental_mobilgadungan/assets/115197672/3c384364-bd03-472e-9109-814744b5854f)
