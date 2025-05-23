# timer-module10

![Pic1](static/pic1.png)

Pada kode, perbedaan utamanya terletak pada penambahan satu baris println! di luar task async, tepat sebelum executor dijalankan. Karena async task tidak langsung dieksekusi secara blocking, baris tersebut dieksekusi lebih dulu oleh thread utama, sehingga output "Karolina's computer: hey hey" muncul sebelum log dari dalam async task seperti "howdy!" dan "done!". Hal ini menunjukkan bahwa eksekusi utama tidak menunggu future selesai dan langsung melanjutkan ke instruksi berikutnya. Meskipun future tetap berjalan setelah dijadwalkan, ia baru benar-benar berjalan ketika dipoll oleh executor, dan bukan saat dipanggil.
