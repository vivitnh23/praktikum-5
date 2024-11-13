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
# Inisialisasi list untuk menyimpan data
data_mahasiswa = []

# Fungsi untuk menghitung nilai akhir
def hitung_nilai_akhir(tugas, uts, uas):
    return round((tugas * 0.3) + (uts * 0.35) + (uas * 0.35), 2)

# Input data mahasiswa
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
