# labpy6
# Praktikum 6
# pemjelasan praktikum6
Program ini dibuat untuk mengelola data mahasiswa dengan cara yang sederhana menggunakan Python. 
Data mahasiswa disimpan dalam bentuk daftar (list), di mana setiap elemen adalah sebuah kamus (dictionary) yang menyimpan nama dan nilai mahasiswa.

Ada empat fungsi utama dalam program ini. Pertama, fungsi tambah untuk menambahkan data mahasiswa ke daftar. 
Kedua, fungsi tampilkan digunakan untuk melihat semua data yang sudah dimasukkan. Ketiga, fungsi hapus
memungkinkan pengguna menghapus data mahasiswa tertentu berdasarkan nama. Keempat, fungsi ubah berguna untuk memperbarui nilai mahasiswa yang sudah ada.

Selain itu, program ini memiliki menu interaktif yang memungkinkan pengguna memilih tindakan yang diinginkan, seperti menambah data, melihat data, menghapus data, mengubah data, atau keluar dari program. Pengguna cukup memasukkan pilihan angka sesuai dengan menu yang tersedia. Program akan terus berjalan sampai pengguna memilih opsi keluar.

Data yang dimasukkan hanya disimpan selama program berjalan, sehingga tidak akan tersimpan secara permanen. 
Program ini cocok untuk latihan sederhana dalam pengelolaan data menggunakan Python.

# Codingan
          mahasiswa = []  # Daftar untuk menyimpan data mahasiswa

          def tambah(nama, nilai):
          """Menambahkan data mahasiswa ke dalam daftar."""
          mahasiswa.append({"nama": nama, "nilai": nilai})
          print(f"Data {nama} berhasil ditambahkan.")

          def tampilkan():
          """Menampilkan semua data mahasiswa."""
          if not mahasiswa:
          print("Tidak ada data mahasiswa.")
          return
          print("Daftar Nilai Mahasiswa:")
          for index, mhs in enumerate(mahasiswa, start=1):
          print(f"{index}. Nama: {mhs['nama']}, Nilai: {mhs['nilai']}")

          def hapus(nama):
          """Menghapus data mahasiswa berdasarkan nama."""
          global mahasiswa
          mahasiswa = [mhs for mhs in mahasiswa if mhs["nama"] != nama]
          print(f"Data {nama} berhasil dihapus.")

          def ubah(nama, nilai_baru):
          """Mengubah data mahasiswa berdasarkan nama."""
          for mhs in mahasiswa:
          if mhs["nama"] == nama:
          mhs["nilai"] = nilai_baru
          print(f"Data {nama} berhasil diubah menjadi nilai {nilai_baru}.")
          return
          print(f"Data {nama} tidak ditemukan.")

          def menu():
          """Menampilkan menu utama."""
          while True:
          print("\nMenu:")
          print("1. Tambah Data")
          print("2. Tampilkan Data")
          print("3. Hapus Data")
          print("4. Ubah Data")
          print("5. Keluar")
          pilihan = input("Pilih opsi (1-5): ")

          if pilihan == '1':
              nama = input("Masukkan nama mahasiswa: ")
              nilai = input("Masukkan nilai mahasiswa: ")
              tambah(nama, nilai)
          elif pilihan == '2':
              tampilkan()
          elif pilihan == '3':
              nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
              hapus(nama)
          elif pilihan == '4':
              nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
              nilai_baru = input("Masukkan nilai baru: ")
              ubah(nama, nilai_baru)
          elif pilihan == '5':
              print("Terima kasih!")
              break
          else:
              print("Pilihan tidak valid. Silakan coba lagi.")

      if __name__ == "__main__":
         menu()
# Flowchart
![image](https://github.com/user-attachments/assets/4f6c7ca9-ca54-4f1f-b42c-70627f0e01ed)
# Penjelasannya
Penjelasan Berikut adalah penjelasan mengenai kode yang Anda berikan, yang merupakan program sederhana untuk mengelola data mahasiswa. Program ini memungkinkan pengguna untuk menambah, menampilkan, menghapus, dan mengubah data mahasiswa. Mari kita bahas setiap bagian dari kode tersebut:
# 1.Daftar untuk menyimpan data mahasiswa
           Mahasiswa = []
Di sini, kami mendeklarasikan sebuah daftar kosong bernama mahasiswa yang akan digunakan untuk menyimpan data siswa dalam 
bentuk kamus.
# 2. Fungsi tambah
            def tambah(nama, nilai):
    """Menambahkan data mahasiswa ke dalam daftar."""
    mahasiswa.append({"nama": nama, "nilai": nilai})
    print(f"Data {nama} berhasil ditambahkan.")
Fungsi ini menerima dua parameter: namadan nilai. Fungsi ini akan menambahkan kamus baru ke dalam daftar mahasiswayang berisi nama dan nilai siswa, lalu mencetak pesan bahwa data berhasil ditambahkan.
# 3. Fungsi tampilkan
            def tampilkan():
    """Menampilkan semua data mahasiswa."""
    if not mahasiswa:
        print("Tidak ada data mahasiswa.")
        return
    print("Daftar Nilai Mahasiswa:")
    for index, mhs in enumerate(mahasiswa, start=1):
        print(f"{index}. Nama: {mhs['nama']}, Nilai: {mhs['nilai']}")
Fungsi ini menampilkan semua data siswa yang ada dalam list. Jika daftar kosong, akan dicetak pesan bahwa tidak ada data. Jika ada data, akan mencetak nama dan nilai setiap siswa dengan nomor urut.
# 4. Fungsi Hapus
             def hapus(nama):
    """Menghapus data mahasiswa berdasarkan nama."""
     global mahasiswa
     _mhs = [mhs for mhs in mahasiswa if mhs["nama"] != nama]
    if len(_mhs) < len(mahasiswa):
         mahasiswa = _mhs
      print(f"Data {nama} berhasil dihapus.")
    else:
       print(f"Data {nama} tidak ditemukan.")
Fungsi ini menghapus data siswa berdasarkan nama. Fungsi ini membuat list baru _mhs yang berisi semua siswa kecuali yang namanya sesuai dengan parameter nama. Jika ada perubahan pada list (artinya data dihapus dan dihapus), maka akan mencetak pesan bahwa data berhasil dihapus.
# 5. Fungsi ubah
            def ubah(nama, nilai_baru):
    """Mengubah data mahasiswa berdasarkan nama."""
    for mhs in mahasiswa:
        if mhs["nama"] == nama:
            mhs["nilai"] = nilai_baru
            print(f"Data {nama} berhasil diubah menjadi nilai {nilai_baru}.")
            return
    print(f"Data {nama} tidak ditemukan.")
Fungsi ini digunakan untuk mengubah nilai siswa berdasarkan nama. Jika nama ditemukan, nilai siswa akan diperbarui dengan nilai baru yang diberikan. Jika tidak ditemukan, akan tercetak pesan bahwa data tidak ditemukan.
# 6.Fungsi menu
            def menu():
     """Menampilkan menu utama."""
      True:
      print("\nMenu:")
      print("1. Tambah Data")
      print("2. Tampilkan Data")
      print("3. Hapus Data")
      print("4. Ubah Data")
      print("5. Keluar")
      pilihan = input("Pilih opsi (1-5): ")
Fungsi ini menampilkan menu utama dan meminta pengguna untuk memilih opsi. Menu ini akan terus ditampilkan hingga pengguna memilih untuk keluar.
# 7. Fungsi menjalankan program
             if __name__ == "__main__":
              menu()
Bagian ini memastikan bahwa fungsi menu() hanya akan dijalankan jika skrip ini dijalankan sebagai program utama, bukan jika diimpor sebagai modul. Kesimpulan Program ini adalah aplikasi manajemen data siswa yang sederhana. Pengguna dapat menambahkan, melihat, menghapus, dan mengubah data siswa melalui antarmuka teks. Program ini menggunakan daftar dan kamus untuk menyimpan dan mengelola data.
# Run codingan 
![image](https://github.com/user-attachments/assets/2a5110f9-9292-4bf7-87ec-9e6cb6112fd7)
![image](https://github.com/user-attachments/assets/48c25fbb-ae9f-4a65-9697-1d03d955b5d8)
![image](https://github.com/user-attachments/assets/d2d52a5b-0547-47af-b9f7-de32f089b3ea)

