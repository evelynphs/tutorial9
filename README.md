## Reflection

1. What are the key differences between unary, server streaming, and bi-directional streaming RPC (Remote Procedure Call) methods, and in what scenarios would each be most suitable?

   - **Unary RPC** <br>
     Pada RPC ini, client mengirimkan satu request ke server, kemudian server memprosesnya dan mengirimkan kembali satu respon. Metode ini cocok digunakan ketika client hanya perlu mengirimkan request tunggal dan menerima respon tunggal seperti ketika melakukan operasi CRUD sederhana. 
   - **Server Streaming RPC** <br>
     Pada RPC ini, client mengirimkan satu request ke server, kemudian server mengirimkan serangkaian respon ke klien yang jumlahnya bisa lebih dari satu. Server dapat mengirimkan beberapa respon tanpa menunggu klien mengirimkan permintaan selanjutnya. Metode ini cocok digunakan ketika client membutuhkan serangkaian data dari server seperti ketika mengambil suatu daftar item.
   - **Bi-Directional Streaming RPC** <br>
     Pada RPC ini, client dan server dapat saling mengirimkan serangkaian message dalam aliran data yang sama, pada waktu yang sama pula tanpa harus saling menunggu satu sama lain. Metode ini cocok digunakan ketika client dan server perlu saling berkomunikasi secara sinkron seperti pada live chat.

<br>

2. What are the potential security considerations involved in implementing a gRPC service in Rust, particularly regarding authentication, authorization, and data encryption? <br>

   Beberapa pertimbangan terkait keamanan tersebut antara lain autentikasi, otorisasi, enkripsi data, _key management_, dan _error handling_. 

<br>

3. What are the potential challenges or issues that may arise when handling bidirectional streaming in Rust gRPC, especially in scenarios like chat applications? <br>

   Beberapa potensi tantangan tersebut (terutama dalam konteks aplikasi chat) antara lain:
   - Sinkronisasi pesan
   - Manajemen koneksi
   - _Error handling_
   - Concurrency dan keamanan (dalam konteks penggunaan memori)
   - Skalabilitas

<br>

4. What are the advantages and disadvantages of using the `tokio_stream::wrappers::ReceiverStream` for streaming responses in Rust gRPC services? <br>

   Kelebihan:

    - Kemudahan integrasi untuk manajemen task asinkronus
    - Fleksibilitas untuk berbagai jenis receiver

   Kekurangan:

    - Ketergantungan pada tokio
    - Kurangnya dukungan untuk middleware
    - Keterbatasan pada scalability

<br>

5. In what ways could the Rust gRPC code be structured to facilitate code reuse and modularity, promoting maintainability and extensibility over time?

   Kode tersebut dapat disusun dengan memperhatikan beberapa prinsip seperti:
   - Pemecahan modul
   - Abstraski terhadap protokol
   - Penggunaan _trait_ dan _generic_
   - Penerapan _design pattern_
   - Unit testing

<br>

6. In the MyPaymentService implementation, what additional steps might be necessary to handle more complex payment processing logic?

   Beberapa step yang mungkin untuk diimplementasikan:
   - Validasi data
   - Pemantauan transaksi
   - Error handling
   - Integrasi dengan payment gateway

<br>

7. What impact does the adoption of gRPC as a communication protocol have on the overall architecture and design of distributed systems, particularly in terms of interoperability with other technologies and platforms?

   Beberapa dampak utamanya antara lain:
   - Desain Berbasis Protokol
   - Serialisasi Protokol Buffer
   - Meningkatkan skalabilitas
