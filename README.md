mahasiswa = {}

# Fungsi untuk menampilkan seluruh data
def tampilkan():
    print("\n=== Daftar Nilai Mahasiswa ===")
    if not mahasiswa:
        print("Belum ada data.")
    else:
        for nama, nilai in mahasiswa.items():
            print(f"Nama: {nama}, Nilai: {nilai}")
    print("==============================\n")

# Fungsi untuk menambah data
def tambah():
    nama = input("Masukkan nama mahasiswa: ")
    nilai = input("Masukkan nilai mahasiswa: ")

    mahasiswa[nama] = nilai
    print(f"Data untuk {nama} berhasil ditambahkan.\n")

# Fungsi untuk mengubah data berdasarkan nama
def ubah(nama):
    if nama in mahasiswa:
        nilai_baru = input(f"Masukkan nilai baru untuk {nama}: ")
        mahasiswa[nama] = nilai_baru
        print(f"Data {nama} berhasil diubah.\n")
    else:
        print(f"Data dengan nama {nama} tidak ditemukan.\n")

# Fungsi untuk menghapus data berdasarkan nama
def hapus(nama):
    if nama in mahasiswa:
        del mahasiswa[nama]
        print(f"Data {nama} berhasil dihapus.\n")
    else:
        print(f"Data dengan nama {nama} tidak ditemukan.\n")

# Menu utama
while True:
    print("=== Menu ===")
    print("1. Tampilkan Data")
    print("2. Tambah Data")
    print("3. Ubah Data")
    print("4. Hapus Data")
    print("5. Keluar")

    pilihan = input("Pilih menu (1-5): ")

    if pilihan == "1":
        tampilkan()
    elif pilihan == "2":
        tambah()
    elif pilihan == "3":
        nama = input("Masukkan nama yang akan diubah: ")
        ubah(nama)
    elif pilihan == "4":
        nama = input("Masukkan nama yang akan dihapus: ")
        hapus(nama)
    elif pilihan == "5":
        print("Program selesai.")
        break
    else:
        print("Pilihan tidak valid!\n")
