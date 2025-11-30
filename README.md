# pratikum-7
# List untuk menyimpan data mahasiswa
data_mahasiswa = []

def tambah():
    nama = input("Masukkan nama mahasiswa: ")
    nilai = float(input("Masukkan nilai: "))
    data_mahasiswa.append({"nama": nama, "nilai": nilai})
    print("Data berhasil ditambahkan!\n")

def tampilkan():
    if not data_mahasiswa:
        print("Belum ada data.\n")
        return
  print("=== Daftar Nilai Mahasiswa ===")
    for mhs in data_mahasiswa:
        print(f"Nama : {mhs['nama']} | Nilai : {mhs['nilai']}")
    print()

def hapus(nama):
    for mhs in data_mahasiswa:
        if mhs['nama'].lower() == nama.lower():
            data_mahasiswa.remove(mhs)
            print("Data berhasil dihapus!\n")
            return
    print("Data tidak ditemukan.\n")

def ubah(nama):
    for mhs in data_mahasiswa:
        if mhs['nama'].lower() == nama.lower():
            nilai_baru = float(input("Masukkan nilai baru: "))
            mhs['nilai'] = nilai_baru
            print("Data berhasil diubah!\n")
            return
    print("Data tidak ditemukan.\n")


# Program utama
while True:
    print("Menu:")
    print("1. Tambah Data")
    print("2. Tampilkan Data")
    print("3. Hapus Data")
    print("4. Keluar")

    pilihan = input("Pilih menu (1-4): ")

    if pilihan == "1":
        tambah()
    elif pilihan == "2":
        tampilkan()
    elif pilihan == "3":
        nama = input("Masukkan nama yang akan dihapus: ")
        hapus(nama)
    elif pilihan == "4":
        print("Program selesai.")
        break
    else:
        print("Pilihan tidak valid.\n")
