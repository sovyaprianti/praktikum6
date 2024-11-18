# Praktikum6
## Nama : Sovy Aprianti
## NIM : 312410344
## Kelas : TI.24.A4
## Mata Kuliah : Bahasa Pemrograman 

# Latihan.py

![soal p6](https://github.com/user-attachments/assets/0b6eb638-1bfb-4078-b8e2-6590129eccec)

 
### Dictionary untuk menyimpan data mahasiswa
mahasiswa = {}

### Fungsi untuk menghitung nilai akhir
def hitung_nilai_akhir(nilai_tugas, nilai_uts, nilai_uas):
    return (nilai_tugas * 0.30) + (nilai_uts * 0.35) + (nilai_uas * 0.35)

### Fungsi untuk menampilkan daftar nilai mahasiswa
def tampilkan_data():
    if mahasiswa:
        print("\nDaftar Nilai Mahasiswa:")
        print("="*55)
        print("| NO |  NIM  |   NAMA   | TUGAS | UTS | UAS |  AKHIR  |")
        print("="*55)
        for i, (nim, data) in enumerate(mahasiswa.items(), 1):
            print(f"| {i:<2} | {nim:<6} | {data['Nama']:<8} | {data['Tugas']:<5} | {data['UTS']:<3} | {data['UAS']:<3} | {data['Nilai Akhir']:<8.2f} |")
        print("="*55)
    else:
        print("TIDAK ADA DATA")

### Fungsi untuk menambah data mahasiswa
def tambah_data():
    nim = input("Masukkan NIM mahasiswa: ")
    nama = input("Masukkan nama mahasiswa: ")
    nilai_tugas = float(input("Masukkan nilai tugas: "))
    nilai_uts = float(input("Masukkan nilai UTS: "))
    nilai_uas = float(input("Masukkan nilai UAS: "))
    
    nilai_akhir = hitung_nilai_akhir(nilai_tugas, nilai_uts, nilai_uas)
    mahasiswa[nim] = {
        'Nama': nama,
        'Tugas': nilai_tugas,
        'UTS': nilai_uts,
        'UAS': nilai_uas,
        'Nilai Akhir': nilai_akhir
    }
    print(f"Data untuk {nama} (NIM: {nim}) telah ditambahkan.")

### Fungsi untuk mengubah data mahasiswa
def ubah_data():
    nim = input("Masukkan NIM mahasiswa yang akan diubah: ")
    if nim in mahasiswa:
        nama = mahasiswa[nim]['Nama']
        print(f"Mengubah data untuk {nama} (NIM: {nim})")
        nilai_tugas = float(input("Masukkan nilai tugas baru: "))
        nilai_uts = float(input("Masukkan nilai UTS baru: "))
        nilai_uas = float(input("Masukkan nilai UAS baru: "))
        
        nilai_akhir = hitung_nilai_akhir(nilai_tugas, nilai_uts, nilai_uas)
        mahasiswa[nim] = {
            'Nama': nama,
            'Tugas': nilai_tugas,
            'UTS': nilai_uts,
            'UAS': nilai_uas,
            'Nilai Akhir': nilai_akhir
        }
        print(f"Data untuk {nama} telah diubah.")
    else:
        print("NIM tidak ditemukan.")

### Fungsi untuk menghapus data mahasiswa
def hapus_data():
    nim = input("Masukkan NIM mahasiswa yang akan dihapus: ")
    if nim in mahasiswa:
        del mahasiswa[nim]
        print(f"Data untuk mahasiswa dengan NIM {nim} telah dihapus.")
    else:
        print("NIM tidak ditemukan.")

### Fungsi untuk mencari data mahasiswa berdasarkan NIM
def cari_data():
    nim = input("Masukkan NIM mahasiswa yang dicari: ")
    if nim in mahasiswa:
        data = mahasiswa[nim]
        print(f"{data['Nama']} (NIM: {nim}) - Tugas: {data['Tugas']}, UTS: {data['UTS']}, UAS: {data['UAS']}, Nilai Akhir: {data['Nilai Akhir']:.2f}")
    else:
        print("NIM tidak ditemukan.")

### Fungsi untuk menampilkan menu pilihan
def tampilkan_menu():
    print("\nMenu Pilihan:")
    print("(L)ihat Daftar Nilai")
    print("(T)ambah Data")
    print("(U)bah Data")
    print("(H)apus Data")
    print("(C)ari Data")
    print("(K)eluar")

### Program utama
while True:
    tampilkan_menu()
    pilihan = input("Pilih menu (L/T/U/H/C/K): ").upper()
    
    if pilihan == 'L':
        tampilkan_data()
    elif pilihan == 'T':
        tambah_data()
    elif pilihan == 'U':
        ubah_data()
    elif pilihan == 'H':
        hapus_data()
    elif pilihan == 'C':
        cari_data()
    elif pilihan == 'K':
        print("Terima kasih! Program selesai.")
        break
    else:
        print("Pilihan tidak valid. Silakan pilih antara L, T, U, H, C, atau K.")
        



