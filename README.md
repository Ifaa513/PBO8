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
### 1. 🎬 Insert (Create)
private void btnInsertActionPerformed(java.awt.event.ActionEvent evt) {                                          
        String ID_Buku, Judul_Buku, Pengarang, Penerbit, Tahun_Terbit;
        try {
            Class.forName(driver);
            conn = DriverManager.getConnection(koneksi, user, password);
            conn.setAutoCommit(false);

            String sql = "INSERT INTO Buku (ID_Buku, Judul_Buku, Pengarang, Penerbit, Tahun_Terbit) VALUES(?, ?, ?, ?, ?)";
            pstmt = conn.prepareStatement(sql);

            ID_Buku = txtID.getText();
            Judul_Buku = txtJudul.getText();
            Pengarang = txtPengarang.getText();
            Penerbit = txtPenerbit.getText();
            Tahun_Terbit = txtTahun.getText();

            pstmt.setInt(1, Integer.parseInt(ID_Buku));
            pstmt.setString(2, Judul_Buku);
            pstmt.setString(3, Pengarang);
            pstmt.setString(4, Penerbit);
            pstmt.setInt(5, Integer.parseInt(Tahun_Terbit));

            pstmt.executeUpdate(); // executeUpdate hanya dipanggil sekali
            conn.commit();

            JOptionPane.showMessageDialog(null, "Data berhasil disimpan");
        } catch (ClassNotFoundException | SQLException ex) {
            JOptionPane.showMessageDialog(null, "Terjadi kesalahan: " + ex.getMessage());
        } finally {
            try {
                if (pstmt != null) {
                    pstmt.close();
                }
                if (conn != null) {
                    conn.close();
                }
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }
        tampil();
    } 
Saat pengguna menekan tombol INSERT, data buku yang dimasukkan pada form akan disimpan ke dalam database dengan menggunakan perintah INSERT INTO. Data ini dimasukkan ke dalam tabel Buku di PostgreSQL.
### 2. 🔎 Read 
Fungsi tampil() digunakan untuk mengambil data dari tabel Buku dan menampilkannya di tabel GUI. Setiap kali ada perubahan baik insert, update, dan delete, data akan diperbarui dan ditampilkan kembali.
### 3. ✏️ Update
Saat pengguna memilih data buku di tabel dan menekan tombol UPDATE, data buku yang sudah dimodifikasi pada form akan diperbarui di database dengan menggunakan perintah UPDATE.
### 4. ❌ Delete 
Fungsi ini memungkinkan pengguna untuk menghapus data buku berdasarkan ID_Buku. Perintah DELETE FROM digunakan untuk menghapus data dari database.
