## Backend Test case

### Komponen:
- Customer: Entitas yang melakukan request transaksi
- Load Balancer: Mendapatkan dan mendistribusikan permintaan transaksi ke server.
- Database: Menyimpan transaksi secara terpusat dengan fitur locking untuk integritas data.
### Alur Sistem:
- Sistem menerima permintaan transaksi melalui Load Balancer yang mendistribusikannya ke database.
- Sistem mengunci akun nasabah, memeriksa saldo dari database, dan memastikan hanya satu transaksi diproses jika saldo mencukupi.
- Transaksi lainnya yang dilakukan pada detik yang sama ditolak, dan hasil transaksi dikirim kembali ke nasabah tanpa terjadi exception atau error.

<Diagram terlampir dengan format gambar (JPG)>