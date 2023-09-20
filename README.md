1. Form POST berfungsi untuk mengirimkan data atau nilai ke server untuk proses lebih lanjut tanpa menampilkan data tersebut secara terbuka pada URL browser. Contoh penggunaannya adalah saat ingin menyimpan atau memperbarui data di server, seperti saat mengirimkan informasi dari formulir pendaftaran pengguna atau saat ingin memperbarui profil pengguna. Misalnya, dalam kondisi berikut:
if form.is_valid() and request.method == "POST":
    form.save()
    return HttpResponseRedirect(reverse('main:show_main'))

Di sini, form.is_valid() adalah metode yang digunakan untuk memeriksa validitas data yang diterima dari permintaan, sementara request.method == "POST" digunakan untuk memastikan bahwa tindakan ini hanya dijalankan jika permintaan merupakan tipe POST. Kemudian, form.save() digunakan untuk menyimpan data yang dikirimkan ke dalam database, diikuti dengan pernyataan return yang mengarahkan pengguna ke URL tertentu.

Form GET, sebaliknya, digunakan untuk mengambil data dari server dan menampilkannya dalam URL. Data yang dikirimkan melalui form GET akan terlihat pada URL dan berguna untuk permintaan yang hanya mengambil informasi dari server tanpa melakukan perubahan pada data yang ada. Misalnya, saat melakukan pencarian atau penyaringan berdasarkan kriteria tertentu.

2. 
- XML (Xtensible Markup Language) adalah bahasa markah yang diciptakan untuk mengizinkan pengguna mendefinisikan struktur data secara bebas. XML menggunakan tanda markah seperti <tag> untuk membedakan elemen dan atribut data dalam dokumen. Data diorganisir dalam bentuk hirarki yang terdiri dari elemen, atribut, dan nilai. XML memisahkan data dari tampilan dan penting dalam pertukaran data antar platform. Kelebihan XML terletak pada fleksibilitasnya dalam mendefinisikan struktur data sesuai kebutuhan aplikasi.

- JSON (JavaScript Object Notation) adalah format pertukaran data ringan yang mudah dibaca oleh manusia dan mesin. JSON menggunakan pasangan kunci-nilai untuk merepresentasikan data dan mengorganisir data dalam bentuk objek dan array. Contohnya adalah { "Produk": "Telur", "kuantitas": 5 }. JSON banyak digunakan dalam komunikasi antar server dan klien, terutama dalam pengembangan web dan aplikasi. Kelebihan JSON adalah efisiensi dan kemudahan pengolahan data struktur sederhana hingga kompleks.

- HTML (HyperText Markup Language) adalah bahasa markah yang digunakan untuk membuat halaman web. HTML mendefinisikan struktur dan tampilan konten pada halaman web menggunakan elemen-elemen seperti teks, gambar, tautan, dan lainnya. HTML menggunakan tag untuk mengorganisir konten dan memberikan instruksi kepada browser web tentang cara menampilkan halaman. HTML digunakan untuk membuat halaman web dan menampilkan konten di browser.

Perbedaan utama antara XML, JSON, dan HTML terletak pada struktur data dan tujuan penggunaannya. XML digunakan untuk pertukaran data antar platform, JSON digunakan untuk pertukaran data ringan antar aplikasi dan server di web, sementara HTML digunakan untuk membuat halaman web dan menampilkan konten di browser.

3. Keuntungan utama JSON meliputi pertukaran data yang cepat, kemampuan penerjemahan data yang mudah dimengerti oleh manusia, dan struktur data yang sederhana dan terstruktur. JSON memungkinkan pertukaran data yang cepat dengan struktur data yang kompak, mengurangi waktu pemrosesan data sehingga server dapat merespons dengan cepat. JSON juga mempermudah penerjemahan data ke bahasa manusia, memudahkan perbaikan atau penambahan kode. Selain itu, JSON membawa format data yang sederhana dan terstruktur, memudahkan pencarian dan modifikasi kode, serta memungkinkan pengguna untuk memasukkan teks dalam bahasa yang mereka pahami, memudahkan proses pengembangan.

4.
A. Buat File forms.py
Langkah pertama adalah menciptakan file forms.py. File ini akan berperan sebagai wadah input dari pengguna dan akan berisi variabel yang sesuai dengan model yang telah didefinisikan dalam file models.py.

B. Modifikasi views.py
Selanjutnya, di dalam file views.py, kita akan melakukan beberapa modifikasi. Pertama, kita akan menambahkan fungsi baru yang dinamakan create_product. Tujuan dari fungsi ini adalah untuk membuat produk berdasarkan input yang diberikan oleh pengguna. Selain itu, kita juga akan mengubah bagian show_main yang terdapat dalam file views.py agar dapat menyimpan setiap produk yang telah ditambahkan.

C. Buat File create_product.html
Langkah berikutnya adalah menciptakan file create_product.html. File ini akan digunakan sebagai tampilan untuk menginputkan data produk. Di dalam file ini, akan ada sebuah tombol yang akan mengarahkan pengguna ke halaman input produk. Setelah produk berhasil diinputkan, pengguna akan kembali ke layar utama dengan melihat daftar produk yang telah diinputkan sebelumnya.

D. Routing
Tindakan selanjutnya adalah melakukan konfigurasi routing untuk fungsi-fungsi yang telah kita buat sebelumnya. Dalam file urls.py, kita akan menambahkan impor yang diperlukan dan juga menambahkan path-path baru. Hal ini dilakukan untuk memungkinkan akses ke fungsi-fungsi tersebut melalui URL. Berikut ini adalah contoh penambahan path-path tersebut dalam file urls.py:

from django.urls import path
from main.views import show_main
from main.views import show_main, create_product
from main.views import show_main, create_product, show_xml 
from main.views import show_main, create_product, show_xml, show_json
from main.views import show_main, create_product, show_xml, show_json, show_xml_by_id, show_json_by_id 

app_name = 'main'

urlpatterns = [
    path('', show_main, name='show_main'),
    path('create-product', create_product, name='create_product'),
    path('xml/', show_xml, name='show_xml'),
    path('json/', show_json, name='show_json'),
    path('xml/<int:id>/', show_xml_by_id, name='show_xml_by_id'),
    path('json/<int:id>/', show_json_by_id, name='show_json_by_id'),
]



SS POSTMAN: https://drive.google.com/drive/folders/1NDEC6ozzJ7OisQ4GGDs-9njubrl9bYg_
 