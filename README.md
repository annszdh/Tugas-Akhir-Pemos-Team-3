# Tugas Akhir Pemos Team 3
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Pemodelan Oseanografi 2022. Repositori ini memuat executable (.exe) file yang dapat memproses beberapa persamaan model hidrodinamika untuk penyelesaian dalam pemodelan dari suatu fenomena atau dinamika oseanografi.
Pengerjaan untuk repositori kali ini menggunakan bahasa pemrograman python yang dapat dilakukan pada beberapa platform seperti Google Colaboratory dan Jupyter Notebook. Sedangkan untuk library yang digunakan kali ini adalah Numpy, Matplotlib, dan Pprint. Seluruh script yang dibuat adalah hasil Team 3 Oseanografi 2020. Semoga dapat bermanfaat!

# 1. AUTHORS of TEAM 3 👥
1. Hanna Sazidah 26050120120002 A
2. Sinta Dwi Rosalia 26050120120019 A
3. Savira Aulia Zahra 26050120140154 B
4. Bussan Adi Nugroho 26050120130100 A
5. Fani Melisa 26050120140090 B
6. Yosefa Pramudita 26050120140151 B
7. Adzkia Fara Ananda 26050120120014 A

# 2. Teori Dasar 📝📝
**📌 2.1. Adveksi Difusi**

Dalam melakukan suatu pemodelan pasti mempunyai dasar dari persamaannya, salah satunya menggunakan persamaan pengatur yaitu persamaan adveksi, difusi, dan adveksi-difusi.

**- Persamaan Adveksi**

Persamaan adveksi termasuk ke dalam persamaan gelombang linear orde satu dan termasuk dalam persamaan differensial hiperbolik yang menggambarkan mekanisme transportasi suatu gas atau zat cair dengan arah tertentu. Adveksi menjelaskan tentang mekanisme perpindahan materi dari titik satu ke titik lainnya. 

![image](https://user-images.githubusercontent.com/105660616/169559068-073bbed3-683a-4f8a-9387-3a91b029c2ea.png)
![Screenshot (878)](https://user-images.githubusercontent.com/105702913/169316707-ae7dc8b7-24d4-4b99-b190-860125d60f7c.png)

Berdasarkan persamaan diatas, maka deskritisasi model penyelesaian difusi terbagi menjadi 2 metode persamaan dengan pendekatan beda hingga sesuai yaitu metode eksplisit dan metode implisit. Dalam hal ini terdapat perbedaan dari kedua metode tersebut, yaitu: 
![ss aja (2)](https://user-images.githubusercontent.com/105660616/169561870-b770f079-56be-4f35-9ab8-9666a1836ad3.png)

Pendekatan dalam metode ini terdiri atas FTCS (_Forward in Time Central in Space), Leapfrog/CTCS (Center Time Center Space),_ dan _Upstream (Forward Time, Forward/Back Space)_

**🔍 FTCS (_Forward in Time Central in Space_)**

Gabungan beberapa pendekatan beda hingga, dimana :
Turunan pertama terhadap waktu  dengan beda maju 
Turunan kedua  terhadap ruang dengan beda tengah
Solusi FTCS salah satu solusi yang memiliki syarat kestabilan

![image](https://user-images.githubusercontent.com/105660616/169566493-321dae35-8989-4dff-8e50-c2ccc0829803.png)

**🔍 _Leapfrog/CTCS (Center Time Center Space_)**

Perluasan metode beda tengah terhadap ruang dan waktu, dimana skema yang dalam metode ini didapatkan hasil turunan deret taylor. Skema yang dihasilkan termasuk skemanya konsisten jika C<1.

![image](https://user-images.githubusercontent.com/105660616/169568591-244e0b9f-8089-465f-abf9-37e152e510ac.png)

**🔍 _Upstream (Forward Time, Forward/Back Space_)**

Penyempurna metode leapfrog yang dibuat untuk model positif. Dalam pendekatan menggunakan beda maju untuk turunan waktu dan turunan ruang berpacu pada arah kecepatan u
U, dimana :
U > 0, turunan ruang dengan beda mundur
U < 0 digunakan pendekatan beda maju untu turunan ruang

![image](https://user-images.githubusercontent.com/105660616/169571094-29e223be-cac0-4693-a282-f05848c55c98.png)


**- Persamaan Difusi**

Persamaan difusi termasuk ke dalam persamaan diferensial parsial yang merupakan representasi perpindahan suatu zat dalam pelarut dari bagian konsentrasi tinggi ke konsentrasi rendah tanpa dipengaruhi oleh kecepatan gerak fluida media.

![Screenshot (879)](https://user-images.githubusercontent.com/105702913/169318097-697d436c-157c-4ef4-bacd-ca42ce695cc6.png)

**- Persamaan Adveksi-Difusi**

Persamaan adveksi-difusi merupakan persamaan yang digunakan untuk memodelkan proses transportasi/adveksi dan sekaligus proses difusi. Penerapan model adveksi-difusi dapat diterapkan dalam berbagai masalah nyata, seperti memodelkan kualitas air, polusi udara, meteorologi, dan oseanografi. Dalam penerapan nya dalam mencari solusi analitik yang cukup sulit menggunakan pendekatan metode numerik.Persamaan adveksi-difusi dapat mensimulasikan bagaimana profil suhu perairan yang kemudian didistribusikan dari waktu ke waktu sebagaimana yang dicontohnya pada ilustrasi di atas. 

![Screenshot (880)](https://user-images.githubusercontent.com/105702913/169318937-d8b8053c-f078-4a5b-a61a-90deedd1fd70.png)

**📌 2.2. Model Hidrodinamika**

**2.2.1 Apa itu Model Hidrodinamika?**

Hidro adalah air.
Dinamika adalah benda bergerak atau tenaga yang menggerakan.

Hidrodinamika merupakan salah satu cabang ilmu yang berhubungan dengan gerak liquid atau lebih dikhususkan pada gerak air. Skala atau lingkup analisis ilmu ini adalah pada gerak partikel air atau dapat disebut dalam skala makroskopik. Skala makroskopik disini memiliki maksud air tersusun dari partikel-partikel fluida. Fluida bukanlah partikel dengan skala terkecil, tetapi partikel atomlah yang merupakan partikel skala terkecil di air. Bidang hidrodinamika merupakan aplikasi matematik bukan fisika. Model hidrodinamika adalah model yang disarankan kepada deskripsi proses-proses yang memengaruhi sirkulasi dan pencampuran massa air. Pembangun nya yaitu hukum konservasi massa dan hukum kekelan momentum. Model ini dapat mensimulasikan variasi tinggi muka air laut dan aliran arus yang dibangkitkan oleh parameter angin, pasang surut, gelombang laut, debit perairan, dan lain-lain. Permodelan hidrodinamika dapat mensimulasikan gerakan laut dengan memecahkan serangkaian persamaan yang memberikan hubungan antara gerakan fluida, yaitu tiga komponen kecepatan, dan gaya yang bekerja pada fluida, misalnya gaya gravitasi, gaya tekanan, angin dan gaya hambat dasar, dan gaya Coriolis. 

**2.2.2 Persamaan-persamaan Model Hidrodinamika 1 Dimensi**

- Persamaan Pengatur Fluida yaitu persamaan kontinuitas dan momentum

Persamaan Kontinuitas
![image](https://user-images.githubusercontent.com/105660616/169678671-ad04a9f9-e0e9-4e7d-99c9-1c3982dd3672.png)

Persamaan Momentum
![image](https://user-images.githubusercontent.com/105660616/169678691-a40aaf1f-1830-4454-b2b1-abaa8c0e6092.png)

Dimana, persamaan pengatur ini mempunyai arti fisis yaitu u merupakan kecepatan sesaat (m/s), ζ adalah elevasi (m), ∂ adalah total (m), H adalah kedalaman terukur (m) yang konstan terhadap ruang, dan g adalah koefisien gravitasi bumi (m²/s). Persamaan hidrodinamika sederhana ini dapat di diskretisasi secara ekplisit dengan metode FTCS beda maju untuk waktu (t) dan beda pusat untuk ruang (x).

- Persamaan Diskretisasi
Persamaan kontinuitas dan persamaan momentum dengan Metode FTCS

![Screenshot (919)](https://user-images.githubusercontent.com/105702913/169481690-ad3449e2-daeb-4217-9837-004ea55f991f.png)

Diskretisasi numerik persamaan hidrodinamika 1 dimensi secara eksplisit harus mempunyai kriteria stabilitas Courant-Freiderichs-Lewy (CFL) sebagai berikut:

![image](https://user-images.githubusercontent.com/105660616/169679662-99241b2b-5855-4e1b-a2d1-cdc57c2fd9fe.png)

Dari kedua persamaan tersebut, nantinya akan dilakukan penyelesaian secara analitik sehingga memberikan nilai elevasi secara sinusoidal dan solusi analitik kecepatan; dimana nantinya akan menghasilkan nilai awal dan syarat batas pemodelan hidrodinamika. 

**2.2.3 Contoh Hasil Pemodelan Oseanografi**

Dalam pemodelan oseanografi dilakukan untuk mensimulasikan suatu dinamika dan fenomena yang terjadi dalam bidang oseanografi dan kelautan. Pemodelan didasarkan kepada beberapa **parameter dan anomali**. 

**Parameter** merupakan ukuran suatu keadaan secara relatif. Parameter berguna dalam menentukan analisis dan mengidentifikasi suatu sistem atau model. 

**Anomali** merupakan penyimpangan dari keadaan normal dalam suatu lingkungan. Anomali suatu nilai dapat dikarenakan adanya perubahan pada jangka waktu ketika terjadinya kenaikan atau penurunan nlai karena faktor perubahan musim, curah hujan, badai, dan angin siklon sehingga mampu mengubah nilai pada parameter dan berdampak pada hasil dari pemodelan yang berbeda. Anomali dalam grafik terlihat dari ketidakstabilan grafik di setiap grid.

**Hasil _Output_ Pemoodelan 🖥️**
**a).Grafik 1**
![Grafik 1 Perubahan Kecepatan Arus (2)](https://user-images.githubusercontent.com/105702913/169355176-43cbee1c-d14e-4c48-a4d2-058079e6692e.png)

**b).Grafik 2**
![Grafik 2 Perubahan Elevasi Muka air (2)](https://user-images.githubusercontent.com/105702913/169355283-f0df2609-93fa-4a93-8b21-930428dce19e.png)

**c).Grafik 3**
![Grafik 3 Perubahan Kecepatan arus (2)](https://user-images.githubusercontent.com/105702913/169355425-3db37fa4-d723-4b10-aec9-c0994e45b8ae.png)

**d).Grafik 4**
![Grafik 4 Perubahan Elevasi Muka air (2)](https://user-images.githubusercontent.com/105702913/169355512-c401c14c-9b10-4f32-a167-333b85ab3eb0.png)

**e.) Grafik 5**
![Hasil modul 4 (1)](https://user-images.githubusercontent.com/105702913/169522601-39369da4-0dff-432b-a403-9d48569a6df1.png) 

**2.2.4 Perbedaan Model Hidrodinamika 1 Dimensi dan 2 Dimensi**

![1D vs  2D](https://user-images.githubusercontent.com/105702913/169360716-ce873920-c909-4566-8856-84ebcb545b65.png)

Konsep Hidrodinamika 1 Dimensi vs. 2 Dimensi, adalah sebagai berikut.
1. Hidrodinamika 1 dimensi
- Sebuah penampang diambil tegak lurus terhadap aliran sungai (x)
- Water level seragam di seluruh penampang karena tidak dipengaruhi oleh kedalaman
- Kecepatan arus dan gelombang seragam melitasi penampang
- Kemiringan rendah

2. Hidrodinamika 2 dimensi
- Daerah yang direpresentasikan sebagai permukaan kontinu (x,y)
- Water level di seluruh penampang tidak pernah sama karena kedalaman
- Kecepatan dari arus dan gelombang tidak pernah sama saat melintasi penampang
- Kemiringan terjal


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
1. Modul 2 : Adveksi Difusi 2D
2. Modul 3 : Model Hidrodinamika 1D
3. Modul 4 : Model Hidrodinamika 2D

**📌 4.1. Adveksi Difusi 2D**

1. Buka laman _jupyter notebook_, kemudian pilih _new pyhton 3_ untuk membuat script
![image](https://user-images.githubusercontent.com/105660616/169575203-41673726-0802-48cd-9562-83cce2747e62.png)
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

1. Buka _**Anaconda prompt** (Miniconda 3)_ yang sudah di unduh sebelumnya.
![image](https://user-images.githubusercontent.com/105660616/169584779-2bc7e183-dbe9-4fd6-aef0-ef073d321db6.png)
2. _Install_ terlebih dahulu _mandatory library_ yang digunakan yaitu _**Matplotlib**_ dan _**Siphon**_ dengan menuliskan _**pip install Matplotlib**_ dan _**pip install Siphon**_.
![image](https://user-images.githubusercontent.com/105660616/169585224-3bb39d56-3d09-4fc4-84a0-3acf7e2ec5ac.png)
3. Setelah _**Matplotlib**_ dan _**Siphon**_ _terinstall_, buka _jupyter notebook_ atau _text editor lainnya_ 
![image](https://user-images.githubusercontent.com/105660616/169586358-c123031f-9e46-41c4-8040-9c4fa878d506.png)
4. Setelah laman _jupyter notebook_ terbuka, kemudian pilih _new python 3_ untuk membuat _script python_ yang akan digunakan dalam pemodelan.
![image](https://user-images.githubusercontent.com/105660616/169586505-fdd23d0a-6ba3-485a-98a3-5ff1f35c2362.png)
5. Setelah itu, ketik _script python_ yang akan dijalankan, _import_ juga data _**import matplotlib**_ dan _**import NDBC**_ dari _Siphon_.
![image](https://user-images.githubusercontent.com/105660616/169586719-5f3bf9e1-13c2-467b-856e-84b207b07bbf.png)
6. Tulis _data frame_ yang akan dibuat berdasarkan data dari _website_ NDBC _(National Data Bouy Center)_ dengan data observasi _realtime_. Pada bagian _Station ID_ ubah _script_ sesuai dengan _Station ID_ yang akan dimodelkan.
![image](https://user-images.githubusercontent.com/105660616/169586882-38641ab0-978e-4aa7-a0f1-5201e3a56baf.png)
7. Langkah selanjutnya, masukan _time series plot_ dari gambar grafik yang akan dijadikan _outputnya_. Sesuaikan ukuran gambar agar hasil grafik terlihat jelas.
![image](https://user-images.githubusercontent.com/105660616/169587027-2b8afdd2-ea97-4bf7-b70d-ac59df317fa6.png)
8. Tambahkan grafik parameter gelombang yang akan dianalisa meliputi tekanan (_presurre_), angin (_wind speed, gust, and direction_), dan suhu (_water temperature_) dengan cara menuliskan _plot_ yang sesuai dengan_data frame_. Sesuaikan juga ukuran dan warna dari masing-masing parameter serta pada kolom nama diubah menjadi Nama_NIM_Kelas.
![image](https://user-images.githubusercontent.com/105660616/169579069-767e1e87-d547-4fea-9933-93bf0c7f043a.png)
9. Tampilkan hasil _script_ dengan menggunakan _directory matplotlib plt_.
![image](https://user-images.githubusercontent.com/105660616/169587303-c33c10d9-68c8-4e4c-8341-f1992ffabf48.png)
10. Setelah itu, _run script_ yang sudah disesuaikan dengan _Station ID_. Kemudian simpan dan tinjau hasilnya.
![image](https://user-images.githubusercontent.com/105660616/169580310-77c79395-3d61-45ee-b327-d0143fca5958.png)
11. Selanjutnya masuk ke laman _website_ **NDBC-NOAA**, _website_ ini dapat diakses melalui _browser_.
![image](https://user-images.githubusercontent.com/105741300/169331207-226a318d-dea7-414e-8418-6e774f782972.png)
12. Cari lokasi _Station ID_ yang akan ditinjau.
![image](https://user-images.githubusercontent.com/105741300/169331717-40b9520f-8163-4a8a-bd76-3b3dd71259fb.png)
13. Langkah terakhir, lakukan identifikasi mengenai karakteristik hasil parameter pengamatan sesuai _Station ID_. 
![image](https://user-images.githubusercontent.com/105741300/169332430-ff8b57cb-708e-4579-8cd2-3f8078545233.png)
14. Untuk mengetahui anomali yang terjadi pada lokasi _Station ID_, Anda bisa membuka _website Zoom Earth_.
![image](https://user-images.githubusercontent.com/105660616/169581147-848241bb-667e-4880-8ccb-aa15fd9fce14.png)
15. Klik logo _search_ dan pilih lokasi untuk melihat anomali yang terjadi.
![image](https://user-images.githubusercontent.com/105660616/169581451-f2887d44-12a2-4744-9e3b-0d29131d0c0d.png)

# 5. Kegunaan dan Penerapan Script dalam Oseanografi
ini lebih ke penjelasan dari kegunaan dan penerapannya di ose bisa buat apa aja, tambahin kekurangan dan kelebihan dari penggunaan model hidrodinamika

Dalam model hidrodinamika mempelajari mengenai sifat-sifat penjalaran fenomena oseanografi terkait gelombang pasang surut dan memahami model kaitannya dengan stabilitas numerik dengan metode eksplisit. Model hidrodinamika dalam air laut dapat digunakan untuk mengkaji disipasi panas di laut, sebaran radionuklida yang terlepas ke badan air laut, serta untuk pengkajian klimatologi laut, Meneliti konsentrasi unsur kimia di perairan terhadap kedalaman; dapat juga memodelkan mengenai tumpahan minyak (_oil spill_) di perairan terhadap luasan laut (ini pindahan dari yang Zahra tulis)

**📌 5.1. Adveksi Difusi 1 Dimensi**

**📌 5.2. Adveksi Difusi 2 Dimensi**

**📌 5.3. Model Hidrodinamika 1 Dimensi**

**📌 5.4. Model Hidrodinamika 2 Dimensi**

Contoh penerapan model hidrodinamika 2 dimensi dalam oseanografi adalah sebagai berikut :
1. Pemodelan gelombang karena angin
2. Pemodelan _longshore current_ beserta proses sedimentasinya
3. Pemodelan sampah plastik di laut
4. Pemodelan _coastal dynamics_ dan sedimentasi pantai
5. Pemodelan konsentrasi unsur kimia berdasarkan kedalaman dan luasnya
6. Pemodelan _oil spill_ (tumpahan minyak di laut)
7. Pemodelan biota laut

Kelebihan dari model hidrodinamika 2 dimensi adalah sebagai berikut :
1. Data yang didapatkan lebih valid karena dilihat dalam 2 arah (x dan y atau x dan z)
2. Pemodelan yang dihasilkan lebih valid
3. Dapat menghasilkan data yang lebih beragam seperti misalnya perbedaan kecepatan maupun perbedaan topografi
4. Dapat digunakan dalam pemodelan wilayah yang curam
5. Dapat menunjukkan anomali yang terjadi

Kekurangan dari model hidrodinamika 2 dimensi adalah sebagai berikut :
1. Membutuhkan data yang cukup banyak untuk melihat anomali
2. Pengumpulan data memerlukan waktu yang cukup lama
3. Keterbatasan data di beberapa wilayah

# 6. Penutup

**📌 6.1. Kesimpulan**

Pemodelan Oseanografi ini merupakan suatu sistem pembelajaran berbagai fenomena oseanografi dengan persamaan-persamaan diskrit atau numerik. Dalam Praktikum Pemodelan Oseanografi ini dipelajari 4 modul yaitu modul 1 mengenai Adveksi-Difusi 1 Dimensi, modul 2 mengenai Adveksi-Difusi 2 Dimensi, modul 3 mengenai Model Hidrodinamika 1 Dimensi, dan yang terakhir untuk modul 4 mengenai Model Hidrodinamika 2 Dimensi. Pemodelan tersebut diaplikasikan dalam oseanografi melalui diskritisasi program _python_ sehingga akan menghasilkan data parameter atau fenomena oseanografi dalam bentuk skenario maupun grafik.

**📌 6.2. Saran**

1. Tipe pembuatan grafik dapat dikreasikan dari segi ukuran, bentuk, dan warnanya.
2. Jenis fenomena yang dimodelkan dapat ditambahkan lagi di setiap modulnya.
3. Script yang dibuat dapat diberi keterangan lebih lanjut.

**📌 6.3. Ucapan Terima Kasih**

Demikianlah tugas akhir repository ini kami buat. Kami dari kelompok 7 selaku authors memohon maaf apabila masih terdapat kekurangan dan kesalahan. Terimakasih pula kami ucapkan khususnya kepada :
1. Dr. Aris Ismanto, S. Si., M. Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi.
2. Prof. Dr. Denny Nugroho Sugianto, S. T., M. Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi.
3. Dr. Elis Indrayanti, S. T., M. Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi.
4. Rikha Widiaratih, S. Si., M. Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi.
5. Tim asisten Praktikum Pemodelan Oseanografi yang telah membimbing selama keberlangsungan praktikum.
6. Seluruh rekan-rekan Oseanografi 2020 yang turut mendukung tersusunnya repository ini.

# 7. Referensi
Diisi jurnal atau buku semisal mengambil materi dari pustaka
