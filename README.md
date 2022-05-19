# Tugas Akhir Pemos Team 3
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Pemodelan Oseanografi 2022. Repositori ini memuat executable (.exe) file yang dapat memproses beberapa persamaan model hidrodinamika untuk penyelesaian dalam pemodelan dari suatu fenomena atau dinamika oseanografi.
Pengerjaan untuk repositori kali ini menggunakan bahasa pemrograman python yang dapat dilakukan pada beberapa platform seperti Google Colaboratory dan Jupyter Notebook. Sedangkan untuk library yang digunakan kali ini adalah Numpy, Matplotlib, dan Pprint. Seluruh script yang dibuat adalah hasil Team 3 Oseanografi 2020. Semoga dapat bermanfaat!

# 1. AUTHORS of TEAM 3
1. Hanna Sazidah 26050120120002 A
2. Sinta Dwi Rosalia 26050120120019 A
3. Savira Aulia Zahra 26050120140154 B
4. Bussan Adi Nugroho 26050120130100 A
5. Fani Melisa 26050120140090 B
6. Yosefa Pramudita 26050120140151 B
7. Adzkia Fara Ananda 26050120120014 A

# 2. Teori Dasar 
**📌 2.1. Adveksi Difusi**

Model hidrodinamika diatur oleh persamaan pengatur yaitu persamaan adveksi, difusi, dan adveksi-difusi
- Persamaan Adveksi 

Persamaan adveksi termasuk ke dalam persamaan gelombang linear orde satu dan termasuk dalam persamaan differensial hiperbolik yang menggambarkan mekanisme transportasi suatu gas atau zat cair dengan arah tertentu

![Screenshot (878)](https://user-images.githubusercontent.com/105702913/169316707-ae7dc8b7-24d4-4b99-b190-860125d60f7c.png)

- Persamaan Difusi

Persamaan difusi termasuk ke dalam persamaan diferensial parsial yang merupakan representasi perpindahan suatu zat dalam pelarut dari bagian konsentrasi tinggi ke konsentrasi rendah tanpa dipengaruhi oleh kecepatan gerak fluida media.

![Screenshot (879)](https://user-images.githubusercontent.com/105702913/169318097-697d436c-157c-4ef4-bacd-ca42ce695cc6.png)

- Persamaan Adveksi-Difusi

Persamaan adveksi-difusi merupakan persamaan yang digunakan untuk memodelkan proses transportasi/adveksi dan sekaligus proses difusi. Penerapan model adveksi-difusi dapat diterapkan dalam berbagai masalah nyata, seperti memodelkan kualitas air, polusi udara, meteorologi, dan oseanografi. Dalam penerapan nya dalam mencari solusi analitik yang cukup sulit menggunakan pendekatan metode numerik.

![Screenshot (880)](https://user-images.githubusercontent.com/105702913/169318937-d8b8053c-f078-4a5b-a61a-90deedd1fd70.png)

**📌 2.2. Model Hidrodinamika**

- Apa itu Model Hidrodinamika?

Hidrodinamika merupakan salah satu cabang ilmu yang berhubungan dengan gerak liquid atau lebih dikhususkan pada gerak air. Skala atau lingkup analisis ilmu ini adalah pada gerak partikel air atau dapat disebut dalam skala makroskopik. Skala makroskopik disini memiliki maksud air tersusun dari partikel-partikel fluida. Fluida bukanlah partikel dengan skala terkecil, tetapi partikel atomlah yang merupakan partikel skala terkecil di air. Bidang hidrodinamika merupakan aplikasi matematik bukan fisika. Model hidrodinamika adalah model yang disarankan kepada deskripsi proses-proses yang memengaruhi sirkulasi dan pencampuran massa air. Pembangun nya yaitu hukum konservasi massa dan hukum kekelan momentum. Model ini dapat mensimulasikan variasi tinggi muka air laut dan aliran arus yang dibangkitkan oleh parameter angin, pasang surut, gelombang laut, debit perairan, dan lain-lain.

- Persamaan-persamaan Model Hidrodinamika 1 Dimensi

- Contoh Model Hidrodinamika 1 Dimensi

Dalam model hidrodinamika 1 dimensi nantinya akan mempelajari mengenai sifat-sifat penjalaran fenomena oseanografi terkait gelombang pasang surut dan memahami model kaitannya dengan stabilitas numerik dengan metode eksplisit. Model hidrodinamika dalam air laut dapat digunakan untuk mengkaji disipasi panas di laut, sebaran radionuklida yang terlepas ke badan air laut, serta untuk pengkajian klimatologi laut, Meneliti konsentrasi unsur kimia di perairan terhadap kedalaman; dapat juga memodelkan mengenai tumpahan minyak (_oil spill_) di perairan terhadap luasan laut. Pada praktikum kali ini, contoh dari pemodelan hidrodinamika 1 dimensi adalah memodelkan perubahan kecepatan arus terhadap ruang, perubahan kecepatan arus terhadap waktu, perubahan elevasi permukaan air terhadap ruang, dan perubahan elevasi permukaan air terhadap waktu. Ketika memodelkan keempat kasus tersebut adanya parameter yang dikaji dan anomali. 

- Perbedaan Model Hidrodinamika 1 Dimensi dan 2 Dimensi

sebelum ke metodenya jelasin dulu soal pengertian Model Hidrodinamika, dasar simulasi model (parameter dan anomali jelasin), persamaan persamaan dan perbedaan model hidrodinamika 1D dan 2D (dikerjain sama 2 orang)

# 3. _Installasi Miniconda 3_ 
Pembuatan Script Pyhton dapat dilakukan dengan menggunakan Miniconda atau menggunakan Google Colaboratory. Setup Miniconda dapat diunduh pada File Terlampir
Adapun langkah instalasi miniconda sebagai berikut :
1. Pengguna dapat mengunduh **setup miniconda** terlebih dahulu kemudian dilakukan instalasi
![1](https://user-images.githubusercontent.com/76476526/169210880-481f7e89-8f5f-49e5-a9f0-aa84c69193eb.png)
2. Kemudian _setup_ di klik hingga muncul jendela _installer_ dan dipilih _next_
![2](https://user-images.githubusercontent.com/76476526/169211002-36ce5bda-f41d-4a1c-8629-06a9c2bbbf91.PNG)
3. Kemudian dilih _I agree_ pada jendela berikutnya sebagai bukti persetujuan pada instalasi program
![3](https://user-images.githubusercontent.com/76476526/169211154-ace3dfea-ec5d-4ed7-88fb-3ec480231af5.PNG)
4. Selanjutnya dipilih _just me_ pada jendela selanjutnya jika penggunaan hanya untuk pribadi
![4](https://user-images.githubusercontent.com/76476526/169211256-4cdc9d38-1edc-4163-bda2-be5fb8f24b7f.PNG)
5. Setelah itu _directory setup_ dipilih atau menyesuaikan dengan yang direkomendasikan oleh sistem dan dipilih _next_
![5](https://user-images.githubusercontent.com/76476526/169211344-01ad1182-f706-4b27-828f-76850aac6116.PNG)
6. Setelah itu dipilih _install_ pada pilihan berikutnya dan tunggu hingga proses instalasi selesai
![6](https://user-images.githubusercontent.com/76476526/169211430-ccf5f67d-88a8-4053-82e7-3e9309696217.PNG)
![7](https://user-images.githubusercontent.com/76476526/169211509-9c3adb74-4b8d-487b-8d15-70ea6bddd1a7.PNG)
7. Setelah proses instalasi selesai kemudian dipilih _next_ pada bagian bawah jendela
![8](https://user-images.githubusercontent.com/76476526/169211633-fc6adfb8-5c76-4821-a66c-e9181e6d2b24.PNG)
8. Pada jendela berikutnya dipilih _finish_ setelah itu laptop dapat dilakukan _restart_ atau langsung digunakan
![9](https://user-images.githubusercontent.com/76476526/169211679-3c04f8ac-65cc-4032-970b-6f28992c3356.PNG)
10. Setelah itu, pengguna dapat membuka **Anaconda Prompt** untuk membuka **_jupyter notebook_**
![1](https://user-images.githubusercontent.com/76476526/168938548-9f5fcaeb-66ec-4aa1-9d76-a03874283c4f.png)
11. Kemudian dilakukan instalasi **Jupyterlab** dengan perintah **_pip install jupyterlab_** kemudian enter. _Library_ _**siphon**_ sudah masuk dalam instalasi namun apabila ingin melakukan instalasi kembali dapat dilakukan dengan perintah _**pip install siphon**_ atau **_ conda install siphon_**
![13](https://user-images.githubusercontent.com/76476526/169211855-0aa39807-e870-438f-b671-2703411d41b5.PNG)
12. Setelah itu, dilakukan instalasi **Library Matplotlib** dengan perintah _**pip install matplotlib**_  atau dengan perintah _**conda install matplotlib**_kemudian enter
![12](https://user-images.githubusercontent.com/76476526/169213321-e6e37ce4-10be-40d7-bbbe-6a058a935b71.PNG)
13. Setelah itu, dilakukan instalasi **Library Numpy** dengan perintah _**pip install numpy**_  atau dengan perintah _**conda install numpy**_kemudian enter
![22](https://user-images.githubusercontent.com/76476526/169213723-008394bd-5201-4319-a5cd-5e2d3932d73e.PNG)


# 4. Metode Pengerjaan
step by step maksud script modul 3 (flowchart dan script python yang digunakan mulai dari persamaan hidrodinamikanya, persamaan pembangun, persamaan transport, diskretitasi, penyelesaian analitik). bagian ini cara nulisnya sama kaya yang contoh asisten kirim. (dikerjain sama 3 orang)

1. Modul 2 : Adveksi Difusi 2D
2. Modul 3 : Model Hidrodinamika 1D
3. Modul 4 : Model Hidrodinamika 2D

**📌 4.1. Adveksi Difusi 2D**

1. Buka laman _jupyter notebook_, kemudian pilih _new pyhton 3_ untuk membuat script
![image](https://user-images.githubusercontent.com/105741300/169244169-ad063e33-0c5d-4ffc-bfb9-5e65790fe393.png)
2. Setelah itu lakukan **import library python matploblib**, **numpy**, dan **sys**
![image](https://user-images.githubusercontent.com/105741300/169255244-e1b50ab2-a52c-4322-adc2-274199f832f8.png)
3. Langkah selanjutnya masukan parameter persebaran polutan yang akan digunakan
![image](https://user-images.githubusercontent.com/105741300/169245860-8eb49961-1fac-436a-ad41-66c719b79c5b.png)
4. Kemudian dibuat _script_ perhitungan untuk mengetahui persebaran polutan
![image](https://user-images.githubusercontent.com/105741300/169246416-32b33897-5f23-4d2d-aab0-a8839ec3b67e.png)
5. Setelah itu membuat _script_ untuk membuatan _grid dari persebaran polutan
![image](https://user-images.githubusercontent.com/105741300/169247085-4979a547-7888-408f-8e68-e516ba98ca78.png)
6. Selanjutnya melakukan iterasi sampai semua syarat batas terpenuhi
![image](https://user-images.githubusercontent.com/105741300/169248728-7d6f022d-eda6-43a5-9ad1-4bd6acef288d.png)
7. Langkah berikutnya membuat _script_ untuk _output_ gambar penyebaran polutan 
![image](https://user-images.githubusercontent.com/105741300/169250267-e66e1089-cf64-47c8-9a0f-e1eceac3c16f.png)
8. Langkah terakhir klik  _running script_ yang terdapat pada menu
![image](https://user-images.githubusercontent.com/105741300/169250673-f9439955-97ad-45bf-bed9-78e5f07a7892.png)

**📌 4.2. Model Hidrodinamika 1D**

1. Buka laman _jupyter notebook_, kemudian dipilih _new phyton 3_ untuk membuat script
![13](https://user-images.githubusercontent.com/76476526/168938644-84a816b9-967b-440c-87a9-ddd69e17463c.PNG)
2. Setelah itu, dilakukan **_import library python matplotlib_** untuk memberikan efek visual berupa grafik dan **_numpy_** untuk perhitungan numerik
![5](https://user-images.githubusercontent.com/76476526/168938673-e9d229be-3649-4da6-9db6-1127555f524e.png)
3. Langkah selanjutnya dimasukkan parameter yang akan digunakan 
![6](https://user-images.githubusercontent.com/76476526/168938702-24782b41-815f-4485-8970-8943018b4d3c.png)
4. Kemudian dibuat _script_ perhitungan 
![7](https://user-images.githubusercontent.com/76476526/168938721-b8bd682a-85f6-42b5-9dc8-a6b6a482a50d.png)
5. Langkah berikutnya membuat script untuk grafik Perubahan Kecepatan Arus Dalam _Grid_ Tertentu di Sepanjang Waktu
![8](https://user-images.githubusercontent.com/76476526/168938751-0614c475-c2c8-4acc-9a8e-13b42711be44.PNG)
6. Selanjutnya dibuat _script_ untuk grafik Perubahan Elevasi Permukaan Air Dalam _Grid_ Tertentu di Sepanjang Waktu
![9](https://user-images.githubusercontent.com/76476526/168938780-a50af0f5-8d0b-4136-a236-4c523dab1b76.PNG)
7. Kemudian dibuat _script_ untuk grafik Perubahan Kecepatan Arus Dalam Waktu Tertentu di sepanjang _Grid_
![10](https://user-images.githubusercontent.com/76476526/168938813-9df167ad-e4bd-4791-b64e-e0967d2840b3.PNG)
8. Berikutnya dibuat _script_ untuk grafik Perubahan Elevasi Permukaan Air Dalam Waktu Tertentu di Sepanjang _Grid_ dan menampilkan hasil grafik secara keseluruhan
![11](https://user-images.githubusercontent.com/76476526/168938845-a05e65ca-e402-4a73-9cd5-b493f00e5c19.PNG)
9. Langkah terakhir _running script_ pada menu _cell_ dan dipilih _running all_
![14](https://user-images.githubusercontent.com/76476526/168939038-dfd3beb2-a039-4777-9f3e-4dee1012870c.PNG)

**📌 4.3. Model Hidrodinamika 2D**

1. Buka **Anaconda prompt** (Miniconda 3) yang sudah di unduh sebelumnya
![image](https://user-images.githubusercontent.com/105741300/169322300-0e28fbeb-28b0-4e0e-9234-deccb9f883bc.png)
2. _Instal_ **siphon** dan **Matplotlib** dengan menuliskan **pip install siphon** dan **pip install Matplotlib**
![image](https://user-images.githubusercontent.com/105741300/169322611-81829675-5403-4ede-9730-1a62fe5dd0c3.png)
3. Setelah **Siphon** dan **Matplotlib** _terinstal_, ketik _jupyter notebook_
![image](https://user-images.githubusercontent.com/105741300/169323277-95c70011-f79c-41db-8e5b-321ddc028c62.png)
4. Setelah laman _jupyter notebook_ terbuka, kemudian pilih _new python 3_ untuk membuat _script_
![image](https://user-images.githubusercontent.com/105741300/169323949-4d802292-1cb3-4fe4-8116-1dde85b94a27.png)
5. Setelah itu, ketik _script_ yang akan dijalankan, _import_ juga data **import matplotlib** dan **import NDBC**, setelah itu masukan nomor stasiun id
![image](https://user-images.githubusercontent.com/105741300/169328662-5e40ab1b-ca60-4522-a3ee-052394263bf6.png)
6. Langkah selanjutnya, masukan rumus dan memasukan nama dengan format nama_nim_kelas
![image](https://user-images.githubusercontent.com/105741300/169329197-dbfece0b-922c-4058-8ef7-fd1345b24613.png)
7. Setelah itu, ketik run untuk menjalankan program dari _script_ yang telah dibuat
![image](https://user-images.githubusercontent.com/105741300/169330101-8efbfa77-3577-4faa-9c59-6350428a4fb9.png)
8. Selanjutnya masuk ke _website_ **NDBC-NOAA**, _website_ ini dapat diakses melalui _browser_ atau _google_
![image](https://user-images.githubusercontent.com/105741300/169331207-226a318d-dea7-414e-8418-6e774f782972.png)
9. Cari lokasi stasiun id sesuai dengan ketentuan yang sudah di tentukan oleh asisten
![image](https://user-images.githubusercontent.com/105741300/169331717-40b9520f-8163-4a8a-bd76-3b3dd71259fb.png)
10. Langkah terakhir, lakukan identifikasi pengamatan sesuai stasiun id yang didapatkan
![image](https://user-images.githubusercontent.com/105741300/169332430-ff8b57cb-708e-4579-8cd2-3f8078545233.png)



# 5. Kegunaan dan Penerapan Script dalam Oseanografi
ini lebih ke penjelasan dari kegunaan dan penerapannya di ose bisa buat apa aja, tambahin kekurangan dan kelebihan dari penggunaan model hidrodinamika

# 6. Penutup
yang kebagian ini berarti otomatis nulis juga bagian kegunaan dan penerapan script (dikerjain sama 1 orang)

# 7. Referensi
Diisi jurnal atau buku semisal mengambil materi dari pustaka
