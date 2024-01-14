## Membangun Web Server dengan NGINX sebagai Reverse Proxy dan Pembatasan Akses

Pada proyek ini, saya berhasil membangun dan mengonfigurasi sebuah web server yang mampu memberikan layanan dengan efisiensi tinggi, menggunakan NGINX sebagai Reverse Proxy Server, dan menerapkan pembatasan akses untuk meningkatkan keamanan. Berikut adalah beberapa langkah - langkah yang saya ambil selama proyek ini:

## update dan install apache2

```bash
sudo apt update
sudo apt install apache2
```

## install nginx

```bash
sudo apt install nginx
```

## Jalankan perintah berikut untuk bisa melihat isi dari berkas yang kita bincangkan tadi

```bash
cat /etc/nginx/sites-available/default
```

Catatan: cat merupakan perintah untuk melihat isi berkas dalam bentuk teks.

## Edit berkas tersebut menggunakan tools nano dengan menjalankan perintah berikut:

```bash
sudo nano /etc/nginx/sites-available/default
```

## Kemudian, tambahkan kode yang diberi tanda tebal berikut pada blok server -> location /.

```bash
	location / {
        	proxy_pass http://localhost:8000;
        	proxy_http_version 1.1;
        	proxy_set_header Upgrade $http_upgrade;
        	proxy_set_header Connection 'upgrade';
        	proxy_set_header Host $host;
        	proxy_cache_bypass $http_upgrade;
 
    		limit_req zone=one;
    	}
```

## Simpan perubahan berkasnya dengan menekan CTRL+X, lalu Y, dan Enter. Usai itu, jalankan ulang NGINX server menggunakan perintah berikut.

```bash
sudo systemctl restart nginx
```

## Selanjutnya, jalankan web server yang kita punya (web server Node.js) dengan perintah berikut.

```bash
cd a387-jarkom-labs/
npm run start
```
