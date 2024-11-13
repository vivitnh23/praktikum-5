# Program Penghitung Nilai Akhir Mahasiswa
Program ini untuk menghitung nilai akhir mahasiswa berdasarkan bobot nilai tugas, UTS, dan UAS yang telah ditentukan. Program ini juga menampilkan data mahasiswa dalam bentuk tabel.

# Deskripsi Program
Program ini dibuat menggunakan bahasa python dengan fitur:
-List dan Dictionary untuk penyimpanan data.
-Fungsi Kustom (def) untuk perhitungan nilai akhir.
-input() dan int() untuk input dan konversi data.
-while dan if untuk kontrol alur.
-append() dan break untuk menambah data ke list dan menghentikan perulangan.
-print() dan F-string untuk mencetak hasil dalam bentuk tabel yang terformat.

## Flowchart
![Flowchart](https://github.com/vivitnh23/praktikum-5/blob/main/flowchart%20nilai%20akhir%20mahasiswa.png?raw=true)

## Kode Program 
```python
data_mahasiswa = []

def hitung_nilai_akhir(tugas, uts, uas):
    return round((tugas * 0.3) + (uts * 0.35) + (uas * 0.35), 2)

while True:
    nama = input("Nama: ")
    nim = input("NIM: ")
    tugas = int(input("Nilai Tugas: "))
    uts = int(input("Nilai UTS: "))
    uas = int(input("Nilai UAS: "))
    nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)

    # Simpan data ke dalam dictionary
    data_mahasiswa.append({
        "Nama": nama,
        "NIM": nim,
        "Tugas": tugas,
        "UTS": uts,
        "UAS": uas,
        "Akhir": nilai_akhir
    })
    
    tambah = input("Tambah data (y/t)? ")
    if tambah.lower() != 'y':
        break

print("\n| No | Nama     | NIM   | Tugas | UTS | UAS | Akhir |")
print("-" * 50)
for i, mhs in enumerate(data_mahasiswa, start=1):
    print(f"| {i:<2} | {mhs['Nama']:<8} | {mhs['NIM']:<5} | {mhs['Tugas']:<5} | {mhs['UTS']:<3} | {mhs['UAS']:<3} | {mhs['Akhir']:<5} |")
```

## Output Program 
````
Nama: vivit nurul hidayah
NIM: 312410110 
Nilai Tugas: 90
Nilai UTS: 98
Nilai UAS: 95
Tambah data (y/t)? y
Nama: Fitri ramadhani
NIM: 312410085
Nilai Tugas: 100
Nilai UTS: 90
Nilai UAS: 95
Tambah data (y/t)? y
Nama: dwi okta 
NIM: 312410056
Nilai Tugas: 90
Nilai UTS: 95
Nilai UAS: 99
Tambah data (y/t)? y
Nama: friska pebriana
NIM: 312410160
Nilai Tugas: 95
Nilai UTS: 90
Nilai UAS: 97
Tambah data (y/t)? t

| No | Nama     | NIM   | Tugas | UTS | UAS | Akhir |
--------------------------------------------------
| 1  | vivit nurul hidayah | 312410110 | 90    | 98  | 95  | 94.55 |
| 2  | Fitri ramadhani | 312410085 | 100   | 90  | 95  | 94.75 |
| 3  | dwi okta  | 312410056 | 90    | 95  | 99  | 94.9  |
| 4  | friska pebriana | 312410160 | 95    | 90  | 97  | 93.95 |
````

# Cara Kerja Program 
1. Program pertama kali menginisialisasi list kosong bernama data_mahasiswa untuk menyimpan data setiap mahasiswa.
2. Fungsi hitung_nilai_akhir digunakan untuk menghitung nilai akhir berdasarkan formula:
   \[
   \text{nilai akhir} = (\text{nilai tugas} \times 0.3) + (\text{nilai UTS} \times 0.35) + (\text{nilai UAS} \times 0.35)
   \]
3. Program meminta pengguna untuk memasukkan data nama, NIM, nilai tugas, UTS, dan UAS.
4. Setelah nilai akhir dihitung menggunakan fungsi hitung_nilai_akhir, semua data tersebut disimpan dalam dictionary dan ditambahkan ke dalam list data_mahasiswa.
5. Pengguna dapat memilih untuk menambahkan data mahasiswa lain atau mengakhiri proses input.
6. Setelah input selesai, program akan mencetak data mahasiswa dalam bentuk tabel dengan kolom nomor, nama, NIM, nilai tugas, UTS, UAS, dan nilai
