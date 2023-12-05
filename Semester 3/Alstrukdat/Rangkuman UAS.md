# Kelas

ALSTRUKDAT

# Tanggal

5/12/2023

# Judul Materi

Rangkuman UAS

# Main Note

1. List Rekursif
sama aja kaya list di haskell yg terdiri dari head (elemen pertama) dan tail (sisa elemen dlm bentuk list). terus juga karena namanya list rekursif, pasti semua fungsi2 nya pakai cara rekursif
- konso(l, e) = nambah elemen sebagai elemen pertama     
`if isEmpty(l) then`     
`-> newnode(e)`     
`else`     
`p <- newnode(e)`     
`p^.next <- l`     
`-> p`     
- konsdot(l, e) = nambah elemen sebagai elemen terakhir     
`if isEmpty(l) then`     
`-> newnode(e)`     
`else`     
`l^.next <- konsdot(tail(l), e)`     
`-> l`     
- copy(l) -> list = ngopi list      
`if isEmpty(l) then`     
`-> NIL`     
`else`     
`-> konsdot(head(l), copy(tail(l)))`     
yang copy list ini bisa diubah ke bentuk prosedur juga, tinggal ubah returnnya ke bentuk parameter aja
- concat(l1, l2) -> list = utk merging l1 dan l2      
`if isEmpty(l1) then`      
`-> copy(l2)` # ini bingung sih sebenarnya bisa return l2 lgsg aja keknya      
`else`      
`-> konso(concat(tail(l1), l2), head(l1))`      

2. Pohon Biner
ada 3 cara akses          

- pre order => akar, kiri, kanan
- in order => kiri, akar, kanan
- post order => kiri, kanan, akar
```
function nbElmt(p:BinTree) -> integer # utk ngitung jlh elemen
if isEmpty(p) then
    -> 0 # ini bisa juga pake basis 1, if nya diganti jadi isOneElmt
else 
    # opsi 1
    -> 1 + nbElmt(p^.left) + nbElmt(p^.right)

    # opsi 2 (pakai depend on)
    depend on p
        isUnerLeft(p) : -> 1 + nbElmt(p^.left)
        isUnerRight(p) : -> 1 + nbElmt(p^.right)
        isBiner(p) : -> 1 + nbElmt(p^.left) + nbElmt(p^.right)
```

```
function nbLeaf(p:BinTree) -> integer # utk ngitung jlh daun, bisa juga sih dibuat basis pake isEmpty
if isOneElmt(p) then
    -> 1
else 
    depend on p
        isUnerLeft(p) : -> nbLeaf(p^.left)
        isUnerRight(p) : -> nbLeaf(p^.right)
        isBiner(p) : -> nbLeaf(p^.left) + nbLeaf(p^.right)
```

```
function depth(p:BinTree) -> integer # utk ngitung kedalaman tree
if isOneElmt(p) then # basis bisa juga pake 0, jadinya isEmpty(p)
    -> 1
else 
    -> 1 + max(depth(p^.left), depth(p^.right)) # ini bisa lgsg pake fungsi max gini
```

# Latihan Soal

1. List Rekursif
```
function countPos (l:List) -> integer
if (isEmpty(l)) then
    -> 0
else
    if (head(l) >= 0) then
        -> 1 + countPos(tail(l))
    else
        -> countPos(tail(l))
```

```
function sumPos (l:List) -> integer
if (isEmpty(l)) then
    -> 0
else
    if (head(l) >= 0) then
        -> head(l) + sumPos(tail(l))
    else
        -> sumPos(tail(l))
```

```
function isMember (l:List, x:ElType) -> boolean
if (isEmpty(l)) then
    -> false
else
    if (head(l) = x) then
        -> true
    else 
        -> isMember(tail(l), x)
```

```
function isEqual(l1:List, l2:List) -> boolean
if (isEmpty(l1) and isEmpty(l2)) then
    -> true
else
    if (head(l1) = head(l2)) then
        -> isEqual(tail(l1), tail(l2))
    else then
        -> false
```

```
procedure extremes(input l:List, output min,max:integer)
if (head(l) > max) then
    max <- head(l)
else if (head(l) < min) then
    min <- head(l)
extremes(tail(l), min, max)
```

```
procedure listPlus(input l1,l2:List, output l3:List)
konsdot(l3, head(l1) + head(l2))
listPlus(tail(l1), tail(l2), l3)
```

2. Pohon
```
function search(P:BinTree, X:ElType) -> boolean
    B <- false
    searchRecursion(P, X, B)
    if (isEmpty(P)) then
        -> false
    else 
        -> B

procedure searchRecursion(input/output P:BinTree, input X:ElType, output B:boolean)
while (not(B) and not(isEmpty(P))) do
    if P^.info = X then
        B <- true
    else
        searchRecursion(P^.left, X, B)
        searchRecursion(P^.right, X, B)
```

3. UAS 2016  
Nomor 1  
```
function SumGenap (L:List) -> integer
    if (isEmpty(L)) then
        -> 0
    else 
        p <- First(L)
        if (Info(p) mod 2 = 0) then
            -> Info(p) + SumGenap(Next(p))
        else 
            -> SumGenap(Next(p))
procedure DelAllMulOfX (input/output L:List, input X:integer)
    if (not(isEmpty(L))) then
        p <- First(L)
        if (Info(p) mod X = 0) then
            q <- p
            p <- Next(p)
            dealokasi(q)
        DelAllMulOfX(Next(p), X)

```
Nomor 3
```
procedure CreateGraph (input X:String, output L:Graph)
    L <- AlokNode(X)
    L^.Trail <- NIL
    L^.Next <- NIL
procedure InsertFriendship (input/output G : Graph, input PersonA, personB : String)
    A <- SearchPerson(G, PersonA)
    B <- SearchPerson(G, PersonB)
    if (A = NIL) then
        InsertPerson(G, PersonA, A)
    if (B = NIL) then
        InsertPerson(G, PersonB, B)
    friendA <- A^.Trail
    friendB <- B^.Trail
    while (friendA /= NULL) do
        friendA <- Next(friendA)
    while (friendB /= NULL) do
        friendB <- Next(friendB)
    nodeA <- AlokNode(PersonA)
    nodeB <- AlokNode(PersonB)
    friendA <- nodeA
    friendB <- nodeB
function IsFriend (PersonA, personB : String, G : Graph) -> boolean
    found <- false
    A <- SearchPerson(G, PersonA)
    B <- SearchPerson(G, PersonB)
    friendA <- A^.Trail
    while (friendA /= NIL and not(found)) do
        if (friendA = B) then
            found <- true
        else 
            friendA <- Next(friendA)
    -> found
```

4. UAS 2017  
Nomor 3  
```
function SearchV (G : Graph, idV : Integer) -> adrV
    p <- FirstV(G)
    found <- false
    while (p /= NIL and not(found)) do
        if (IdV(p) = idV) then
            found <- true
        else
            p <- NextV(p)
    -> p
```
```
procedure InsertE (input/output G : Graph, input idV1, idV2, idE : integer)
    EMasuk <- AlokE(idE)
    if (EMasuk /= NIL) then
        NextE(EMasuk) <- FirstE(G)
        FirstE(G) <- EMasuk
        V1 <- SearchV(G, idV1)
        V2 <- SearchV(G, idV2)
        V1Edge <- V1^->FirstInc
        V2Edge <- V2^->FirstInc
        while (V1Edge /= NIL) do
            V1Edge <- V1Edge^->Next
        while (V2Edge /= NIL) do
            V2Edge <- V2Edge^->Next
        V1Edge^->PtrEdge <- idE
        V2Edge^->PtrEdge <- idE
        V1Edge^->Next <- NIL
        V2Edge^->Next <- NIL
```

# Kesimpulan

multilist uas 2016 halaman 74  
incidence list uas 2017 halaman 77  
edge list uas 2020 halaman 86  
adjacency list uas 2021 halaman 92  

# Pertanyaan

1. belajar lagi ttg pohon bst dan pohon yg dibuat pake string
