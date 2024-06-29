# Tugas Praktikum { Pertemuan ke 15 }

|**Nama**|**NIM**|**Kelas**|**Matkul**|
|----|---|-----|------|
|Muhammad Arif Mulyanto|312310359|TI.23.A.5|Basis Data|

# Soal latihan praktikum 7

### 1. Tampilkan data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Dika

```
SELECT nik, nama, id_dept FROM Karyawan WHERE id_dept = (SELECT id_dept FROM Karyawan WHERE nama = 'Dika');
```
**Output :**

![tugas 7 1](https://github.com/MuhArifyanto/MYSQL7/assets/147913440/daf80bfd-c5e9-466c-8cb2-06779e88508d)

### 2. Tampilkan data karyawan yang gajinya lebih besar dari rata-rata gaji semua karyawan. Urutkan menurun berdasarkan besaran gaji

```
SELECT nik, nama FROM Karyawan WHERE id_dept IN (SELECT id_dept FROM Karyawan WHERE nama LIKE '%K%');
```

**Output :**

![tugas 7 2](https://github.com/MuhArifyanto/MYSQL7/assets/147913440/eb53928b-5885-4a3e-b627-97032b5e2902)

### 3. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di departmen yang sama dengan karyawan dengan nama yang mengandung huruf 'K'.

```
SELECT nik, nama FROM Karyawan WHERE id_dept IN (SELECT id_dept FROM Karyawan WHERE nama LIKE '%K%');
```

**Output :**

![tugas 7 3](https://github.com/MuhArifyanto/MYSQL7/assets/147913440/154db17c-1f4f-4a6f-aeb3-db78a1b94de1)

### 4. Tampilkan data karyawan yang bekerja pada departemen yang ada di Kantor pusat.

```
SELECT karyawan.nik, karyawan.nama, karyawan.id_dept FROM karyawan JOIN departemen ON karyawan.id_dept = departemen.id_dept WHERE departemen.id_p = 'P01';
```

**Output :**

![tugas 7 4](https://github.com/MuhArifyanto/MYSQL7/assets/147913440/5e4f103f-d8c8-4d9f-865a-7e772d4dd521)


### 5. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di departmen yang sama dengan karyawan dengan nama yang mengandung huruf 'K' dan yang gajinya lebih besar dari rata-rata gaji semua karyawan

```
SELECT DISTINCT k1.nik, k1.nama FROM karyawan k1 JOIN karyawan k2 ON k1.id_dept = k2.id_dept WHERE k1.gaji_pokok > (SELECT AVG(gaji_pokok) FROM karyawan WHERE nama LIKE '%K%');
```

**Output :**

![tugas 7 5](https://github.com/MuhArifyanto/MYSQL7/assets/147913440/d6e288d0-e36b-4c42-8f47-d4490c2205f0)
