# latihan 1
Input Pengguna:
   Program meminta pengguna untuk memasukkan nilai n, yaitu jumlah bilangan acak yang ingin ditampilkan. Nilai n ini diinputkan pada runtime.

Proses:
Program menggunakan perulangan while untuk memastikan jumlah bilangan acak yang dihasilkan dan ditampilkan sesuai dengan yang diminta oleh pengguna.
Setiap bilangan acak dihasilkan menggunakan random.random(), yang menghasilkan bilangan acak antara 0 dan 1.
Jika bilangan acak yang dihasilkan lebih kecil dari 0.5, maka bilangan tersebut akan ditampilkan.
Proses ini akan terus berlanjut sampai jumlah bilangan yang ditampilkan mencapai nilai n.

Output:
Program akan menampilkan sejumlah bilangan acak yang lebih kecil dari 0.5 sesuai dengan jumlah yang diminta oleh pengguna.
    
   ```python
    # Meminta input dari pengguna untuk jumlah bilangan acak yang ingin ditampilkan
    n = int(input("Masukkan jumlah bilangan acak yang ingin ditampilkan: "))

    # Meminta input dari pengguna untuk jumlah bilangan acak yang ingin ditampilkan
    n = int(input("Masukkan jumlah bilangan acak yang ingin ditampilkan: "))
    count = 0  # Variabel untuk menghitung jumlah bilangan acak yang telah ditampilkan
    
    # Menggunakan while loop untuk terus menampilkan bilangan acak sampai mencapai jumlah yang diinginkan
    while count < n:
        # Menghasilkan bilangan acak antara 0 dan 1
        random_number = random.random()
        
        # Jika bilangan acak lebih kecil dari 0.5, tampilkan
        if random_number < 0.5:
            print(random_number)
            count += 1  # Menambah hitungan bilangan yang sudah ditampilkan
```

# Latihan 2
Modal Awal: 
Program mulai dengan modal usaha sebesar 100 juta.

Proses:
Program menggunakan perulangan for untuk menghitung keuntungan bulan demi bulan selama 8 bulan.
Keuntungan pada setiap bulan dihitung dengan persentase yang berbeda:
Bulan 1 dan 2: Tidak ada keuntungan (0%).
Bulan 3: Keuntungan 1% dari modal awal.
Bulan 5: Keuntungan meningkat menjadi 5% dari modal awal.
Bulan 8: Keuntungan menurun menjadi 3% dari modal awal.
Bulan lainnya: Keuntungan tetap 1%.
Keuntungan setiap bulan akan ditambahkan ke total keuntungan yang dihitung.

Output:
Program menampilkan total keuntungan yang diperoleh setelah 8 bulan berjalan, dalam format mata uang yang mudah dibaca

    ```python
    # Modal awal usaha (dalam juta rupiah)
    modal_awal = 100000000  # 100 juta
    keuntungan = 0  # Inisialisasi total keuntungan

    # Loop selama 8 bulan
    for bulan in range(1, 9):
        # Kondisi keuntungan berdasarkan bulan
        if bulan == 1 or bulan == 2:
            # Pada bulan 1 dan 2 tidak ada keuntungan
            laba_bulan = 0
        elif bulan == 3:
            # Pada bulan 3, laba mulai 1% dari modal awal
            laba_bulan = 0.01 * modal_awal
        elif bulan == 5:
            # Pada bulan 5, laba meningkat menjadi 5%
            laba_bulan = 0.05 * modal_awal
        elif bulan == 8:
            # Pada bulan 8, laba menurun menjadi 3%
            laba_bulan = 0.03 * modal_awal
        else:
            # Untuk bulan selain yang disebutkan, laba tetap 1%
            laba_bulan = 0.01 * modal_awal
        
        # Menambahkan keuntungan bulan ini ke total keuntungan
        keuntungan += laba_bulan  

    # Menampilkan total keuntungan selama 8 bulan
    print(f"Total keuntungan selama 8 bulan adalah: Rp {keuntungan:,.2f}")
```

# Latihan 3
Saldo Awal:
Program dimulai dengan saldo sebesar Rp 1.000.000.

Menu Pilihan:
Program menampilkan tiga opsi kepada pengguna:
Tarik Uang: Pengguna dapat menarik sejumlah uang, selama saldo mencukupi.
Cek Saldo: Pengguna dapat memeriksa saldo mereka.
Keluar: Pengguna dapat memilih untuk keluar dari mesin ATM

Proses:
Tarik Uang: Jika pengguna memilih untuk menarik uang, program akan meminta jumlah uang yang ingin ditarik. Jika jumlah yang diminta lebih besar dari saldo yang ada, program akan memberikan peringatan bahwa saldo tidak cukup. Jika cukup, uang akan ditarik dan saldo akan dikurangi.
Cek Saldo: Pengguna dapat memilih opsi ini untuk memeriksa saldo mereka.
Keluar: Pengguna dapat memilih opsi ini untuk keluar dari mesin ATM, yang akan menghentikan program.

Perulangan:
Program menggunakan perulangan while yang terus berjalan hingga pengguna memilih untuk keluar. Setiap kali transaksi selesai, program kembali menampilkan menu pilihan.

Output:
Program akan menampilkan saldo saat ini setelah setiap transaksi, atau pesan kesalahan jika saldo tidak cukup untuk menarik uang

```python
    # Saldo awal pengguna (Rp 1.000.000)
    saldo = 1000000  # Saldo awal Rp 1.000.000

    # Menampilkan saldo awal pengguna
    print("Selamat datang di mesin ATM!")
    print(f"Saldo Anda saat ini: Rp {saldo:,.2f}")

    # Program berjalan dalam loop hingga pengguna memilih untuk keluar
    while True:
        # Menampilkan menu transaksi
        print("\nPilih transaksi:")
        print("1. Tarik Uang")
        print("2. Cek Saldo")
        print("3. Keluar")
        
        # Meminta input pilihan transaksi dari pengguna
        pilihan = input("Masukkan pilihan (1/2/3): ")

        if pilihan == "1":
            # Tarik uang
            while True:
                try:
                    jumlah_tarikan = int(input("Masukkan jumlah uang yang ingin ditarik: Rp "))
                    if jumlah_tarikan <= 0:
                        print("Jumlah penarikan harus lebih besar dari 0. Coba lagi.")
                        continue
                    if jumlah_tarikan > saldo:
                        # Mengecek apakah saldo cukup untuk penarikan
                        print("Saldo Anda tidak cukup untuk melakukan penarikan.")
                    else:
                        # Mengurangi saldo dengan jumlah yang ditarik
                        saldo -= jumlah_tarikan
                        # Menampilkan informasi tentang penarikan dan saldo setelahnya
                        print(f"Uang Rp {jumlah_tarikan:,.2f} berhasil ditarik. Sisa saldo: Rp {saldo:,.2f}")
                    break
                except ValueError:
                    print("Input tidak valid! Harap masukkan angka yang valid.")
        
        elif pilihan == "2":
            # Menampilkan saldo pengguna
            print(f"Saldo Anda saat ini: Rp {saldo:,.2f}")
        
        elif pilihan == "3":
            # Keluar dari program ATM
            print("Terima kasih telah menggunakan mesin ATM. Sampai jumpa!")
            break  # Keluar dari loop dan mengakhiri program
        
        else:
            # Menangani pilihan yang tidak valid
            print("Pilihan tidak valid. Silakan coba lagi.")
```

      
