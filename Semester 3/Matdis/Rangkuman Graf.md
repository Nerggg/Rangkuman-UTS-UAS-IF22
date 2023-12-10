# ppt pertama

graf ada 2 komponen yaitu simpul (vertex) dan sisi (edge).  
bisa dinyatakan dalam himpunan V = {v1,v2,v3,...} dan E = {e1,e2,e3,...} dan masing2 e itu merepresentasikan hubungan 2 vertex kayak e = (1,2) gitu.  
sisi ganda = misal ada dua sisi yg nunjuk pd angka yg sama  
sisi gelang = sisi yng balik ke angkanya sendiri kayak e = (  2,2) 
pembagian graf menurut ada sisi ganda/gelang
- graf sederhana, gaada ganda/gelang  
- graf tak sederhana, ada ganda/gelang  
    - graf ganda = ada ganda  
    - graf semu = ada gelang  
pembagian graf menurut arah sisi
- graf tak berarah = sisinya gaada arah  
- graf berarah  

terminologi graf
- ketetanggaan, kalau kedua simpul terhubung
- bersisian, e = (1,2) bersisian dengan 1 dan 2 (nyentuhnya kemana gitu)
- simpul terpencil, simpul yg tdk memiliki sisi yg bersisian
- graf kosong, graf yg gaada sisi
- derajat dari suatu simpul, berapa sisi yg nyentuh dia 
    - di graf berarah, derajat dibagi dua jadi derajat masuk dan keluar
    - lemma jabat tangan = jlh derajat semua simpul pd graf adlh 2 kali jlh sisi
    jadi menurut teorema ini, graf gamungkin punya simpul berderajat ganjil sejumlah ganjil (ada soalnya biasanya)
- lintasan, jalan dari suatu vertex ke vertex tertentu
- siklus, jalan yg mulai dari suatu vertex dan berakhir lagi disana
- keterhubungan, dua buah simpul v1 dan v2 disebut terhubung jika ada lintasan dari v1 ke v2 (gak harus langsung)
    - strongly connected jika pd graf berarah terdapat dua arah bolak balik (ga harus langsung jugak)
- upagraf, A upagraf dari B jika vertex dan edge A adlh subelemen dari vertex dan edge B dan komplemen dari upagraf adalah E2 = E - E1 alias sisi selain upagraf awal. vertexnya tinggal ngikutin aja.
    - upagraf merentang (spanning) adlh upagraf yg punya semua V dari ayahnya
- cut set, himpunan sisi yg bisa dibuang sehingga membuat G disconnected

graf khusus
- graf lengkap, misal K5, itu artinya ada 5 vertex dan setiap vertex derajatnya 4
- graf lingkaran, misal C4, itu artinya ada 4 vertex dan setiap vertex derajatnya 2 (selalu dua)
- graf teratur, graf yg semua simpulnya berderajat sama. jumlah sisi = derajat * jlh vertex / 2 (lemma jabat tangan)
- graf bipartit, graf yg simpul2nya bisa dibagi menjadi dua himpunan bagian sehingga setiap sisi dari salah satu himpunan bagiannya (anggap v1) terhubung dengan semua anggota dari v2

# ppt kedua

matriks ketetanggaan / adjacency matrix, itu untuk nentuin simpul mana aja yg bertetanggaan  
matriks bersisian / incidency matrix, nentuin suatu sisi itu bersentuhan/bersisian dengan simpul mana aja. sumbu y nya itu vertex, sumbu x nya edge (pasti bernilai 0 dan 1 aja)  

graf isomorfik, graf yang berbeda secara geometri tapi sisanya sama  
syarat isomorfik: jlh simpul dan sisi sama, jumlah simpul yg berderajat tertentu itu sama  

graf planar, graf yang bisa digambarkan tanpa ada sisinya yg saling beririsan  
kalau udah digambar tanpa ada sisinya saling beririsan berarti dia juga graf bidang  
ada hubungan rumus euler pada graf bidang yaitu  
n - e + f = 2  
n = jlh simpul  
e = jlh sisi  
f = jlh wilayah  

cara menentukan keplanaran suatu graf itu pakai teorema kuratowski  
pokoknya kalau suatu graf G itu upagrafnya sama dengan salah satu graf kuratowski K5 atau K3,3 maka dia otomatis ga planar  

# ppt ketiga

sirkuit euler, melewati semuanya dan kembali ke simpul awal. kalo ada disebut graf euler  
lintasan euler, melewati semuanya tapi ga kembali ke simpul awal. kalo ada disebut graf semi euler  

graf tidak berarah memiliki lintasan euler jika dia memiliki dua buah simpul berderajaat ganjil atau gaada sama sekali  
kalo graf berarah itu punya sirkuit euler jika connected dan setiap simpul memiliki derajat in dan out yg sama  
dan punya lintasan euler jika connected dan setiap simpul memiliki derajat in dan out yg sama kecuali dua simpul, yg pertama punya derajat keluar lebih besar yg kedua punya derajat keluar lebih kecil  

hamilton  
lintasan hamilton itu semua simpul dilewatin sekali (graf semi hamilton)  
sirkuit hamilton itu semua simpul dilewatin sekali kecuali simpul pertama yg dilewatin dua kali (biar bisa balik ke simpul awal) (graf hamilton)  
