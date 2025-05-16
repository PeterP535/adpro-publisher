

### a. Berapa banyak data yang dikirim oleh program publisher ke message broker dalam satu kali run?

Jumlah data yang dikirim oleh program **publisher** ke message broker dalam satu kali run tergantung pada implementasi program tersebut. Secara umum, jika hanya satu pesan yang dikirim, maka data yang dikirim hanyalah isi dari satu event atau message. Misalnya, jika pesan yang dikirim berisi data pengguna seperti:

```json
{
  "id": 1,
  "name": "John Doe",
  "email": "johndoe@example.com"
}
```

Maka hanya data tersebut (sekitar beberapa ratus byte) yang dikirim ke message broker dalam satu kali run. Namun, jika publisher dikonfigurasi untuk mengirim banyak pesan (misalnya dalam loop), maka total data yang dikirim akan tergantung pada jumlah dan ukuran masing-masing pesan.

---

### b. URL `amqp://guest:guest@localhost:5672` sama seperti di program subscriber, apa artinya?

URL `amqp://guest:guest@localhost:5672` digunakan baik oleh **publisher** maupun **subscriber** untuk terhubung ke message broker (RabbitMQ) yang sama.

Penjelasan komponennya:

* `guest`: adalah **username** untuk login ke RabbitMQ.
* `guest`: adalah **password** untuk username tersebut.
* `localhost`: berarti koneksi dilakukan ke server RabbitMQ yang berjalan di komputer lokal.
* `5672`: adalah **port default** untuk protokol AMQP yang digunakan oleh RabbitMQ.

Karena baik publisher maupun subscriber menggunakan URL yang sama, ini berarti **keduanya terhubung ke broker yang sama**, sehingga dapat saling bertukar pesan melalui event yang mereka tentukan (misalnya `user_created`).


![RabbitMQ Dashboard](https://media.discordapp.net/attachments/916932753897967666/1372899998366306314/image.png?ex=68287442&is=682722c2&hm=ceb705200427223b2a21e573c9db)


![Rabbit Connection](https://media.discordapp.net/attachments/916932753897967666/1372901180325498991/image.png?ex=6828755c&is=682723dc&hm=bf05ed6736b56fa53628b47440e6b1333d548aa8507b8a6b0e5c21561e46aca7&=&format=webp&quality=lossless&width=1736&height=856)
![console](https://media.discordapp.net/attachments/916932753897967666/1372901675232395354/image.png?ex=682875d2&is=68272452&hm=44ec84eef63fb7b12bbb0a16ff164b644f418ac2ff6346a431147bddcad94f6c&=&format=webp&quality=lossless)

