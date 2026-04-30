# Common Question

## 1. Pengalaman End-to-End

```css
Jadi saya pernah ngerjain project sistem retail inventory untuk sebuah swalayan di Jawa Tengah, bareng tim kecil sekitar tiga orang.

Awalnya kita kerjain bareng, tapi di tengah jalan, karena teman saya yang lead ada project lain, akhirnya sebagian besar tanggung jawab saya yang handle sendiri.

Saya terlibat dari awal, mulai dari komunikasi dengan client, analisis kebutuhan, desain sistem dan database, sampai implementasi dan deployment.

Bahkan waktu grand opening, saya juga turun langsung untuk mantau sistem di production.

Dari situ saya jadi terbiasa handle sistem secara end-to-end dan memahami bagaimana sistem berjalan dari awal sampai benar-benar dipakai oleh user.
```

## 2. Tantangan Terbesar

```css
Tantangan terbesar yang pernah saya hadapi itu terjadi saat sistem sudah di production.

Waktu grand opening, karena traffic tinggi, sistem sempat jadi lambat bahkan hampir overload.

Setelah saya analisis, ternyata masalahnya ada di desain database dan cara pengambilan data. Waktu itu kita pakai ID dalam bentuk string di database relasional, dan juga penggunaan ORM seperti Hibernate yang memicu N+1 query, jadi query ke database terlalu banyak.

Di situ saya refactor beberapa bagian, termasuk mengubah tipe ID jadi integer dan optimasi query supaya lebih efisien.

Hasilnya cukup signifikan, dari yang awalnya load data bisa sampai beberapa menit, akhirnya turun jadi hanya beberapa detik.

Dari situ saya belajar pentingnya desain awal dan testing, terutama untuk memastikan sistem siap dipakai di kondisi real.
```

## 3. Keputusan Penting

```css
Salah satu keputusan penting yang paling berpengaruh buat saya itu terkait pemilihan arsitektur sistem.

Saya pernah menggunakan pendekatan microservices, waktu itu karena memang lagi tren dan tim juga ada.

Tapi di tengah jalan, tim berkurang dan akhirnya saya harus handle sendiri, dan di situ terasa bahwa microservices justru menambah kompleksitas, sementara kebutuhan sistemnya belum sampai ke level itu.

Dari situ saya sadar bahwa pemilihan arsitektur harus berdasarkan kebutuhan, bukan karena tren.

Sekarang saya lebih cenderung mulai dari solusi yang sederhana dulu, yang penting bisa solve problem dan cepat di-deliver, baru dikembangkan bertahap kalau memang dibutuhkan.
```

## Draf Lengkap

Draft lengkap (end-to-end + problem + decision)

```css
Jadi saya pernah ngerjain project sistem retail inventory untuk sebuah swalayan di Jawa Tengah, bareng tim kecil sekitar tiga orang.

Awalnya kita kerjain bareng, tapi di tengah jalan, karena teman saya yang lead ada project lain, akhirnya sebagian besar tanggung jawab saya yang handle sendiri.

Saya terlibat dari awal, mulai dari komunikasi dengan client, analisis kebutuhan, desain sistem dan database, sampai implementasi dan deployment. Bahkan waktu grand opening, saya juga turun langsung untuk mantau sistem di production.

Nah, salah satu tantangan terbesar yang saya hadapi itu justru muncul saat sistem sudah dipakai di kondisi real. Waktu grand opening, karena banyak pembeli, sistem sempat jadi lambat bahkan hampir overload.

Setelah saya analisis, ternyata masalahnya ada di beberapa keputusan teknis di awal, terutama di desain database dan cara ambil data. Waktu itu kita pakai ID dalam bentuk string di database relasional, dan juga penggunaan ORM seperti Hibernate yang memicu N+1 query, jadi query ke database terlalu banyak dan tidak efisien.

Di situ saya refactor beberapa bagian, termasuk mengubah tipe ID jadi integer dan optimasi query supaya lebih sederhana dan efisien. Hasilnya cukup signifikan, dari yang awalnya load data bisa sampai beberapa menit, akhirnya turun jadi hanya beberapa detik.

Dari situ saya belajar pentingnya pengambilan keputusan di awal, terutama terkait performa dan scalability, serta pentingnya testing sebelum sistem benar-benar dipakai di production.

Selain itu, pengalaman lain yang cukup mengubah cara saya berpikir adalah waktu saya pernah menggunakan arsitektur microservices. Waktu itu memang lagi tren, dan tim juga ada, jadi saya coba ke arah sana.

Tapi di tengah jalan, tim berkurang dan akhirnya saya harus handle sendiri. Di situ baru terasa, microservices itu kompleks sekali, harus mengelola banyak service, komunikasi antar service, deployment, dan lain-lain, sementara kebutuhan sistemnya sebenarnya belum sampai ke level itu.

Dari situ saya sadar bahwa pemilihan arsitektur itu harus berdasarkan kebutuhan, bukan karena tren.

Sekarang saya lebih cenderung mulai dari solusi yang sederhana dulu, yang penting bisa solve problem dan cepat di-deliver. Nanti kalau memang butuh scale, baru dikembangkan secara bertahap.

Jadi prinsip yang saya pegang sekarang adalah membangun sistem yang readable, maintainable, dan scalable, tapi tetap sesuai kebutuhan, tidak over-engineering di awal.
```
