# Kelas

Matkul Terharam

# Tanggal

11/12/2023

# Judul Materi

Rangkuman UAS

# Main Note

1. Konversi dari bentuk relasi ke klausa  
    stepnya tuh INSEADO  
    - Implication Out  
        ngubah implikasi kedalam bentuk or, contohnya a -> b jadi ~a v b  
    - Negation In  
        masukin negasi ke dalam kurung (jadiin de morgan)  
    - Standardize Variables  
        ngubah variabel yang tabrakan  
    - Existentials Out  
        variabel yg lengket di E itu diganti dengan sesuatu  
        tapi kalau misal gini:  
        Va (Eb (f(a, b)))  
        kalau mau ngilangin E nya, b nya harus dibuat dlm fungsi thd a karena dia lengket dengan a  
        Va (f(a, k(a)))  
        tapi kalau gini doang, ga perlu karena gaada Va nya  
        Eb (f(a, b))  
    - Alls Out  
        ngapus v nya (bener2 cuman dihapus doang)  
    - Distribution  
        make hukum distribusi dimana bisa dipake  
    - Operators Out  
        ngubah jadi klausa  
2. Cara nyari MGU (Most General Unifier)  
    harus pake compare result compare result yg di ppt itu  
    misal soalnya cari MGU dari p(x,b) dan p(a,y)  
    ```
    compare: p(x,b), p(a,y), {}  
        compare: p, p, {}  
        result: {}  
        compare: x, a, {}  
        result: {x <- a}  
        compare: y, b, {x <- a}  
        result: {x <- a, y <- b}  
    result: {x <- a, y <- b}  
    ```
    **penjelasan**  
    - baris pertama itu compare soalnya
    - baris kedua kayanya compare nama fungsinya, kalau ga sesuai, resultnya lgsg fail
    - baris keempat itu compare parameter pertama dari masing2 fungsi terus hasilnya dimasukin ke kurung {} yg disamping
    - baris keenam itu compare parameter kedua
    - lanjut compare parameter lagi jika masih ada
    - pokoknya dia tuh bakal selalu **parameter kiri <- parameter kanan**, jadi kalau misalnya dia compare dan dua2nya tuh **isi dari parameter kanan**, maka dia fail
3. Tips random utk soal klausa klausa  
    - misal ada **a are b** jadinya dia tuh dibuat **a -> b** BUKAN a and b
4. Teori ttg Logika  
    - substitution  
        ada dua, pure sama impure. pure itu variabelnya lain semua, kalo impure variabelnya ada yg sama  
        substitution dilambangkan dgn sigma, ekspresi dilambangkan dengan phi, hasilnya tuh dlm bentuk phi sigma    
    - composition of substitution  
        composition nya dilambangkan dgn sigma dan substitution dilambangkan dgn taw  
        purity dari composition ga mempengaruhi purity akhir dari compositionnya
    - pattern matching  
        misal ada p(x,y), dia itu match sama p(a,b) karena ada matcher yg memungkinkan dia untuk sama yaitu sigma = {x <- a, y <- b}  
    - unification  
        ada ekspresi a dan b, maka unifier itu adalah substitusi sigma yg memenuhi a sigma = b sigma
    - unifier generality  
        sigma itu lebih general atau sama generalnya dgn taw jika ada substitutsi gamma yg memenuhi taw = sigma * gamma
    - composability

# Kesimpulan



# Pertanyaan
