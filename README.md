1. Karakteristik Memori dan Akses Data
Operasi akses elemen pada Array dapat dilakukan dalam waktu O(1) karena array disimpan dalam memori yang kontinu (berurutan).
Setiap elemen memiliki alamat yang bisa dihitung langsung dengan rumus:
alamat = base_address + index × ukuran_elemen
Karena itu, komputer tidak perlu mencari elemen satu per satu—cukup langsung lompat ke alamatnya.
Sebaliknya, Singly Linked List disimpan dalam memori non-kontinu (tidak berurutan).
Setiap node hanya mengetahui alamat node berikutnya melalui pointer.
Untuk mengakses elemen ke-n, harus mulai dari head dan mengikuti pointer satu per satu.
Inilah yang menyebabkan waktu akses menjadi O(n).

2. Analisis Efisiensi Operasi Manipulasi
Linked List lebih unggul dibanding Array dalam operasi penyisipan (insertion) dan penghapusan (deletion) ketika:
Kondisi:
Sering terjadi penambahan/penghapusan di tengah atau awal struktur data
Ukuran data sering berubah (dinamis)
Alasan Teoritis:
Pada Array:
Harus menggeser elemen lain untuk menjaga urutan
Kompleksitas: O(n)
Pada Linked List:
Cukup mengubah pointer (referensi)
Tidak perlu menggeser elemen
Kompleksitas: O(1) (jika posisi sudah diketahui)

3. Konsep Doubly Linked List
Pada Doubly Linked List, setiap node memiliki tiga bagian:
Data → menyimpan nilai
Pointer ke node berikutnya (next)
Pointer ke node sebelumnya (prev)
Dampak Pointer Tambahan:
a. Terhadap Memori:
Membutuhkan lebih banyak memori karena ada tambahan pointer prev
Overhead memori lebih besar dibanding Singly Linked List
b. Terhadap Fleksibilitas:
Bisa melakukan traversal dua arah (maju dan mundur)
Mempermudah operasi:
Penghapusan node (tidak perlu mencari node sebelumnya)
Navigasi bolak-balik

4. Mekanisme Circular Linked List
Circular Linked List berbeda dari Linked List biasa karena:
Node terakhir tidak menunjuk ke NULL
Sebaliknya, menunjuk kembali ke node pertama (head)
Membentuk struktur melingkar (loop)
Perbedaan Utama:
Tidak ada titik akhir (NULL)
Traversal bisa dimulai dari node mana saja dan tetap kembali ke awal
Contoh Use Case:
Round Robin Scheduling (penjadwalan CPU)
Setiap proses mendapat giliran secara bergantian
Setelah proses terakhir, kembali ke proses pertama
Struktur melingkar sangat cocok untuk pola berulang seperti ini

5. Array Dinamis di Python
Python list adalah implementasi dari Dynamic Array.
Mekanisme saat kapasitas penuh (append):
Ketika array penuh, Python:
Mengalokasikan memori baru yang lebih besar (biasanya lebih dari 2× ukuran sebelumnya, strategi over-allocation)
Menyalin semua elemen lama ke memori baru
Menambahkan elemen baru
Menghapus referensi ke array lama
