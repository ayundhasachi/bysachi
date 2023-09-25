1. Django UserCreationForm adalah sebuah bentuk form bawaan yang disediakan oleh Django, sebuah framework web Python untuk memudahkan pembuatan dan pendaftaran pengguna dalam aplikasi web. Form ini digunakan untuk mengumpulkan data yang diperlukan untuk membuat akun pengguna baru, seperti username, password, dan data tambahan lainnya.
KELEBIHAN: Mudah digunakan, validasi otomatis, integrasi yang baik karena adanya Django Authentication, mudahnya untuk di custom.
KEKURANGAN: terbatasnya fungsiolitas (membutuhkan penyesuaian tambahan), keamanan yang kurang (hanya ada password, mungkin perlu penambahan), Tidak mendukung adanya autentikasi tersentralisasi.


2. Autentikasi dan otorisasi adalah dua konsep kunci dalam pengembangan web yang memiliki perbedaan yang signifikan dan penting dalam konteks Django, sebuah framework web Python.

a. Autentikasi:
   - Autentikasi adalah proses memverifikasi identitas user yang mencoba mengakses aplikasi atau sumber daya tertentu. Ini digunakan untuk memastikan bahwa pengguna yang mengakses aplikasi adalah orang yang mereka klaim.
   - Dalam Django, autentikasi adalah proses yang memungkinkan pengguna untuk login ke dalam sistem. Django memiliki sistem autentikasi bawaan yang mengelola informasi pengguna, seperti username dan password, dan menyediakan mekanisme untuk memverifikasi identitas pengguna.

b. Otorisasi:
   - Otorisasi adalah proses menentukan apa yang dapat dilakukan user setelah mereka berhasil diautentikasi. Ini mengontrol hak akses user terhadap berbagai sumber daya atau tindakan di dalam aplikasi.
   - Dalam Django, otorisasi biasanya dilakukan melalui sistem perizinan. Contohnya, kita dapat menentukan apakah user dapat membaca, menulis, atau menghapus entri di database.

hal ini penting karena autentikasi dan otorisasi adalah komponen penting dalam membangun aplikasi web yang aman dan sesuai dengan kebutuhan bisnis kita. Django menyediakan alat yang kuat untuk mengelola kedua aspek ini dengan mudah.


3. Cookies adalah potongan data yang disimpan di perangkat pengguna saat berinteraksi dengan situs web atau aplikasi web tertentu. Cookies digunakan untuk menyimpan informasi pada perangkat pengguna yang dapat diakses oleh server web ketika pengguna mengunjungi situs tersebut lagi. Ini memungkinkan aplikasi web untuk menyimpan informasi tertentu tentang pengguna dan mengingat preferensi atau status mereka.

Django, sebagai framework web Python, menggunakan cookies untuk mengelola data sesi pengguna. Seperti menyimpan data login user, menyimpan data sesi, dan mengamankan cookie.Ini memungkinkan Django untuk menyimpan informasi sesi pengguna di sisi klien dengan aman dan mengaksesnya kembali ketika pengguna melakukan permintaan berikutnya.


4. Penggunaan cookies dalam pengembangan web memiliki manfaat besar, tetapi juga potensi risiko yang perlu diperhatikan. Meskipun tidak ada yang benar-benar "aman secara default" dalam pengembangan web, ada beberapa risiko potensial yang terkait dengan penggunaan cookies adalah kebocoran data, serangan Cross-site Scripting, Serangan Man-In-The-Middle. Cara mewaspadai dan mengurangi risiko adalah: melakukan enkripsi data, securing cookies, monitoring dan memantau penggunaan cookies, mempertimbangkan alternatif (seperti web storage.

5. - Mengaktifkan lingkungan virtual
- Mengimpor modul yang diperlukan, salah satunya adalah UserCreationForm
- Membuat sebuah fungsi yang menerima permintaan dari browser ke server, yang dinamakan sebagai fungsi "register"
- Membuat sebuah berkas HTML yang akan digunakan sebagai tampilan formulir pendaftaran yang telah dibuat
- Mengimpor fungsi "register" ke dalam berkas urls.py dan menambahkan jalur URL ke dalam urlpatterns
- Mengikuti langkah yang sama untuk menciptakan formulir masuk. Kali ini, modul yang diimpor adalah "authenticate" dan "login"
- Fungsi yang dibuat dinamakan "login_user"
- Mengikuti langkah yang serupa untuk membuat fungsi logout, dengan modul yang diimpor adalah "logout"
- Perbedaannya terletak dalam pembuatan berkas HTML; dalam kasus logout, hanya diperlukan sebuah tag hyperlink di dalam berkas main.html
- Untuk otorisasi, menggunakan modul "login_required" untuk membatasi akses hanya untuk pengguna yang telah masuk. Kode ini ditambahkan pada views.py seperti yang berikut:
@login_required(login_url='/login')
def show_main(request):
- Selanjutnya, membuat dua akun untuk menghubungkan model Item dengan Product, menambahkan impor User ke dalam models.py, dan menambahkan kode untuk menghubungkan satu Item dengan User
- Kemudian, melakukan beberapa perubahan pada fungsi create_product di views.py agar Django dapat mengenali bahwa objek yang sedang dibuat dimiliki oleh pengguna tersebut.
- Terdapat perubahan juga pada fungsi show_main agar hanya menampilkan produk yang dimiliki oleh pengguna tertentu.





