# project-website

from itertools import combinations

# Data barang dan nilainya
barang = {
    "Buku": 5,
    "Tas": 8,
    "Sepatu": 6,
    "Laptop": 10,
    "Jam": 4
}

# Batas maksimum kapasitas
batas = 20

nilai_maksimum = 0
kombinasi_terbaik = []

# Memeriksa semua kemungkinan kombinasi
for r in range(1, len(barang) + 1):
    for kombinasi in combinations(barang.items(), r):

        # Menghitung total nilai kombinasi
        total = sum(nilai for nama, nilai in kombinasi)

        # Memeriksa apakah tidak melebihi batas
        if total <= batas:
            if total > nilai_maksimum:
                nilai_maksimum = total
                kombinasi_terbaik = kombinasi

# Menampilkan hasil
print("=== PEMILIHAN KOMBINASI NILAI MAKSIMUM ===")
print("Batas kapasitas:", batas)

print("\nBarang yang dipilih:")
for nama, nilai in kombinasi_terbaik:
    print(nama, "=", nilai)

print("\nTotal nilai maksimum:", nilai_maksimum)
print("Sisa kapasitas:", batas - nilai_maksimum)
