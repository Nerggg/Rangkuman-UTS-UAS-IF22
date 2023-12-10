# Kelas

Matdis

# Tanggal

9/12/2023

# Judul Materi

Rangkuman UAS

# Main Note

1. Teori Bilangan
    - Teorema Euclidean  
        m dibagi n, hasilnya q (quotient) dan sisanya r (remainder)  
        **m = nq + r**  
        note: **r harus positif**  
    - PBB atau GCD (greatest common divisor)  
        cara nyari PBB dari dua angka pake algoritma euclidean (m = nq + r)  
        misal 80 dan 12  
        80 = 6 * 12 + 8  
        12 = 1 * 8 + 4  
        8 = 3 * 4 + 0  
        nilai r terakhir sebelum 0 itu adalah PBB nya  
        maka PBB(80, 12) = 4
    - Relatif Prima  
        a dan b itu relatif prima jika PBB(a, b) = 1  
    - Modulo  
        dari teorema euclidean kan **m = nq + r**, maka dpt dituliskan **m mod n = r** (inget r harus positif)
    - Kongruen  
        misal 38 mod 5 = 3 dan 13 mod 5 = 3, maka 38 [kongruen] 13 (mod 5)  
        simbol konguren itu sama dengan 3 biji
    - Modulo Invers  
        balikan dari a (mod m) adalah x sedemikian sehingga **a * x [kongruen] 1 (mod m)**  
        cara nyarinya:  
        1. pastikan PBB(a, m) = 1. kalo nggak, inversnya gaada
        2. susun biar 1 itu dibentuk dari kombinasi linier pake teorema euclideannya
        3. bilangan yg nempel dengan a, itulah invers modulonya (bisa negatif)
    - Chinese Remainder Problem  
        biasanya soalnya tuh dikasih 3 persamaan dlm bentuk kekongruenan linier terus disuruh nyari solusi x nya  
        contoh soal:  
        x [kongruen] 3 (mod 5)  
        x [kongruen] 5 (mod 7)  
        x [kongruen] 7 (mod 11)  
        <br>
        ubah persamaan 1 ke bentuk linier, jadi x = 3 + 5k1  
        substitusi ke persamaan 2, jadi  
        3 + 5k1 [kongruen] 5 (mod 7)  
        5k1 [kongruen] 2 (mod 7)  
        k1 [kongruen] 6 (mod 7)  
        k1 = 6 + 7k2  
        x = 3 + 5(6 + 7k2)  
        x = 33 + 35k2  
        substitusi x ke persamaan 3  
        33 + 35k2 [kongruen] 7 (mod 11)  
        35k2 [kongruen] -26 (mod 11)  
        k2 [kongruen] 9 (mod 11)  
        k2 = 9 + 11k3  
        x = 33 + 35(9 + 11k3)  
        x = 348 + 385k3  
        maka didapatkan solusi x yaitu **x [kongruen] 348 (mod 385)**
    - Bilangan Prima  
        cara ngecek dia prima ato gak itu dibagi dengan bilangan yg lebih kecil sama dengan dengan akarnya
    - Teorema Fermat  
        jika p adalah prima dan a adlh bilangan sehingga PBB(a, p) = 1 maka  
        **a<sup>p-1</sup> [kongruen] 1 (mod p)**
    - Kode Buku ISBN  
        kan ada 10 digit dan anggap x, jadi 1 * x1 + 2 * x2 ... harus **kongruen dgn 0 dalam mod 11**
    - Hash  
        kayanya ga masuk  
    - Caesar Cipher  
        misal enkripsinya sejauh 10 karakter, maka c = (p + 10) mod 26 dan p = (c - 10) mod 26
    - RSA  
        dah hapal  
    2. Kombinatorial  
        bismillah  
    3. Graf  
        liat rangkuman pas kuis aja, males buat lagi
    4. Tree  
        sama
    5. Kompleksitas  
        gampang

# Kesimpulan



# Pertanyaan
