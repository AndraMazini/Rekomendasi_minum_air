# Rekomendasi_minum_air
kodingan python dimana mensimulasikan, untuk memberi rekomendasi kebutuhan air untuk pasien sesuai dengan variabel tertentu
# Input untuk data pasien

nama = input("masukan nama anda: ")
usia = int(input("masukan usia anda: "))
jk = input("masukan jenis kelamin anda(L/P): ").upper()
aktivitas_fisik = input("masukan tingkat aktivitas fisik (sedentari/ringan/sedang/berat/atlit): ")
kondisi_kesehatan = input("masukan kondisi kesehatan anda (sehat/hamil/menyusui/demam/infeksi/ginjal/jantung): ")

# Usia
if usia < 3:
    print("masih diberikan asi")
    rekomendasi = 0
elif usia <= 18:
    if jk == "L":
        rekomendasi = 1.6
    elif jk == "P":
        rekomendasi = 1.4
    else:
        print("jenis kelamin tidak valid")
        rekomendasi = 0
elif usia <= 64:
    if jk == "L":
        rekomendasi = 2.5
    elif jk == "P":
        rekomendasi = 2.0
    else:
        print("jenis kelamin tidak valid")
        rekomendasi = 0
else:
    if jk == "L":
        rekomendasi = 2.0
    elif jk == "P":
        rekomendasi = 1.8
    else:
        print("jenis kelamin tidak valid")
        rekomendasi = 0
        
# Aktivitas fisik

if aktivitas_fisik == "sedentari":
    saran = 0
elif aktivitas_fisik == "ringan":
    saran = 0.3
elif aktivitas_fisik == "sedang":
    saran = 0.5
elif aktivitas_fisik == "berat":
    saran = 0.8 
elif aktivitas_fisik == "atlit":
    saran = 1.0
else:
    print("aktivitas tidak valid")
    saran = 0
    
#kondisi kesehatan 

if kondisi_kesehatan == "sehat":
    disarankan = 0
elif kondisi_kesehatan == "hamil":
    disarankan = 0.5
elif kondisi_kesehatan == "menyusui":
    disarankan = 0.5
elif kondisi_kesehatan == "demam":
    disarankan = 0.7
elif kondisi_kesehatan == "infeksi":
    disarankan = 0.7
elif kondisi_kesehatan == "ginjal":
    disarankan = -0.3
elif kondisi_kesehatan == "jantung":
    disarankan = -0.2
else:
    print("Kondisii kesehatan tidak valid/anomali")
    disarankan = 0


#Jumlah per liter pasien yang di rekomendasikan

total = rekomendasi + saran + disarankan

#Output
if usia < 3:
    print("masih diberi dukungan asi")
else:
    print("\n === Hasil rekomendasi jumlah air per liter untuk anda ===")
    print(f"jumlah konsumsi air dasar: {rekomendasi} liter")
    print(f"jumlah konsumsi air aktivitas fisik: {saran} liter")
    print(f"jumlah konsumsi air kondisi kesehatan: {disarankan} liter")
    print(f"-----------------------------------------------------------")
    print(f"rekomendasi jumlah per liter air untuk anda: {total} liter")
print("Terimakasih sudah menggunakan alat kami <3")
