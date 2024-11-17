---
title: Centrality graph

---

#### Social Network Analysis 
merupakan bidang kajian yang mengekplorasitentang hubungan manusia dengan menggunakan teori graf. Implementasi Social Network Analysis dapat menjelaskan relasi atau hubungan antar aktor melalui visualisasi berbentuk graf. Relasi dalam analisis jaringan sosial dapat diproses dalam bentuk perhitungan yang disebut centrality dalam sebuah jaringan sosial sesuai dengan posisi masing-masing aktor di dalam struktur jaringan tersebut.

#### Social network 
terdapat node yang mewakili 
orang atau individu atau aktor. 
Relasi  antar objek  dapat dinyatakan dengan link 
atau edges yang terjadi antara aktor tersebut 
Social network terdiri dari banyak aktor 
yang mempunyai relasi satu sama lain hingga
membentuk peta jaringan sosial yang dinyatakan dengan 
graph.


| Node | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   |  9  |
|:----:| --- | --- | --- | --- | --- | --- | --- | --- |:---:|
|  1   | -   | 1   | 1   | 1   | 0   | 0   | 0   | 0   |  0  |
|  2   | 1   | -   | 1   | 0   | 0   | 0   | 0   | 0   |  0  |
|  3   | 1   | 1   | -   | 1   | 0   | 0   | 0   | 0   |  0  |
|  4   | 1   | 0   | 1   | -   | 1   | 1   | 0   | 0   |  0  |
|  5   | 0   | 0   | 0   | 1   | -   | 1   | 1   | 1   |  0  |
|  6   | 0   | 0   | 0   | 1   | 1   | -   | 1   | 1   |  0  |
|  7   | 0   | 0   | 0   | 0   | 1   | 1   | -   | 1   |  1  |
|  8   | 0   | 0   | 0   | 0   | 1   | 1   | 1   | -   |  0  |
|  9   | 0   | 0   | 0   | 0   | 0   | 0   | 1   | 0   |  -  |

* Tidak semua node dalam jaringan adalah penting  (aktor)
* Mencari node yang paling penting dalam suatu jaringan
* Centrality adalah penentuan aktor menggunakan ukuran pada Social Network Centrality dalam teori graf dan social network .Dibagi menjadi empat jenis, 
1. degree centrality, 
2. betweeness centrality, 
3. closeness centrality 
4. eigenvector centrality

## Degree Centrality
* Degree centrality adalah jumlah edge yang terkoneksi pada suatu node yang mewakili interaksi.
* Pentingnya node ditentukan oleh jumlah node yang berdekatan dengan node tersebut
-- Lebih besar derajatnya (degree), maka lebih penting node itu dalam suatu jaringan 
-- Hanya sebagian kecil node yang memiliki derajat tinggi dalam jaringan

- *Degree Centrality*
  - Rumus: 
  $$ C_D(v_i) = d_i = \sum A_{ij} $$

- *Normalisasi Degree Centrality* 
  - Rumus: 
  $$ C'_D(v_i) = \frac{d_i}{(n-1)} $$
  
 
## Closeness Centrality
* Closenes centrality adalah nilai kedekatan antara satu node dengan node lain dalam jaringan dengan menghitung rata-rata dari jarak relasi node-node tersebut. Skor closeness centrality mewakili kecepatan dalam penyebaran informasi.

- *Average Distance* 
  Rumus: 
  
  $$ D_{\text{avg}}(v_i) = \frac{1}{n-1} \sum_{j \neq i} g(v_i, v_j) $$
  

- *Closeness Central* 
  Rumus: 
  
  $$ C_C(v_i) = \left[ \frac{1}{n-1} \sum_{j \neq i} g(v_i, v_j) \right]^{-1} = \frac{n-1}{\sum_{j \neq i} g(v_i, v_j)} $$
  
## Contoh Closeness Centrality 

| Node | 1   | 2   | 3   |  4  |  5  | 6   | 7   | 8   |  9  |
|:----:| --- | --- | --- |:---:|:---:| --- | --- | --- |:---:|
|  1   | 0   | 1   | 1   |  1  |  2  | 2   | 3   | 3   |  4  |
|  2   | 1   | 0   | 1   |  2  |  3  | 3   | 4   | 4   |  5  |
|  3   | 1   | 1   | 0   |  1  |  2  | 2   | 3   | 3   |  4  |
|  4   | 1   | 2   | 1   |  0  |  1  | 1   | 2   | 2   |  3  |
|  5   | 2   | 3   | 2   |  1  |  0  | 1   | 1   | 1   |  2  |
|  6   | 2   | 3   | 2   |  1  |  1  | 0   | 1   | 1   |  2  |
|  7   | 3   | 4   | 3   |  2  |  1  | 1   | 0   | 1   |  1  |
|  8   | 3   | 4   | 3   |  2  |  1  | 1   | 1   | 0   |  2  |
|  9   | 4   | 5   | 4   |  3  |  2  | 2   | 1   | 2   |  0  |


$$ Cc(3) = \frac{9 - 1}{1 + 1 + 1 + 2 + 2 + 3 + 3 + 4} = \frac{8}{17} = 0.47 $$


$$ Cc(4) = \frac{9 - 1}{1 + 2 + 1 + 1 + 1 + 2 + 2 + 3} = \frac{8}{13} = 0.62 $$

## Betweenness Centrality

* Skor betweeness Centrality mewakili seberapa besar informasi yang tersebar dari suatu aktor. Semakin besar skor, artinya aktor tersebut semakin berperan dalam penyebaran informasi. 

* Semakin banyak lintasan yang harus melewati persimpangan itu (misal tidak ada jalan alternatif), maka semakin penting arti persimpangan tersebut. Hal ini menandakan seberapa besar suatu node diperlukan sebagai penghubung dalam penyebaran informasi di dalam jaringan.
* Ukuran ini juga dapat digunakan untuk mengidentifikasi **boundary spanners**, yaitu orang atau node yang berperan sebagai penghubung (jembatan) antara dua komunitas.
* Menghitung jumlah lintasan terpendek yang melewati suatu node.
* Node dengan  betweenness  tinggi  adalah  penting dalam komunikasi dan penyebaran informasi.
* Betweenness Centrality.

* Rumus Betweenness Centrality

$$ C_B(v_i) = \sum_{v_s \neq v_i \neq v_t \in V, s < t} \frac{\sigma_{st}(v_i)}{\sigma_{st}} $$

### Keterangan
- $$ \sigma_{st}: \text{Jumlah lintasan terpendek antara} (s) dan (t) $$

- $$ \sigma_{st}(v_i): \text{Jumlah lintasan terpendek antara} (s) dan (t) \text{yang melewati} (v_i) $$


Table 2.2:$$ \sigma_{st}(4)/\sigma_{st}$$
|       | s = 1 | s = 2 | s = 3 |
|:-----:|:-----:|:-----:|:-----:|
| t = 5 |  1/1  |  2/2  |  1/1  |
| t = 6 |  1/1  |  2/2  |  1/1  |
| t = 7 |  2/2  |  4/4  |  2/2  |
| t = 8 |  2/2  |  4/4  |  2/2  |
| t = 9 |  2/2  |  4/4  |  2/2  |

Betweenness Centrality Untuk Node 5?

$$ \sigma_{st} : \text{Jumlah path terpendek antara } s \text{ dan } t $$


$$ \sigma_{st}(v_i) : \text{Jumlah path terpendek antara } s \text{ dan } t \text{ yang melewati } (v_i) $$


$$ C_B(v_i) = \sum_{v_s \neq v_i \neq v_t \in V, s < t} \frac{\sigma_{st}(v_i)}{\sigma_{st}} $$

## Normalisasi Betweenness Centrality

$$ C's_B(i) = \frac{C_B(i)}{(n-1)(n-2)/2} $$







  











