## CODING
```python
class DataMahasigma : 
    def __init__(self):
        self.DataMahasiswa = []
    
    def tambah(self, nama, nilai): 
        self.DataMahasiswa.append({"nama" : nama, "nilai": nilai})
        print(f'data {nama} berhasil di tambahkan')
        
    def tampilkan (self):
        if not self.DataMahasiswa:
            print("Data Tidak Di Temukan")
        else:
            print("Daftar Nilai Mahasiswa")
            for i, mahasiswa in enumerate(self.DataMahasiswa, start= 1) :
                print(f"{i}. Nama: {mahasiswa['nama']}\n   Nilai: {mahasiswa['nilai']}")
                
    def hapus (self, nama):
        for mahasiswa in self.DataMahasiswa:
            if mahasiswa ['nama'] == nama:
                self.DataMahasiswa.remove(mahasiswa)
                print(f"Data {nama} Mahaiswa Berhasil Di Hapus")
                return
        print("Data Tidak Di Temukan")
    
    def ubah (self, nama, nilai_baru):
        for mahasiswa in self.DataMahasiswa:
            if mahasiswa ["nama"] == nama:
                mahasiswa ["nilai"] = nilai_baru
                print(f"Data {nama} Berhasil Di Ubah")
                return
            print("Data Tidak Di Temukan")
                
if __name__ == '__main__':
    data = DataMahasigma()
    
    while True:
        print("\n=====Menu Daftar Mahasiswa=====")
        print("1. Tambah Data")
        print("2. Tampilkan Data")
        print("3. Hapus Data")
        print("4. Ubah Data")  
        print("5. Keluar")
        
        try :
             pilihan = int(input("Masukan PIlihan (1-5): "))
        except ValueError:
            print("Masukkan angka yang valid!")
            continue

        if pilihan == 1:
            nama = input("Masukkan nama mahasiswa: ")
            try:
                nilai = float(input("Masukkan nilai mahasiswa: "))
                data.tambah(nama, nilai)
            except ValueError:
                print("Nilai harus berupa angka!")
                
        elif pilihan == 2:
            data.tampilkan()
            
        elif pilihan == 3:
            Nama = input("Masukan Nama Yang Ingin Di Hapus: ")
            data.hapus(Nama)
            
        elif pilihan == 4:
            Nama = input("Masukan Nama Mahasiswa Yang Ingin Di Ubah Nilainya: ")
            try:
                nilai_baru = input("Masukan Nilai Baru: ")
                data.ubah(Nama, nilai_baru)
            except ValueError:
                print("Nilai Harus Berupa Angka")
                
        elif pilihan == 5:
            print("Program telah Selesai, Terima Kasih")
            break 
        
        else:
            print("Pilihan Tidak Valid, Silakan Pilih Menu (1-5).")
```
## OUTPUT
````markdown
=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 1
Masukkan nama mahasiswa: aldi rismandayana
Masukkan nilai mahasiswa: 89
data aldi rismandayana berhasil di tambahkan

=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 2
Daftar Nilai Mahasiswa
1. Nama: aldi rismandayana
   Nilai: 89.0

=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 4
Masukan Nama Mahasiswa Yang Ingin Di Ubah Nilainya: aldi rismandayana
Masukan Nilai Baru: 90
Data aldi rismandayana Berhasil Di Ubah

=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 2
Daftar Nilai Mahasiswa
1. Nama: aldi rismandayana
   Nilai: 90

=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 3
Masukan Nama Yang Ingin Di Hapus: aldi rismandayana
Data aldi rismandayana Mahaiswa Berhasil Di Hapus

=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 2
Data Tidak Di Temukan

=====Menu Daftar Mahasiswa=====
1. Tambah Data
2. Tampilkan Data
3. Hapus Data
4. Ubah Data
5. Keluar
Masukan PIlihan (1-5): 5
Program telah Selesai, Terima Kasih
````
## PENJELASAN
Penjelasan Program Utama:

- Class PersonManager Digunakan untuk mengelola data mahasiswa, seperti menambah, menampilkan, menghapus, atau mengubah data.
- Menu Interaktif: Program menyediakan menu untuk memilih operasi:
  1.  Tambah data mahasiswa.
  2.  Tampilkan semua data mahasiswa.
  3.  Hapus data mahasiswa berdasarkan nama.
  4.  Ubah nilai mahasiswa berdasarkan nama.
  5.  Keluar dari program.
- Validasi Input: Menggunakan try-except untuk menangani input yang tidak valid, seperti saat memasukkan nilai yang seharusnya berupa angka.
- Pengulangan Program: Menggunakan while True agar program terus berjalan sampai pengguna memilih opsi untuk keluar.
