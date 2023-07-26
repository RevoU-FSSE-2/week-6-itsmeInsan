[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/nj7iw4Wb)
# TUGAS WEEK 6
Tugas minggu ini adalah menjalankan node.js di dalam container docker.
### Hal-hal yang diperlukan
1. install [docker](https://www.docker.com/products/docker-desktop/)
2. node.js [github](https://gist.github.com/berdoezt/e51718982926f0caa3fcd8ed45111430)

Langkah-langkahnya sebagai berikut.
1. Pertama unduh file dockernya. ![Screenshot download docker](screenshot/Screenshot%20(128).png) File dockernya sekitar 500mb.
2. Install docker. click file docker yang sudah diunduh. maka akan muncul seperti ini. ![screenshot install docker](screenshot/Screenshot%20(129).png) Jika sudah selesai maka akan muncul seperti ini. ![screenshot selesai install docker](screenshot/Screenshot%20(131).png) Jika sudah, restart laptop. Selesai restart harap melihat version dockernya. Berikut version docker saya. ![screenshot versi docker](screenshot/Screenshot%20(132).png)
3. Kemudian click docker yang sudah diinstall. Berikut tampilan awalnya ![screenshot tampilan awal docker](screenshot/Screenshot%20(133).png) REMINDER untuk pengguna windows harap update wslnya. Sebagai berikut ![screenshot update wsl](screenshot/Screenshot%20(135).png)
4. Sign up akun [docker](https://hub.docker.com/signup)nya ![screenshot signup docker](screenshot/Screenshot%20(140).png)
5. login akun dockernya ![screenshot login akun docker](screenshot/Screenshot%20(139).png) jika berhasil login akan muncul sepert ini ![screenshot login berhasil](screenshot/Screenshot%20(143).png) Kembali ke app docker.
6. Membuat folder baru untuk penyimpanan filenya. Setelah itu clone foldernya dengan github anda. Jika sudah buka vs code.
7. Membuat file docker di [vscode](https://code.visualstudio.com/) klik new file -> ketik dockerfile . Jika sudah isi file docker sebagai berikut

```
FROM node:18-alpine
WORKDIR /app
COPY . /app
RUN npm install 
EXPOSE 3001
CMD ["node", "app.js"]
```
FYI baris pertama FROM node:18-alpine. Saya mendefinisikan format image yang akan dibuat. Sekarang saya menggunakan LTS node versi 18 yang available di docker. kemudian baris kedua WORKDIR atau work directory file code atau tempat penyimpanannya. setelah itu ada copy untuk mengcopy source code ke file image. kemudian ada run NPM install, untuk menginstall node.js dan npm ke dalam image. kemudian Expose untuk membuat portnya. terakhir ada CMD["node", "app.js"] mejalankan app dengan format node dan mejalankan source code yang bernama app.js yang sudah dicoding.

8. Membuat file package.json . Saya membuat dengan new file -> kemudian berinama "package.json" setelah itu saya isi dengan source code
```
 {
    "name": "hello-node.js",
    "version": "1.0.0",
    "description": "Node.js on Docker",
    "author": "faqqihfiddin",
    "main": "app.js",
    "scripts": {
      "start": "node app.js"
    },
    "dependencies": {
      "express": "^4.18.2"
    }
  }
```
9. Build image. caranya -> terminal -> docker build . -t namausername/nama-web-apps ![screenshot build image](screenshot/Screenshot%20(153).png)
10. Cek imagenya. apa sudah ada di local host atau belum![screenshot cek image](screenshot/Screenshot%20(154).png)
11. Cek image sudah diinstall atau belum
```
docker ps
```
![screenshot cek image sudah jalan di local host atau belum](screenshot/Screenshot%20(157).png)
Berikut tampilan image sudah berhasil di dalam local host.
![screenshot image sudah di dalam local host](screenshot/Screenshot%20(155).png)
12. Berikut node.js sudah berhasil run di dalam container docker.
![screenshot node.js berhasil](screenshot/Screenshot%20(156).png)

### SELESAI