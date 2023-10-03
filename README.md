TUGAS 5

1. Jelaskan manfaat dari setiap element selector dan kapan waktu yang tepat untuk menggunakannya.
- Selektor Elemen: Selektor ini memilih elemen HTML berdasarkan nama mereka. Misalnya, selektor p akan memilih semua elemen <p> pada halaman. Selektor ini berguna ketika Anda ingin menerapkan gaya pada semua elemen dengan jenis tertentu.

- Selektor ID: Selektor ini memilih elemen HTML berdasarkan atribut ID mereka. Atribut ID harus unik untuk setiap elemen pada halaman. Misalnya, selektor #header akan memilih elemen dengan id="header". Selektor ini berguna ketika Anda ingin menerapkan gaya pada elemen tertentu.

- Selektor Kelas: Selektor ini memilih elemen HTML berdasarkan atribut kelas mereka. Atribut kelas dapat digunakan pada beberapa elemen pada halaman. Misalnya, selektor .button akan memilih semua elemen dengan class="button". Selektor ini berguna ketika Anda ingin menerapkan gaya pada sekelompok elemen.

- Selektor Universal: Selektor ini memilih semua elemen HTML pada halaman. Ini diwakili oleh simbol *. Selektor ini berguna ketika Anda ingin menerapkan gaya pada semua elemen pada halaman.

- Selektor Atribut: Selektor ini memilih elemen HTML berdasarkan nilai atribut mereka. Misalnya, selektor [type="text"] akan memilih semua elemen dengan type="text". Selektor ini berguna ketika Anda ingin menerapkan gaya pada elemen dengan nilai atribut tertentu.


2. Jelaskan HTML5 Tag yang kamu ketahui.
- <body>: digunakan untuk menandai isi dari halaman web.
- <button>: digunakan untuk membuat tombol.
- <br>: digunakan untuk membuat baris baru.
- <code>: digunakan untuk menandai kode komputer atau program.
- <div>: digunakan untuk membuat sebuah container untuk konten lainnya.
- <footer>: digunakan untuk menandai footer dari sebuah halaman web.
- <meta>: digunakan untuk memberikan informasi tentang dokumen.
- <nav>: digunakan untuk menandai navigasi dari sebuah halaman web.
- <table>: digunakan untuk membuat sebuah tabel.
- <td>: digunakan untuk membuat sebuah cell pada sebuah tabel.


3. Jelaskan perbedaan antara margin dan padding.
**Margin**:
- Merujuk pada ruang di luar elemen.
- Menentukan jarak antara elemen dan elemen-elemen yang berdekatan.
- Tidak memiliki warna latar belakang.
- Dapat diatur menggunakan properti margin.
- Dapat diatur untuk setiap sisi elemen (atas, kanan, bawah, kiri) atau semua sisi sekaligus.

**Padding**:
- Merujuk pada ruang di dalam elemen.
- Menentukan jarak antara konten elemen dan batasnya.
- Memiliki warna latar belakang.
- Dapat diatur menggunakan properti padding.
- Dapat diatur untuk setiap sisi elemen (atas, kanan, bawah, kiri) atau semua sisi sekaligus.

4. Jelaskan perbedaan antara framework CSS Tailwind dan Bootstrap. Kapan sebaiknya kita menggunakan Bootstrap daripada Tailwind, dan sebaliknya?
- **Tailwind CSS** adalah framework CSS yang berfokus pada utility classes, memungkinkan Anda untuk membangun tampilan dengan menggabungkan kelas-kelas utilitas yang telah ditentukan.
- **Bootstrap** adalah framework CSS dengan desain UI yang siap digunakan, menyediakan komponen UI bawaan dengan gaya yang telah ditentukan.

**Kapan Menggunakan Bootstrap:**
- Saat memerlukan pengembangan cepat dengan komponen siap pakai.
- Saat memiliki sedikit waktu untuk merancang tampilan dan ingin memanfaatkan desain Bootstrap yang telah ditentukan.
- Saat ingin pengalaman pengguna yang konsisten dan familiar dengan desain Bootstrap.

**Kapan Menggunakan Tailwind CSS:**
- Saat ingin tingkat kustomisasi yang tinggi dan fleksibilitas dalam merancang tampilan.
- Saat ingin menghindari desain yang terlalu bervariasi dari gaya Bootstrap atau desain lainnya.
- Saat ingin menghasilkan kode HTML yang lebih bersih tanpa tambahan kelas yang tidak perlu.

5. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial).
Untuk melakukan penyesuaian, saya memanfaatkan file CSS eksternal dengan cara membuat direktori statis baru di dalam direktori utama aplikasi. Kemudian, saya membuat direktori CSS di dalamnya yang berisi file CSS yang diperlukan oleh file HTML yang telah dibuat sebelumnya. Agar file HTML terhubung dengan file CSS, saya menambahkan kode berikut di bagian atas setiap file HTML (contoh untuk main):

{% block meta %}
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="{% static 'css/main.css' %}">
  <title>Home</title>
{% endblock meta %}

setelah itu di file main html saya ubah dikit-dikit dan memanggil class-class, contoh potongan kode:

<div class="container mt-4">
  <div class="table-container">
    <table class="table table-bordered">
        <thead class="table-primary">
            <tr>
                <th>Name</th>
                <th>Price</th>
                <th>Description</th>
                <th>Date Added</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody>
            {% comment %} Berikut cara memperlihatkan data produk di bawah baris ini {% endcomment %}
            {% for product in products %}
                <tr>
                    <td>{{ product.name }}</td>
                    <td>{{ product.price }}</td>
                    <td>{{ product.description }}</td>
                    <td>{{ product.date_added }}</td>
                    <td>
                        <a href="{% url 'main:edit_product' product.pk %}" class="btn btn-warning">Edit</a>
                        <a href="{% url 'main:delete_product' product.pk %}" class="btn btn-danger">Delete</a>
                    </td>
                </tr>
            {% endfor %}
        </tbody>
    </table>
  </div>

nah class class diatas dimodifikasikan sesuai keinginan saya di file main.css, contoh potongan kode:
body {
    font-family: Arial, sans-serif;
    background-color: #F0F8FF; /* Ganti dengan warna latar belakang yang Anda suka */
    margin: 0;
    padding: 0;
  }
  
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
  }
  
  /* Navbar Styles */
  .navbar {
    background-color: #9a0909; /* Ganti dengan warna latar belakang yang Anda suka */
    color: #831717;
    padding: 10px 0;
  }
  
  .navbar a {
    color: #fff;
    text-decoration: none;
    margin-right: 20px;
  }
  
  .navbar-brand {
    font-size: 24px;
    font-weight: bold;
  }
  
  .navbar-toggler-icon {
    background-color: #fff;
  }
  
  /* Header Styles */
  h1 {
    font-size: 36px;
    margin-top: 20px;
  }
  
  h5 {
    font-size: 20px;
    margin-top: 10px;
  }
  
  /* Table Styles */
  /* Mengubah Warna Tabel */
  /* Membuat container untuk tabel */
.table-container {
  display: flex;
  justify-content: center; /* Untuk mengatur ke tengah horizontal */
  margin: 70px; /* Menambahkan margin di samping tabel */
}

table {
  width: 100%;
  border-collapse: separate;
  border-spacing: 0;
  background-color: #ffffff;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

th, td {
  border: 1px solid #ddd;
  padding: 12px;
  text-align: left;
  border-radius: 10px;
}

th {
  background-color: #96D4D4;
  color: #333;
}

tr:nth-child(even) {
  background-color: #f2f2f2;
}

tr:hover {
  background-color: #E0E0E0;
}

td {
  color: #333;
}
