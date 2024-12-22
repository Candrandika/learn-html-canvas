# HTML CANVAS


## Pengertian

```Canvas adalah elemen pada HTML5 yang berfungsi untuk menampilkan grafik, gambar, ataupun teks. Canvas sendiri biasanya digunakan dalam pembuatan game berbasis web, ataupun aplikasi web lain yang memerlukan pengolahan grafis tingkat lanjutan di dalamnya. Dalam pembuatannya, grafik atau objek lain yang dirender pada html canvas harus dibuat secara manual dengan menggunakan JavaScript.```



## Setup

HTML :
```html
<canvas id="canvas" width="100" height="100"></canvas>
```

JavaScript :
```javascript
const canvas = document.getElementById("canvas");
const ctx = canvas.getContext("2d");
```



## Fungsi Penting (Untuk Pembuatan Game)

tiap kode dibawah ini sebaiknya ditulis diantara kode `ctx.beginPath()` dan `ctx.closePath()`

### Fungsi Styling

- `ctx.fillStyle = "red"` : untuk mengatur warna fill
- `ctx.strokeStyle = "blue"` : untuk mengatur warna stroke
- `ctx.lineWidth = 10` : untuk mengatur bentuk stroke
- `ctx.font = "24px Arial"` : untuk mengatur font
- `ctx.textAlign = "left|center|right"` : untuk mengatur posisi text
- `ctx.textBaseline = "top|middle|bottom"` : untuk mengatur posisi text


### Membuat Teks

- `ctx.fillText(text, x, y, maxWidth?)` : untuk membuat text fill
- `ctx.strokeText(text, x, y, maxWidth?)` : untuk membuat text stroke


### Membuat Garis

- `ctx.moveTo(x, y)` : untuk memulai garis
- `ctx.lineTo(x, y)` : untuk mengakhiri garis
- `ctx.stroke()` : untuk menggambar garis


### Membuat Lingkaran

- cara 1
```javascript 
ctx.arc(x, y, radius, startAngle, endAngle, anticlockwise?);
ctx.stroke(); // jika ingin membuat lingkaran dengan stroke
ctx.fill(); // jika ingin membuat lingkaran dengan fill
```

- cara 2
```javascript
ctx.fillArc(x, y, radius, startAngle, endAngle, anticlockwise?); // menjalankan fungsi arc dan fill
ctx.strokeArc(x, y, radius, startAngle, endAngle, anticlockwise?); // menjalanakan fungsi arc dan stroke
```

- `x, y` adalah posisi dari titik tengah lingkaran
- `radius` adalah jari jari lingkaran
- `startAngle` adalah arah lingkaran mulai
- `endAngle` adalah arah lingkaran berakhir
- `anticlockwise` menentukan perputaran lingkaran, `false` untuk searah jarum jam, dan `true` untuk sebaliknya


### Membuat Segiempat

- cara 1
```javascript 
ctx.rect(x, y, w, h);
ctx.stroke(); // jika ingin membuat segiempat dengan stroke
ctx.fill(); // jika ingin membuat segiempat dengan fill
```

- cara 2
```javascript
ctx.fillRect(x, y, w, h); // menjalanakan fungsi rect dan fill
ctx.strokeRect(x, y, w, h); // menjalanakan fungsi rect dan stroke
```

- `x, y` adalah posisi dari titik kiri atas segiempat
- `w` adalah panjang segiempat
- `h` adalah tinggi segiempat


### Menghapus Area

`digunakan untuk menghapus suatu area dalam bentuk segiempat`
```javascript
ctx.clearRect(x, y, w, h);
```

- `x, y` adalah posisi dari titik kiri atas segiempat
- `w` adalah panjang segiempat
- `h` adalah tinggi segiempat

### Menampilkan Gambar / Video

untuk menampilkan gambar / video, gunakan fungsi `drawImage`, dengan beberapa aturan penulisan parameter sebagai berikut

- `ctx.drawImage(image, x, y)`
- `ctx.drawImage(image, x, y, w, h)`
- `ctx.drawImage(image, sx, sy, sw, sh, x, y, w, h)`


penjelasan parameter:
- `image` adalah gambar yang akan ditampilkan
- `sx, sy` adalah posisi dari gambar (source) yang akan ditampilkan
- `sw, sh` adalah lebar dan tinggi dari gambar (source) yang akan ditampilkan
- `x, y` adalah posisi canvas, lokasi gambar akan ditampilkan
- `w, h` adalah lebar dan tinggi dari gambar yang akan ditampilkan


### Transformasi

- `ctx.scale(x, y)` merubah ukuran objek saat ini
- `ctx.rotate(angle)` merubah arah objek saat ini
- `ctx.translate(x, y)` merubah posisi objek saat ini