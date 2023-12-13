# Kelas

TBFO

# Tanggal

12/12/2023

# Judul Materi

Rangkuman UAS

# Main Note

1. CFG dan Parse Trees  
    CFG itu yg kaya gini  
    S -> blablabla  
    A -> blablabla  
    B -> blablabla  
    ada dua jenis simbol, terminal sama nonterminal  
    ini gampangla
2. PDA  
    ini yg pake stack2 kaya tubes itu  
    tuplenya ada 7  
    1. set state
    2. set input symbol
    3. set stack alphabet
    4. fungsi transisi
    5. start state
    6. start stack symbol
    7. set final state  

    untuk penulisan di diagram, dia tuh **a,b/c**  
    - a itu input symbol
    - b stack symbol yg di pop
    - c stack symbol yg di push
3. Deterministic PDA  
    ini in short sama kaya deterministic biasa sih, yg fungsi transisinya gaboleh ada yg sama. tapi bedanya ini PDA  
    ini gampang juga
4. Konversi PDA/CFG  
    - Dari CFG ke PDA  
        ini cuman menghasilkan satu state aja  
        misal ada aturan berikut  
        S -> zMNz  
        M -> aMa | z  
        N -> bNb | z  
        terminal ada 3 yaitu a, b, dan z  
        non terminal ada 3, S, M, dan N  
        pertama kita buat fungsi transisi untuk setiap aturan. misal utk aturan pertama (S -> zMNz). itu berubah jadi **epsilon, S / zMNz** dan ini diulangi utk semua aturannya. jadi total ada 5 fungsi transisi dari step ini.  
        terakhir, kita buat fungsi transisi **hanya utk simbol terminal saja.** kan simbol terminalnya ada 3 yaitu a, b, dan z. jadi tinggal buat **a, a / epsilon** untuk masing2 simbol jadi totalnya ada 3 utk step ini.  
        jadi kesimpulannya, jlh fungsi transisi utk konversi ini adalah **jumlah terminal + jlh aturan.**  
    - Dari PDA ke CFG  
        ini yang ribet wkwkwk  
        ada dua aturan (sebenarnya lebih ke tahap sih)  
        - aturan pertama, buat **S -> [iZq]** dimana  
            - i adalah initial state dari PDA  
            - Z adalah initial stack symbol dari PDA  
            - q adalah **SETIAP** state dari PDA  
        - aturan kedua, utk setiap fungsi transisi (q, a, X) = (r, Y) dimana  
            - q itu current state  
            - a itu input symbol  
            - X itu top stack yg mau dipop  
            - r itu next state  
            - Y itu simbol yg mau dipush  

            maka ada production sebanyak (jlh state total)<sup>(panjang string Y)</sup> dengan aturan sbb  
            [qXr<sub>k</sub>] -> a[rY<sub>1</sub>r<sub>1</sub>][rY<sub>2</sub>r<sub>2</sub>].... dan ini dilanjutin sampe r<sub>k</sub>  
            Y<sub>n</sub> itu maksudnya huruf pada Y yg ke n  
            contoh: ada fungsi transisi (q1, x, #) = (q1, x#)  
            total state pada PDA ini ada 3  
            jadi production yg didapat dari aturan 2 ada 9 yaitu  
            [q1#q1] -> x[q1xq1][q1#q1]  
            [q1#q1] -> x[q1xq2][q2#q1]  
            [q1#q1] -> x[q1xq3][q3#q1]  
            [q1#q2] -> x[q1xq1][q1#q2]  
            [q1#q2] -> x[q1xq2][q2#q2]  
            [q1#q2] -> x[q1xq3][q3#q2]  
            [q1#q3] -> x[q1xq1][q1#q3]  
            [q1#q3] -> x[q1xq2][q2#q3]  
            [q1#q3] -> x[q1xq3][q3#q3]  
            polanya liat dari sini aja ntar pokoknya gitu la  
            tapi kalo dia ngepop, dia cuman 1 production aja jadinya  
            misal (q1, y, x) = (q2, e)  
            jadi [q1xq2] -> y  

5. CNF  
    step utk convert CFG ke CNF  
    1. hilangkan epsilon  
        bismillah bisa  
    2. hilangkan unit production  
        ngilangin simbol nonterminal yg cuman satu (makna simbol nonterminalnya dimasukin)  
    3. hilangin simbol yg tdk terpakai  
        yaitu yg tdk generating dan tidak tercapai **(cek generating dulu baru reachability)**  
    4. last step yaitu ngubah semua aturan jadi **mengandung dua nonterminal atau satu terminal**  
6. Algoritma CYK  
    ini referring ke jawaban latihan aja karna gabisa dicatat disini
8. Turing Machine  
    ada 7 tuple  
    1. himpunan state  
    2. himpunan input symbol
    3. himpunan tape symbol
    4. himpunan fungsi transisi
    5. start state
    6. blank symbol
    7. himpunan final state  

    fungsi transisi nya itu gini  
    (q, x) = (p, y, d)  
    - q itu current state
    - x itu simbol yg dibaca
    - p itu next state
    - y itu simbol yg akan menggantikan x di pita/tape
    - d itu arah pembacaan pita selanjutnya (kiri atau kanan)  

    penjelasan lebih lanjutnya referring ke jawaban latihan aja

# Kesimpulan



# Pertanyaan
