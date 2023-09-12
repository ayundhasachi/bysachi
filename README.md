1. Langkah dalam mengimplemtasikan checklist step-by-step
    - Membuat direktori baru dan menghubungkan dengan github
    - Menginstalasi django pada direktori
    - Membuat aplikasi main pada direktori melalui terminal
    - Mendaftarkan main ke dalam installed_apps pada direktori bysachi
    - Membuat template html pada aplikasi main lalu memasukan variable bahasa django
    - Pada views.py, mendeklarasikan context pada bahasa django
    - Membuat routing dari urls pada main lalu di-route ke urls pada bysachi
    - Membuat app baru pada Adaptable dengan source repository githun
    - Melakukan deployment pada aplikasi

2. https://drive.google.com/file/d/1aXTz4yOdmWjAkeHlNiDgfalEQc105M9I/view?usp=drive_link
link bagan

3. Dengan adanya virtual environment makan terdapat beberapa manfaat bagi pemrogram, yaitu :
    1. Mengisolasi lingkungan direktori, dengan kata lain membantu menghindari konflik dan memastikan kestabilan dari proyek
    2. Mamudahkan pembaruan, jika adanya ingin diperbaharui dari proyek maka pemrogram tidak perlu khawatir menggangu yang lain
    3. Mudah untuk menguji, perubahan yang dilakukan dilakam virtual environment akan lebih mudah dilakukan

4. Ketiga model memiliki perbedaan sebagai berikut
    1. MVC atau Model-View-Controller: Dalam MVC, View dan Controller biasanya lebih erat terkait, yang berarti bahwa mereka sering berinteraksi secara langsung. Model memiliki pengetahuan tentang Controller tetapi tidak tentang View.
    2. MVT atau Model-View-Template : Pada MVT peran yang biasanya dipegang oleh Controller dalam MVC digantikan oleh Template. MVT adalah pola yang lebih umumnya terkait dengan kerangka kerja seperti Django yang digunakan untuk pengembangan web.
    3. MVVM atau Model-View-ViewModel : MVVM akan melakukan ViewModel yang memiliki peran lebih kuat dalam mengelola tampilan daripada Controller dalam MVC. ViewModel mengikat data dari Model ke tampilan secara deklaratif, yang memungkinkan perubahan otomatis dalam tampilan saat data Model berubah.
