# Kelas

ORKOM

# Tanggal

2/12/2023

# Judul Materi

Rangkuman UAS

# Main Note

## Cara ngakses array di assembly
misal val[5] = {1,5,2,1,3}  
val[4] = 3  
&val[4] = pointer ke 3  
val = pointer ke 1  
val + 1 = pointer ke 5  
\*(val + 1) = 5  
val + 1\*i = pointer ke elemen ke i  

misal di asm, berlaku val[i] dimana edx = val dan eax = i  
karena val itu integer jadi ukurannay 4 byte  
jadi ngaksesnya di asm adalah (%edx,%eax,4), %eax -> ini juga berarti edx + eax * 4 dan disimpan di eax

kalau array multidimensi kurleb sama aja  
misal ada arr berukuran 5x5 dan kita mau ngakses arr[y][x].  
misal y ada di ebp+8 dan x ada di ebp+12  
movl 8(%ebp), %eax          # ambil y jadi eax = y  
movl arr(,%eax,4), %edx     # akses arr[y] dan simpan ke edx  
movl 12(%ebp), %eax         # ambil x jadi eax = x   
movl (%edx,%eax,4), %eax    # akses edx[x] kaya akses array satu dimensi   

## Cara ngakses struct di assembly
misal ada linked list   
`struct rec {`   
`    int a[3];`   
`    int i;`   
`    struct rec *n;`   
`}`   
dan ada variabel `r = rec`  
jadi ukuran total dari r adalah 20 byte  
- 12 byte utk a[3]  
- 4 byte utk i  
- 4 byte utk n (4 byte utk 32 bit dan 8 byte utk 64 bit)     

jadi cara ngaksesnya sama aja, misal kita mau akses i, edx itu val dan eax itu r. maka  
`r->i = val`   
`movl %edx, 12(%eax)`  
kalau ngakses a[3] itu sama aja kaya [ngakses array](#cara-ngakses-array-di-assembly)

## Cara ngakses union di assembly
kita cek ukuran dari anggotanya dulu, misal ada union u beranggotakan 1 float (8 bytes) dan arr of 2 int (8 bytes). terus misal dia ngakses (secara eksplisit) float u, jadi hasilnya pasti bilangan float itu. tapi kalau dia aksesnya int u jadi hasilnya arr[0]. tapi kalau dia akses u + 4 tanpa kasitau tipenya jadi otomatis dia akses arr[1] karena kemungkinannya cuman itu     
in short, union ini cuman beda di cara ngakses aja. nilainya sama di dalam memori

## Cache
cache terdiri dari 3 komponen yaitu tag, set, dan block  
jlh byte dalam satu blok cache itu adalah 2 pangkat jlh digit dari block  
1. bit valid = untuk validasi apakah blok data dalam cache valid atau tidak. jika ga valid maka gabisa diakses
2. bit tag = untuk dibandingkan dengan bit tag dari data yang diminta. jika sama berarti data tersebut ada dalam cache
3. bit set = menunjukkan ke set mana suatu entri cache akan ditempatkan
4. bit block = berisi byte dari blok data        

## Buffer Overflow
susunan stack itu (di 32 bit) kaya gini
1. stack frame
2. return address (ebp + 4 utk 32 bit dan ebp + 8 utk 64 bit)
3. ebp (ukuran ebp 4 byte utk 32 bit)
4. ebx
5. canary (kalau ada)
6. program     

cara kerja canary tuh kan kalau kita mau ngereplace return address pasti bakal lewatin canary dulu. jadi otomatis canary juga bakal direplace dengan padding yg kita isi. tapi masih bisa di bypass sih, dengan cara padding yg ngisi canary itu diganti dengan nilai canary awal jadi canary ga bakal terganti

# Kesimpulan

kalo diliat dari soal tahun lalu, materi yg penting itu cuman assembly (terutama buffer overflow) dan cache (terutama cara ngakses yg hit n miss itu) doang  

## Materi Assembly
1. [cara ngakses array di assembly](#cara-ngakses-array-di-assembly)
1. [cara ngakses struct di assembly](#cara-ngakses-struct-di-assembly)

# Pertanyaan

1. apa itu caller save dan callee save (kayanya ga masuk)
2. [bagaimana cara ngakses array di assembly](#cara-ngakses-array-di-assembly)
2. [bagaimana cara ngakses union di assembly](#cara-ngakses-array-di-assembly)
3. [gimana susunan stack pas buffer overflow](#buffer-overflow)
4. [bagaimana cara kerja stack protector/canary pada serangan buffer overflow](#buffer-overflow)
