TUGAS 6

1. **Jelaskan perbedaan antara asynchronous programming dengan synchronous programming.**
a. Synchronous Programming (Program Sinkron):
Dalam pemrograman sinkron, tugas-tugas dieksekusi secara berurutan, satu per satu. Ini berarti bahwa tugas pertama harus selesai sebelum tugas berikutnya dapat dimulai.
Jika ada tugas yang memerlukan waktu yang lama untuk menyelesaikan, itu dapat menghentikan eksekusi program secara keseluruhan. Selama tugas panjang dieksekusi, program akan terjebak dalam keadaan tunggu, tidak bisa melakukan hal lain.
Cocok untuk tugas-tugas sederhana dan berurutan, tetapi kurang efisien untuk tugas yang memerlukan waktu lama atau berinteraksi dengan perangkat keras atau jaringan.

b. Asynchronous Programming (Program Asinkron):
Dalam pemrograman asinkron, tugas-tugas dieksekusi secara independen, tanpa harus menunggu satu sama lain. Ini berarti program dapat melanjutkan menjalankan tugas-tugas lain tanpa harus menunggu yang sedang berlangsung.
Biasanya digunakan ketika ada tugas yang memerlukan waktu, seperti mengambil data dari jaringan atau menyimpan data ke penyimpanan jarak jauh, tanpa menghentikan program utama.
Biasanya digunakan dalam lingkungan berbasis peristiwa (event-driven) atau dalam pemrograman berbasis thread (thread-based) di mana tugas-tugas dapat dieksekusi secara bersamaan.
Memerlukan mekanisme seperti callback functions, promises, async/await, atau event handlers untuk mengelola tugas-tugas asinkron.

2. **Dalam penerapan JavaScript dan AJAX, terdapat penerapan paradigma event-driven programming. Jelaskan maksud dari paradigma tersebut dan sebutkan salah satu contoh penerapannya pada tugas ini.**
Paradigma "event-driven programming" merujuk pada pendekatan dalam pemrograman di mana program merespons peristiwa atau kejadian yang terjadi secara asinkron. Dalam konteks JavaScript dan AJAX, ini berarti bahwa kode JavaScript tidak hanya dieksekusi berurutan dari atas ke bawah, tetapi lebih banyak berfokus pada menanggapi peristiwa yang terjadi, seperti klik tombol, pengiriman permintaan AJAX yang selesai, atau interaksi pengguna lainnya. Paradigma ini memungkinkan pembuatan aplikasi web yang dinamis dan responsif.
Contoh penerapan paradigma event-driven programming dalam JavaScript dan AJAX adalah:
----Klik Tombol untuk Memuat Data dengan AJAX-----
Saat tombol "Muat Data" diklik, sebuah event click terpicu. sebuah event listener yang menunggu peristiwa klik ini. Ketika tombol diklik, event listener ini akan menjalankan kode untuk memicu permintaan AJAX ke server untuk mengambil data.
Ketika permintaan AJAX selesai dan data diterima, kita akan memiliki event handler yang akan merespons event AJAX selesai (misalnya, event "onload" atau "success").
Data yang diterima akan diolah dan ditampilkan di halaman web, mungkin dalam elemen HTML tertentu.

3. **Jelaskan penerapan asynchronous programming pada AJAX.**
Penerapan asynchronous programming pada AJAX (Asynchronous JavaScript and XML) adalah inti dari penggunaan AJAX itu sendiri. AJAX adalah teknik yang memungkinkan permintaan data dari server ke client dan pembaruan halaman web tanpa harus memuat ulang seluruh halaman. Penggunaan asynchronous programming dalam AJAX memungkinkan halaman web untuk tetap responsif saat permintaan data dikirim ke server dan menunggu respons dari server.

4. **Pada PBP kali ini, penerapan AJAX dilakukan dengan menggunakan Fetch API daripada library jQuery. Bandingkanlah kedua teknologi tersebut dan tuliskan pendapat kamu teknologi manakah yang lebih baik untuk digunakan.**
a. Fetch API:
- Native: Fetch API adalah bagian dari JavaScript standar (ES6), sehingga tidak memerlukan unduhan tambahan. Ini merupakan teknologi bawaan di semua browser modern.
- Promise-Based: Fetch API mengembalikan objek Promise, yang memungkinkan penggunaan asynchronous programming yang bersih dan efisien.
- Lebih Ringan: Fetch API lebih ringan daripada jQuery, sehingga mengurangi beban yang harus diunduh oleh pengguna.
- Fokus pada HTTP Requests: Fetch API dirancang khusus untuk pengiriman permintaan HTTP, sehingga lebih cocok untuk kasus pengambilan dan pengiriman data dari dan ke server.
- Fleksibel: Anda memiliki kontrol lebih besar atas permintaan HTTP, termasuk mengelola header permintaan, metode, dan lainnya.

b. jQuery:
- Cross-Browser Compatibility: jQuery dirancang untuk menyederhanakan pengembangan lintas browser dan menyediakan serangkaian metode yang konsisten untuk berbagai tugas.
- Rich Set of Features: jQuery adalah library yang komprehensif dengan berbagai fungsi seperti animasi, manipulasi DOM, event handling, dan AJAX.
- Callback-Based: jQuery menggunakan callback functions untuk menangani permintaan AJAX, yang dapat menjadi lebih sulit dibaca daripada Promise dalam Fetch API.
- Legacy Support: Terutama digunakan dalam proyek-proyek lama yang mungkin masih bergantung pada jQuery.
- Lebih Berat: jQuery adalah library yang lebih besar daripada Fetch API, jadi jika Anda hanya perlu AJAX, penggunaan jQuery bisa menjadi lebih berat dan berlebihan.

KESIMPULANNYA:  jika hanya membutuhkan fitur AJAX dalam proyek modern dan ingin menghindari beban yang tidak perlu, Fetch API adalah pilihan yang baik. Namun, jika proyeknya lebih besar dan Anda memerlukan fungsionalitas tambahan yang ditawarkan oleh jQuery, maka jQuery bisa menjadi pilihan yang baik.

5.**Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).**
Awalnya, saya memulai dengan menambahkan elemen <div id="get_card" class="cardss" dengan pengaturan tampilan seperti "display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); grid-gap: 20px; margin: 40px; justify-content: center; justify-items: center; padding-bottom: 20px;" untuk membuat kartu-kartu di halaman utama. Selanjutnya, saya melakukan perubahan di model dengan menambahkan field "image_url" dengan tipe data models.TextField(). Kemudian, saya menjalankan perintah migrations untuk mengaplikasikan perubahan tersebut ke basis data.

Selanjutnya, saya membuat dua fungsi di views.py, yaitu "get_product_json" dan "add_product_ajax", yang didekorasi dengan @csrf_exempt, serta mengimpor modul yang diperlukan dan menentukan path-nya. Saya menggunakan teknologi fetch API untuk mengambil data JSON dan mengelolanya dengan fungsi .then().

Kemudian, saya menambahkan beberapa fungsi di file script di halaman utama (main.html), termasuk "refreshProducts", "refreshCards", dan "addProduct". Fungsi-fungsi ini digunakan untuk mengelola konten halaman secara dinamis dan menambahkan atribut "onclick" untuk berbagai elemen.

Selanjutnya, saya membuat fungsi "delete_item_aja" di views.py dengan parameter request dan id, serta menambahkan impor dan path yang diperlukan. Fungsi ini digunakan untuk menghapus item.

Terakhir, saya memperindah tampilan halaman utama (main.html) dengan menambahkan gambar latar belakang (gif) dan melakukan berbagai perubahan gaya lainnya.