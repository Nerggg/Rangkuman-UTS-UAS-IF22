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

# Kesimpulan



# Pertanyaan
