# Praktikum6
## Nama : Sovy Aprianti
## NIM : 312410344
## Kelas : TI.24.A4
## Mata Kuliah : Bahasa Pemrograman 

# Latihan.py

![soal p6](https://github.com/user-attachments/assets/0b6eb638-1bfb-4078-b8e2-6590129eccec)

 
# daftar kontak.py
  
  
  ```python
kontak = {
    "Ari": "081267888",
    "Dina": "087677776"
}

print(f"Kontak Ari: {kontak['Ari']}")

kontak["Riko"] = "087654544"

kontak["Dina"] = "088999776"

print("Semua Nama:")
for nama in kontak:
    print(nama)

print("Semua Nomor:")
for nomor in kontak.values():
    print(nomor)

print("Daftar Nama dan Nomor:")
for nama, nomor in kontak.items():
    print(f"{nama}: {nomor}")

del kontak["Dina"]

print("Daftar Kontak setelah menghapus Dina:")
for nama, nomor in kontak.items():
    print(f"{nama}: {nomor}")
```   






        



