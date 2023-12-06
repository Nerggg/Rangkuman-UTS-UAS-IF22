# Kelas

ALGEO

# Tanggal

6/12/2023

# Judul Materi

Rangkuman UAS

# Main Note

1. Bilangan Kompleks  
    bilangan kompleks itu berbentuk **z = a + bi** sedangkan konjugat dari suatu bilangan kompleks itu berbentuk **z\* = a - bi** (tinggal ngubah tanda doang)
    - Terminologi Bilangan Kompleks  
        1. modulus, panjang bilangan kompleks, rumusnya sqrt(a^2 + b^2)
        2. sudut yg dibentuk bilangan kompleks, rumusnya tan invers b/a
        3. z dalam bentuk polar itu **z = r (cos(teta) + i \* sin(teta))**  

    penjumlahan sama perkalian dua bilangan kompleks itu tinggal kekbiasa aja tapi perlu diingat bahwa **i^2 = -1**  
    kalau utk pembagian, pake normalisasi kayak pembagian irasional   
    - Persamaan Euler  
        **e^(ix) = cos(x) + i \* sin(x)** perlu diingat ada plus minus nya di ix  
        penggunaan persamaan euler ini utk mutar vektor z, jadi z' = z * e^(i * teta) dimana teta itu sudut putarnya (kalau positif berlawanan arah jarum jam, kalo negatif searah jarum jam) 
    - Vektor di Ruang Kompleks  
        dua vektor itu **ortogonal jika hasil dot productnya itu nol**  
        ini nih part asiknya, yaitu nilai eigen dan vektor eigen  
        - Nilai Eigen dan Vektor Eigen  
            rumus mencari nilai eigen itu adlh det(i * lambda - A) = 0  
            nanti lambda nya itu adlh nilai eigennya

2. Bilangan Quaternion  
    bentuknya **z = a + b * i + c * j + d * k** dan disini berlaku putaran **ijk** kayak di cross product  
    disini, b * i + c * j + d * k adlh vektor dan a adlh skalar karena itu bisa ditulis ulang jadi **z = a + v**  
    perkalian quaternion itu jugak agak beda yaitu **q1 * q2 = a1a2 + a1v2 + a2v1 + v1 x v2 - v1 . v2** (kayanya cara ini lebih cepat daripada ngalikan langsung sih)
    - Terminologi Quaternion
        - norma (panjang) quaternion, sqrt(a^2 + b^2 + c^2 + d^2)
        - quaternion satuan, gampang lah
        - quaternion murni, quaternion yg a nya nol
        - konjugat, sama kaya bilangan kompleks (tinggal ganti tanda di ijk nya). btw harus diingat bahwa **q * q konjugat = a^2 + b^2 + c^2 + d^2**
        - inverse quaternion, rumusnya konjugat per norma
    - Rotasi Vektor dengan Quaternion
        misal p adlh vektor. p mau diputar sejauh teta berlawanan arah jarum jam terhadap sumbu u. maka bayangannya adalah  
        **p' = q * p * q^(-1)**
        - p = vektor
        - q = cos(teta/2) + sin(teta/2) * vektor satuan u
        - q^(-1) = cos(teta/2) - sin(teta/2) * vektor satuan u  

        note: kalau putar searah jarum jam tinggal sudutnya minus aja

3. Aljabar Geometri (materi tergampang)
    - Wedge Product
        notasinya ^ besar (di keyboard gaada wkwkw)  
        - Aksioma yg penting2  
            - a ^ a = 0
            - a ^ b = -b ^ a

        luas parallelogram yg dibentuk a dan b adalah ||a ^ b|| = ||a|| ||b|| sin(teta). ntar tetanya dapet dari dot product a.b = ||a|| ||b|| cos(teta)
    - Volume Bangun Datar dan Bangun Ruang
        terakhir aja

4. Perkalian Geometri
    sebenarnya sama aja sih cuman ngulang2 perkalian vektor doang
    - Pseudoscalar (I)
        gatau ini apa, pokoknya di ruang R^2 pseudoscalarnya e1 ^ e2 terus di ruang R^3 pseudoscalarnya e1 ^ e2 ^ e3 dst  
        terus ini juga bisa dipake muter vektor. misal ada vektor a, jika a' = a * I maka a itu muter 90 derajat berlawanan arah jarum jam. sedangkan jika a' = I * a maka a itu muter 90 derajat searah jarum jam. dan berlaku aI = -Ia  
    - Balikan Vektor
        misal b = e1 + e2 adlh vektor, balikannya adlh **b^(-1) = b dibagi norma b kuadrat**
    - Operasi Meet
        **A v B = A* . B**  
        - A* = IA
# Kesimpulan

1. ringkasan rumus ada di akhir halaman ppt perkalian geometri bagian 1
2. kayanya perlu ngulang2 ppt perkalian geometri bagian 2

# Pertanyaan

1. gimana caranya ngitung volume bangun datar dan bangun ruang pake aljabar dan perkalian geometri
2. karena perkalian geometri ada rumus dot product sendiri, berarti perkalian dot product disini ga selalu menghasilkan skalar kah
