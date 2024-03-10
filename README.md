# Latar Belakang

Proyek "PacMail" adalah aplikasi web yang dirancang untuk menyediakan platform pengiriman dan penerimaan pesan email dengan fitur-fitur yang memungkinkan pengguna untuk mengelola email mereka dengan lebih efisien. Proyek ini bertujuan untuk memberikan pengalaman pengguna yang intuitif dan responsif dalam mengelola komunikasi email mereka.

Dalam era di mana komunikasi digital telah menjadi bagian penting dari kehidupan sehari-hari, memiliki aplikasi email yang handal dan mudah digunakan sangatlah penting. "PacMail" hadir sebagai solusi untuk memenuhi kebutuhan ini, dengan fokus pada keamanan, kinerja, dan antarmuka pengguna yang ramah.

Proyek "PacMail" akan dikembangkan menggunakan teknologi web modern seperti Python untuk backend, framework Flask untuk pengembangan web, HTML, CSS, dan JavaScript untuk antarmuka pengguna, serta database PostgreSQL untuk menyimpan data pengguna. Selain itu, proyek ini akan di-deploy menggunakan Docker dan Docker Compose untuk memastikan portabilitas dan skalabilitas aplikasi di lingkungan produksi.

# Objective

Tujuan proyek ini adalah untuk memberikan pengalaman pembelajaran yang komprehensif terkait penggunaan alat-alat dan praktik-praktik terkini dalam domain DevOps. Beberapa tujuan khusus yang ingin dicapai melalui proyek ini termasuk:

1. **Pemahaman tentang Deployment Aplikasi Web**: Peserta diharapkan dapat memahami konsep dan proses dasar dalam melakukan deployment aplikasi web dari pengembangan hingga produksi.

2. **Penggunaan Docker dan Docker Compose**: Melalui proyek ini, peserta akan belajar menggunakan Docker dan Docker Compose untuk mengemas, mendistribusikan, dan menjalankan aplikasi dalam lingkungan kontainer.

3. **Pengaturan Server**: Peserta akan mendapatkan pengetahuan tentang bagaimana melakukan setup dan konfigurasi server yang diperlukan untuk menjalankan aplikasi web, termasuk instalasi Docker, Nginx, dan konfigurasi firewall.

4. **Implementasi Continuous Integration/Continuous Deployment (CI/CD)**: Peserta akan mempelajari praktik-praktik CI/CD dengan membuat pipeline otomatis untuk membangun, menguji, dan mendeploy aplikasi secara terus-menerus.

5. **Penggunaan Git dan GitHub Actions**: Proyek ini akan membantu peserta memahami konsep dasar Git, serta mengimplementasikan otomatisasi CI/CD menggunakan GitHub Actions.

6. **Konfigurasi Web Server menggunakan Nginx**: Peserta akan belajar cara mengkonfigurasi Nginx sebagai web server untuk mengatur lalu lintas HTTP/HTTPS ke aplikasi web.

7. **Manajemen Nama Domain dan Sertifikat SSL/TLS**: Proyek ini juga akan memberikan pengetahuan tentang cara membuat nama domain, mengonfigurasi DNS, dan menginstal sertifikat SSL/TLS untuk meningkatkan keamanan aplikasi.

8. **Penggunaan Layanan Cloud**: Jika diperlukan, peserta dapat mempelajari cara menggunakan layanan cloud seperti AWS, Google Cloud, atau Azure untuk hosting aplikasi.

Melalui kombinasi praktik-praktik ini, peserta diharapkan akan memperoleh pemahaman yang mendalam tentang alat-alat dan praktik-praktik DevOps modern, serta kemampuan untuk menerapkan pengetahuan tersebut dalam proyek-proyek masa depan.

# Dokumentasi Project

Dengan memperhatikan informasi yang diberikan, berikut adalah langkah-langkah yang harus Anda ikuti untuk menyelesaikan proyek tersebut:

## Langkah #1 - Persiapan Server
Tahap Persiapan Server merupakan langkah awal yang krusial dalam proyek deployment aplikasi web "PacMail". Tahapan ini bertujuan untuk memastikan bahwa server yang akan digunakan siap untuk menerima dan menjalankan aplikasi web tersebut. Berikut adalah penjelasan lebih rinci tentang setiap langkah dalam Persiapan Server:

1. **Update Paket pada Server:**
   Langkah ini melibatkan pembaruan sistem operasi server dan semua paket yang terinstall ke versi terbaru. Hal ini penting untuk memastikan bahwa sistem operasi dan perangkat lunak yang terinstall memiliki semua pembaruan keamanan dan perbaikan bug terbaru. Pembaruan ini juga memastikan bahwa server berfungsi secara optimal.

2. **Install Docker:**
   Docker adalah platform perangkat lunak yang memungkinkan Anda untuk mengemas, mengirim, dan menjalankan aplikasi dalam lingkungan yang terisolasi yang disebut container. Instalasi Docker akan memungkinkan aplikasi "PacMail" untuk dijalankan dalam kontainer, yang menyediakan fleksibilitas, portabilitas, dan konsistensi lingkungan di seluruh lingkungan pengembangan dan produksi.

3. **Install Nginx sebagai Web Server:**
   Nginx adalah salah satu server web paling populer yang digunakan untuk melayani situs web dan aplikasi web. Instalasi Nginx pada server akan memungkinkan Anda untuk mengkonfigurasi server sebagai titik masuk untuk aplikasi web "PacMail". Nginx dapat digunakan sebagai reverse proxy untuk meneruskan permintaan ke aplikasi web yang berjalan di dalam kontainer Docker.

4. **Konfigurasi Firewall untuk Mengatur Port yang akan Di-open:**
   Konfigurasi firewall merupakan langkah penting dalam mengamankan server. Dalam konteks ini, Anda perlu mengatur firewall server untuk memperbolehkan lalu lintas masuk pada port yang diperlukan oleh aplikasi "PacMail". Hal ini dapat mencakup membuka port standar HTTP (80) dan HTTPS (443) untuk akses web, serta port lain yang diperlukan oleh aplikasi atau layanan yang dijalankan.

Setelah menyelesaikan tahap Persiapan Server, server Anda akan siap untuk menjalankan aplikasi web "PacMail". Pastikan untuk mengikuti instruksi dengan cermat dan memastikan bahwa setiap langkah dilakukan dengan benar untuk memastikan kesiapan server yang optimal.

## Langkah #2 - Persiapan Container

Tahap Komposisi Aplikasi merupakan langkah selanjutnya setelah Persiapan Server dan fokus pada pengaturan aplikasi "PacMail" dalam lingkungan yang dijalankan menggunakan Docker. Berikut adalah penjelasan lebih rinci tentang setiap langkah dalam Komposisi Aplikasi:

1. **Membuat Custom Docker Image untuk Backend:**
   - Dalam langkah ini, Anda diminta untuk membuat Docker image kustom untuk backend aplikasi "PacMail".
   - Docker image ini akan digunakan untuk menjalankan backend aplikasi di dalam kontainer Docker.
   - Anda perlu membuat Dockerfile yang mendefinisikan langkah-langkah untuk membangun Docker image.
   - Dockerfile harus berisi langkah-langkah seperti mengambil base image Python 3.10, mengekspos port 5000, dan menjalankan perintah `python3 api.py` untuk menjalankan server backend.

2. **Membuat Docker Compose untuk Konfigurasi Seluruh Service:**
   - Setelah membuat Docker image kustom untuk backend, Anda perlu membuat Docker compose file untuk mengatur seluruh service aplikasi.
   - Docker compose file ini akan mendefinisikan service-service yang diperlukan untuk menjalankan aplikasi "PacMail", termasuk frontend, backend, dan database.
   - Setiap service akan diatur dengan parameter seperti nama image, nama kontainer, port yang diekspos, pengaturan jaringan, dan pengaturan volume.

3. **Service Frontend:**
   - Anda perlu menentukan konfigurasi untuk service frontend dalam Docker compose.
   - Ini mungkin melibatkan penggunaan image node:latest, menentukan nama kontainer, direktori kerja, dan command untuk menjalankan service frontend.
   - Service frontend juga harus diatur untuk selalu di-restart jika mati dan dijalankan setelah service backend dan database berjalan.

4. **Service Backend:**
   - Untuk service backend, Anda akan menggunakan Docker image kustom yang telah Anda buat sebelumnya.
   - Konfigurasi untuk service backend akan mencakup parameter seperti nama kontainer, hostname, dan pengaturan jaringan.
   - Service backend juga akan diatur untuk selalu di-restart jika mati dan dijalankan setelah service database berjalan.

5. **Service Database:**
   - Service database akan menggunakan image postgres:13 yang tersedia secara publik.
   - Anda perlu menentukan nama kontainer, hostname, dan parameter lingkungan seperti username, password, dan nama basis data.
   - Service database juga akan diatur untuk selalu di-restart jika mati dan akan menggunakan volume Docker untuk menyimpan data basis data.

Dengan menyelesaikan tahap Komposisi Aplikasi, Anda akan memiliki lingkungan Docker yang terkonfigurasi dengan baik untuk menjalankan aplikasi "PacMail". Pastikan untuk memahami setiap langkah dengan baik dan melakukan konfigurasi sesuai dengan instruksi yang diberikan.

## Langkah #3 - Pipeline CI/CD

Langkah #3 - Membuat Pipa CI/CD melibatkan pembuatan pipeline otomatisasi untuk Continuous Integration (CI), Continuous Delivery (CD), dan Continuous Deployment (CD) menggunakan GitHub Actions. Berikut adalah penjelasan lebih rinci tentang setiap langkah dalam membuat pipeline CI/CD:

1. **Persiapan:**
   - Pada langkah ini, Anda akan menyiapkan dan mengkonfigurasi repository GitHub Anda untuk digunakan dalam CI/CD pipeline.
   - Anda akan melakukan proteksi pada branch utama (main/master) agar hanya memungkinkan merge melalui pull request.
   - Menambahkan kolaborator yang akan bertindak sebagai orang yang melakukan pull request.

2. **Continuous Integration (CI):**
   - CI adalah proses otomatisasi yang berfokus pada penggabungan kode yang baru dengan kode yang ada secara berkala, serta menjalankan serangkaian tes otomatis untuk memastikan bahwa perubahan kode tidak menyebabkan kerusakan.
   - Anda akan membuat workflow CI yang akan dipicu setiap kali ada pull request ke branch utama.
   - Workflow CI akan menjalankan serangkaian langkah, termasuk build dan pengujian aplikasi.
   - Sebelum menjalankan pengujian, pastikan untuk menginstal dependensi yang diperlukan menggunakan `pip install -r testing/requirements.txt`.
   - Hasil dari langkah-langkah CI ini akan memberikan umpan balik cepat tentang integritas dan kualitas kode.

3. **Continuous Delivery (CD):**
   - CD adalah proses otomatisasi yang berfokus pada pengiriman perubahan kode ke lingkungan produksi atau pengujian, setelah melewati serangkaian pengujian otomatis dalam lingkungan CI.
   - Anda akan membuat workflow CD yang akan dipicu setiap kali ada merge (push) ke branch utama.
   - Workflow CD akan menangani langkah-langkah untuk mengirimkan docker image ke Docker Hub.
   - Docker image yang dihasilkan akan digunakan untuk melakukan CD ke lingkungan produksi.

4. **Continuous Deployment (CD):**
   - CD adalah proses otomatisasi yang berfokus pada implementasi perubahan kode ke lingkungan produksi atau pengujian secara otomatis, setelah melewati serangkaian pengujian dalam lingkungan CI.
   - Anda akan membuat workflow CD yang akan berjalan setelah CD selesai.
   - Workflow CD akan menangani langkah-langkah untuk mendeploy dan menjalankan aplikasi di server produksi.
   - Pastikan untuk menyertakan script runner (run.sh) pada server sebagai sebuah service yang akan otomatis berjalan ketika server dijalankan.

Dengan menyelesaikan langkah-langkah di atas, Anda akan memiliki CI/CD pipeline yang lengkap untuk aplikasi "PacMail". Pastikan untuk mengonfigurasi setiap langkah dengan cermat dan menguji pipeline secara menyeluruh untuk memastikan bahwa aplikasi dapat dideploy dengan aman dan dapat diandalkan.

## Langkah #4 - Pipeline CI/CD

Langkah #4 - Konfigurasi Web Server menggunakan Nginx bertujuan untuk mengatur Nginx sebagai web server untuk aplikasi "PacMail" yang telah di-deploy. Berikut adalah penjelasan lebih rinci tentang langkah-langkah dalam konfigurasi web server menggunakan Nginx:

1. **Reverse Proxy Configuration:**
   - Konfigurasi reverse proxy pada Nginx adalah langkah penting untuk mengarahkan lalu lintas web dari pengguna ke aplikasi yang dijalankan di server.
   - Anda akan membuat file konfigurasi Nginx untuk aplikasi "PacMail" di direktori konfigurasi Nginx.
   - Dalam file konfigurasi ini, Anda akan menentukan bagaimana Nginx akan meneruskan permintaan HTTP ke aplikasi yang dijalankan di server.
   - Anda akan menentukan host dan port tempat aplikasi berjalan, serta konfigurasi lain seperti header HTTP dan opsi keamanan.

2. **Load Balancing:**
   - Jika diperlukan, Anda juga dapat mengatur Nginx untuk melakukan load balancing di antara beberapa instance aplikasi yang berjalan di server.
   - Ini berguna jika Anda memiliki lebih dari satu instance aplikasi untuk meningkatkan kinerja dan ketersediaan aplikasi.
   - Anda dapat menentukan aturan load balancing, seperti round-robin atau weighted round-robin, dalam file konfigurasi Nginx.

3. **SSL/TLS Configuration:**
   - Jika Anda ingin meningkatkan keamanan aplikasi dengan menggunakan HTTPS, Anda dapat mengkonfigurasi Nginx untuk mengaktifkan SSL/TLS.
   - Ini melibatkan penginstalan sertifikat SSL/TLS yang valid pada server dan konfigurasi Nginx untuk menggunakan sertifikat tersebut.
   - Anda dapat menggunakan Certbot atau layanan sertifikat SSL/TLS lainnya untuk mendapatkan sertifikat SSL/TLS yang valid secara otomatis dan gratis.

4. **Restart Nginx:**
   - Setelah Anda menyelesaikan konfigurasi Nginx, Anda akan me-restart Nginx untuk menerapkan perubahan konfigurasi yang baru saja Anda buat.
   - Pastikan untuk memeriksa log Nginx untuk kesalahan konfigurasi atau masalah lain yang mungkin terjadi saat me-restart Nginx.

Dengan menyelesaikan langkah-langkah di atas, Nginx akan dikonfigurasi dengan benar untuk menjadi web server yang menangani lalu lintas HTTP/HTTPS dan meneruskan permintaan ke aplikasi "PacMail" yang telah di-deploy. Pastikan untuk melakukan konfigurasi dengan hati-hati dan melakukan pengujian untuk memastikan bahwa Nginx berfungsi dengan baik dan aplikasi dapat diakses melalui internet dengan aman dan stabil.

## Langkah 5 - Membuat Nama Domain dan Menginstal Sertifikat SSL 

Merupakan langkah penting dalam memastikan keamanan dan keterlaksanaan aplikasi web "PacMail" di lingkungan produksi. Berikut adalah penjelasan lebih rinci tentang langkah-langkah dalam proses ini:

1. **Membuat DNS Record:**
   - Langkah pertama adalah membuat DNS record untuk menetapkan alamat IP publik server Anda ke nama domain yang Anda miliki.
   - Anda dapat menggunakan layanan DNS yang tersedia secara gratis atau berbayar, seperti Namecheap atau Cloudflare, untuk membuat record DNS A dan CNAME yang sesuai untuk nama domain Anda.
   - Setelah DNS record dibuat, pengguna dapat mengakses aplikasi "PacMail" melalui nama domain yang ditentukan.

2. **Instalasi Sertifikat SSL/TLS:**
   - Untuk meningkatkan keamanan dan privasi pengguna, Anda akan menginstal sertifikat SSL/TLS pada server Anda.
   - Anda dapat menggunakan Certbot, layanan sertifikat SSL/TLS gratis dan open source yang didukung oleh Let's Encrypt, untuk mendapatkan dan menginstal sertifikat SSL/TLS yang valid secara otomatis.
   - Certbot akan memandu Anda melalui proses verifikasi kepemilikan domain dan pemasangan sertifikat SSL/TLS pada server Nginx Anda.
   - Setelah sertifikat SSL/TLS berhasil diinstal, lalu lintas antara pengguna dan server akan dienkripsi, meningkatkan keamanan dan privasi data.

3. **Konfigurasi Nginx untuk SSL:**
   - Setelah sertifikat SSL/TLS terinstal, Anda perlu mengkonfigurasi server Nginx untuk menggunakan HTTPS.
   - Ini melibatkan mengubah file konfigurasi Nginx untuk menyesuaikan penggunaan sertifikat SSL/TLS yang baru diinstal.
   - Anda akan menentukan port SSL (biasanya 443), lokasi sertifikat SSL/TLS, dan konfigurasi keamanan tambahan seperti HSTS (HTTP Strict Transport Security).

4. **Pembaruan Konfigurasi DNS:**
   - Setelah sertifikat SSL/TLS berhasil diinstal dan Nginx dikonfigurasi untuk menggunakan HTTPS, Anda perlu memperbarui DNS record Anda untuk menunjuk ke protokol HTTPS.
   - Ini melibatkan pembaruan record DNS A atau CNAME untuk menyesuaikan alamat IP atau alamat domain dengan protokol HTTPS.

Dengan menyelesaikan langkah-langkah di atas, Anda akan memiliki aplikasi "PacMail" yang aman dan dapat diakses melalui nama domain dengan protokol HTTPS. Pastikan untuk memeriksa dan memastikan bahwa semua langkah telah dilakukan dengan benar, dan lakukan pengujian untuk memastikan bahwa aplikasi berfungsi dengan baik dan aman di lingkungan produksi.
