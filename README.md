# SIG_Nearest-Neighbor-Analysis

*Tutorial Nearest Neighbor Analysis 

1. Download terlebih dahulu file ne_10m_populated_places_simple.zip dan ne_10m_populated_places_simple.zip

2. Cari file ne_10m_populated_places_simple.zip yang telah diunduh dan pilih file ne_10m_populated_places_simple.shp ke kanvas (*Gambar 1*)

3. Kita akan melihat layer baru ne_10m_populated_places_simple dimuat pada panel layers. Lapisan ini berisi titik yang mewakili tempat berpenduduk. Sekarang kita akan memuat lapisan gempa bumi. Lapisan ini ada pada file teks Tab Serepated Values (TSV). Untuk memuat file ini, klik tombol Open Data Source Manager pada Data Source Toolbar (*Gambar 2*)

4. Pada jendela Data Source Manager pilih Delimited Text (*Gambar 3*)

5. Klik tombol ... di sebelah dile name dan telusuri file earthquakes-2021-11-25_13-39-30_+0530.tsv yang diunduh. Bergantung pada sistem operasi, kita mungkin tidak melihat dile direktori yang diunduh. Jika demmikian, alihkan ke semua file. Setelah dibuka pilih Custom delimiters pada file format dan centang Tab. PAda bagian geometry definition pilih Point coordinates secara default nilai bidang X dan bidang Y akan diisi secara otomatis dengan bidang yang sesuai dengan input, setelah diatur semuanya lalu klik Add (*Gambar 4*)

6. Perbesar dan jelajahi kedua set data. Setiap titik hijau mewakili lokasi kejadian gempa bumi , dan setiap titik orange mewakili lokasi tempat berpenduduk. Tujuan kita yaitu menemukan titik terdekat dari lapisan tempat berpenduduk untuk setiap titik di lapisan gempa. Kita periksa pada atrbut lapisan gempa bumi. Klik layer dan klik Open Attributr Table di Toolbar (*Gambar 5*)

7. Ada 2586 fitur, tetapi data berisi sedikit entri tanpa informasi lintang atau bujur. Kita harus menghapus sebelum melanjutkan lebih jauh. Close Attribute table (*Gambar 6*)

8. Pilih Processing lalu klik Toolbox dan pilih vector geometry dan pilih Remove null geometries. Klik dua kali untuk menampilkan (*Gambar 7*)
 
9. Pada jendela Remove Null Geometries, pilih earthquakes-2021-11-25_13-39-30_+0530 sebagagi input lapisan dan centang pada Also remove empty geometries. Setelah itu klik Run dan klik close (*Gambar 8*)

10. Akan tampil sebuah layer baru Non null geometries. Untuk analisis kita akan menggunakan layer ini sebagai pengganti layer aslinya. Hapus centang pada layer earthquakes-2021-11-25_13-39-30_+0530 di panel layer untuk menyembunyikannya. Pilih layer non null geometries dan klik Open Attribute Table dari Attributes Toolbar (*Gambar 9*)

11. Kita akan melihat jumlah fitur total yang lebih rendah karena semua baris dengan nilai lintang dan bujur kosong telah dihapus. Tutup tabel atribut (*Gambar 10*)

12. Sekarang saatnya melakukan analisis tetangga terdekat. Klik processing lalu Toolboc lalu vector analysis dan pilih Distance to nearest hub(line to hub). Klik dua kali untuk menampilkannya (*Gambar 11*)

13. Pada Distance to Nearest Hub(Line to Hub) pilih Non null geometries sebagai layer SOurce points. Pilih ne_10m_populated_places_simple sebagai Destination hubs. Pilih nama sebagai atribut nama lapisan hub. Alat ini juga akan menghitung jarak garis lurus antara tempat berpenduduk dan gempa terdekat. Tetapkan Kilometers sebagai unit pengukuran. Klik ... di jarak hub dan klik Simpan ke Berkas .. untk menyimpan berkas sebagai earthquakes_with_nearest_city. Klik Run jika proses selesai klik close (*Gambar 12*)

14. Kembali pada tampilan utama QGIS, kita akan melihat lapisan garis baru bernama earthquakes_with_nearest_city. Lapisan ini memiliki ciri-ciri garis yang menghubungkan setiap titik gempa dengan tempat berpenduduk terdekat. Pilih layer earthquakes_with_nearest_city dak klik Open Attribute Tabel pada Toolbar (*Gambar 13*)

15. Kita akan melihat 2 atribut baru bernama HubName dan HubDist ditambahkan ke fitur earthquake features. Ini adalah nama jarak ke te tangga terdekat dari layer tempat berpenduduk (*Gambar 14* *Gambar 15*)
