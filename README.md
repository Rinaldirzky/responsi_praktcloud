# Responsi
- Kerjakan dari Website-Profile terlebih Dahulu
## Buat dua direktori: website-utama dan website-profil.
```sh
mkdir website-profil
mkdir website-utama
```
## Masuk kedalam masing" direktori
```sh
cd website-profil
cd website-utama
```
## Buat file index.html (sesuai deskripsi halaman utama).
```sh
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Halaman Utama</title>
    </head>
<body>
    <h1>Data Diri</h1>
    <p>Nama : Rinaldi Rizqi Mulya</p>
    <p>NIM  : 215610065</p>
    <p>Program Studi : Sistem Informasi</p>
    <p>Hobi : Olahraga dan Membaca</p>
    <a href="https://89ba4115-983f-4468-98e1-2e3d36033d60-10-244-8-94-8081.papa.r.killercoda.com/">Profil</a>
</body>
</html>
```
## Buat file index.html (sesuai deskripsi halaman profil).
```sh
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=0">
        <title>Profil</title>
    </head>
    <body>
        <h1>Profil</h1>
        <img src="foto.jpg" alt="Foto Profil" style="width: 200px;">
    </body>
</html>
```
## Membuat Dockerfil di website-profil dan website-utama
```sh
FROM nginx:latest
COPY . /usr/share/nginx/html
EXPOSE 80
```
## Di dalam website-profil, letakkan file gambar profil Anda (foto.jpg).
```sh
wget -O ~/website-profil/foto.jpg "https://drive.google.com/uc?export=download&id=1hggSYhlmQneVDGUBXmD0HWptz1LZn5Y-"
```
## Membuat network my-namamahasiswa-network
```sh
docker network create my-rinaldi-network
```
## Build Image website-profil dan website-utama
```sh
docker build -t website-profil .
docker build -t website-utama . 
```
## Jalankan Container Website-Utama
```sh
docker run -d --name website-profil --network my-rinaldi-network -p 8081:80 website-profil
```
## Jalankan Container Website-Utama
```sh
docker run -d --name cont_utama --network my-rinaldi-network -p 8080:80 website-utama 
```
# Hasil Saat Dijalankan
- Website-Utama
![image](https://github.com/Rinaldirzky/responsi_praktcloud/assets/147987091/e78d5e50-b876-4500-8c0b-c5659291be63)
- Website-Profil
![Screenshot_3](https://github.com/Rinaldirzky/responsi_praktcloud/assets/147987091/79ac18bc-5b5e-4074-b08c-5729b2139b0f)


