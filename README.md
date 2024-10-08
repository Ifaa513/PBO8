# Aplikasi Pendataan Buku dengan Fitur CRUD - JAVA SWING X PostgreSQL 🚀
Program ini merupakan implementasi dari aplikasi CRUD Data Buku, yang berfungsi untuk mengelola data buku dengan menggunakan GUI dan menyimpan data tersebut dalam database PostgreSQL.
## 🔧 Tech
Aplikasi ini dibuat dengan menggunakan:
- [Java](https://www.oracle.com/java/technologies/downloads/?er=221886) - Java merupakan bahasa pemrograman utama yang digunakan untuk membuat aplikasi sederhana ini.
- [Swing](https://docs.oracle.com/javase/tutorial/uiswing/start/index.html) - Java Swing digunakan untuk membangun antarmuka pengguna grafis (GUI), Swing ini merupakan library GUI di Java yang menyediakan berbagai komponen seperti tombol, tabel, label, dan lain-lain untuk membuat aplikasi desktop.
- [JDBC (Java Database Connectivity)](https://docs.oracle.com/javase/tutorial/jdbc/) - JDBC adalah API dalam Java yang digunakan untuk menghubungkan aplikasi Java dengan berbagai database, dalam aplikasi ini database yang digunakan adalah PostgreSQL, dimana aplikasi mengeksekusi operasi insert, update, delete, dan query data menggunakan JDBC.
- [PostgreSQL](https://www.postgresql.org/download/) - PostgreSQL adalah sistem manajemen basis data berbasis objek yang bersifat open source, dalam aplikasi ini database PostgreSQL dikoneksikan menggunakan JDBC.
- [NetBeans IDE](https://netbeans.apache.org/download/index.html) - NetBeans IDE adalah Integrated Development Environment (IDE) yang berifat open source yang digunakan untuk pengembangan aplikasi, terutama aplikasi Java. NetBeans juga mendukung berbagai bahasa pemrograman lain seperti PHP, HTML5, JavaScript, C/C++, dll.
## 🔭 Features
### 1. 🎬 [Insert (Create)](https://github.com/Ifaa513/PBO8/blob/main/BukuFrame.java)
Saat pengguna menekan tombol INSERT, data buku yang dimasukkan pada form akan disimpan ke dalam database dengan menggunakan perintah INSERT INTO. Data ini dimasukkan ke dalam tabel Buku di PostgreSQL.
### 2. 🔎 [Tampil (Read)](https://github.com/Ifaa513/PBO8/blob/main/BukuFrame.java) 
Fungsi tampil() digunakan untuk mengambil data dari tabel Buku dan menampilkannya di tabel GUI. Setiap kali ada perubahan baik insert, update, dan delete, data akan diperbarui dan ditampilkan kembali.
### 3. ✏️ [Update](https://github.com/Ifaa513/PBO8/blob/main/BukuFrame.java)
Saat pengguna memilih data buku di tabel dan menekan tombol UPDATE, data buku yang sudah dimodifikasi pada form akan diperbarui di database dengan menggunakan perintah UPDATE.
### 4. ❌ [Delete](https://github.com/Ifaa513/PBO8/blob/main/BukuFrame.java)
Fungsi ini memungkinkan pengguna untuk menghapus data buku berdasarkan ID_Buku. Perintah DELETE FROM digunakan untuk menghapus data dari database.
## 🐙 [DbUtils](https://github.com/Ifaa513/PBO8/blob/main/DbUtils.java)
Program ini adalah sebuah utility class bernama DbUtils yang menyediakan metode untuk mengubah hasil query dari database berupa ResultSet menjadi objek TableModel. TableModel digunakan untuk menampilkan data dalam komponen GUI seperti JTable di Java Swing.

### 🎁 Fitur Tambahan
- [tblDataMouseClicked](https://github.com/Ifaa513/PBO8/blob/main/BukuFrame.java)
Fungsi ini dibuat untuk memudahkan pengguna agar tidak perlu mengisi ulang data buku yang ia pilih pada baris tabel untuk di update/di delete atau sekedar dilihat saja. Fungsi ini mengambil data dari baris yang diklik oleh pengguna dan menampilkannya ke dalam form input, seperti ID buku, judul buku, penulis, dst.
- [Clear](https://github.com/Ifaa513/PBO8/blob/main/BukuFrame.java)
Fungsi ini bekerja dengan mengosongkan semua input pada form, seperti menghapus teks di field ID buku, judul buku, penulis, dan lainnya. Tujuannya adalah untuk mereset form agar siap digunakan untuk memasukkan data baru atau menghindari kesalahan input ketika form masih berisi data sebelumnya.
