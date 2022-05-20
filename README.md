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
![image](https://user-images.githubusercontent.com/105660616/169559459-3a7e3e8d-1b47-4ac9-90a7-fc785586b3e3.png)
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
![image](https://user-images.githubusercontent.com/105660616/169563707-5aac5ea4-77a7-4236-bbe3-28a47176b849.png)

**🔍 _Upstream (Forward Time, Forward/Back Space_)**
Penyempurna metode leapfrog yang dibuat untuk model positif. Dalam pendekatan menggunakan beda maju untuk turunan waktu dan turunan ruang berpacu pada arah kecepatan u
U, dimana :
U > 0, turunan ruang dengan beda mundur
U < 0 digunakan pendekatan beda maju untu turunan ruang
![image](https://user-images.githubusercontent.com/105660616/169564064-37ebb40a-9bef-4517-a20b-08c295237751.png)

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

∂ζ/∂t+H ∂u/∂x=0 --> Persamaan Kontinuitas

∂u/∂t+g ∂ζ/∂x=0 --> Persamaan Momentum

Dimana, persamaan pengatur ini mempunyai arti fisis yaitu u merupakan kecepatan sesaat (m/s), ζ adalah elevasi (m), ∂ adalah total (m), H adalah kedalaman terukur (m) yang konstan terhadap ruang, dan g adalah koefisien gravitasi bumi (m²/s). Persamaan hidrodinamika sederhana ini dapat di diskretisasi secara ekplisit dengan metode FTCS beda maju untuk waktu (t) dan beda pusat untuk ruang (x).

- Persamaan Diskretisasi
Persamaan kontinuitas dan persamaan momentum dengan Metode FTCS

![Screenshot (919)](https://user-images.githubusercontent.com/105702913/169481690-ad3449e2-daeb-4217-9837-004ea55f991f.png)

Diskretisasi numerik persamaan hidrodinamika 1 dimensi secara eksplisit harus mempunyai kriteria stabilitas Courant-Freiderichs-Lewy (CFL) sebagai berikut:

![Screenshot (918)(1)](https://user-images.githubusercontent.com/105702913/169482788-09464d8c-c118-4bde-a23f-9a37361ff072.png)

Dari kedua persamaan tersebut, nantinya akan dilakukan penyelesaian secara analitik sehingga memberikan nilai elevasi secara sinusoidal dan solusi analitik kecepatan; dimana nantinya akan menghasilkan nilai awal dan syarat batas pemodelan hidrodinamika. 

**2.2.3 Contoh Model Hidrodinamika 1 Dimensi**

Dalam model hidrodinamika 1 dimensi (modul 3) nantinya akan mempelajari mengenai sifat-sifat penjalaran fenomena oseanografi terkait gelombang pasang surut dan memahami model kaitannya dengan stabilitas numerik dengan metode eksplisit. Model hidrodinamika dalam air laut dapat digunakan untuk mengkaji disipasi panas di laut, sebaran radionuklida yang terlepas ke badan air laut, serta untuk pengkajian klimatologi laut, Meneliti konsentrasi unsur kimia di perairan terhadap kedalaman; dapat juga memodelkan mengenai tumpahan minyak (_oil spill_) di perairan terhadap luasan laut. Sedangkan, dalam model hidrodinamika 2 dimensi (modul 4) dapat digunakan untuk memodelkan gelombang karena angin, memodelkan sampah plastik di laut, memodelkan coastal dynamics dan sedimentasi di Pantai.

Dalam model 3, dilakukan untuk mensimulasikan elevasi muka air laut dan arus yang dipengaruhi oleh beberapa parameter. Pada praktikum kali ini, hasil dari pemodelan hidrodinamika 1 dimensi adalah grafik pemodelan perubahan kecepatan arus terhadap ruang, perubahan kecepatan arus terhadap waktu, perubahan elevasi permukaan air terhadap ruang, dan perubahan elevasi permukaan air terhadap waktu. Ketika memodelkan keempat kasus tersebut adanya parameter yang dikaji yaitu kecepatan arus dan elevasi permukaan air dan anomali.	Anomali sering kali ditemukan dalam melakukan pemodelan oseanografi atau pemodelan lainnya. Anomali merupakan penyimpangan dari keadaan normal dalam suatu lingkungan. Anomali suatu nilai dapat dikarenakan adanya perubahan pada jangka waktu ketika terjadinya kenaikan atau penurunan nlai karena faktor perubahan musim, curah hujan, badai, dan angin siklon sehingga mampu mengubah nilai pada parameter dan berdampak pada hasil dari pemodelan yang berbeda. Anomali dalam grafik terlihat dari ketidakstabilan grafik di setiap grid.

**a).Grafik 1**
![Grafik 1 Perubahan Kecepatan Arus (2)](https://user-images.githubusercontent.com/105702913/169355176-43cbee1c-d14e-4c48-a4d2-058079e6692e.png)

**b).Grafik 2**
![Grafik 2 Perubahan Elevasi Muka air (2)](https://user-images.githubusercontent.com/105702913/169355283-f0df2609-93fa-4a93-8b21-930428dce19e.png)

**c).Grafik 3**
![Grafik 3 Perubahan Kecepatan arus (2)](https://user-images.githubusercontent.com/105702913/169355425-3db37fa4-d723-4b10-aec9-c0994e45b8ae.png)

**d).Grafik 4**
![Grafik 4 Perubahan Elevasi Muka air (2)](https://user-images.githubusercontent.com/105702913/169355512-c401c14c-9b10-4f32-a167-333b85ab3eb0.png)

Kesimpulan dari keempat grafik tersebut sangat dipengaruhi oleh _boundary_. Nilai amplitudo dan kedalaman juga sangat berpengaruh terhadap nilai yang dihasilkan. amplitudo yang tinggi berakibat pada kecepatan dan elevasi permukaan air yang lebih besar pula. Perairan yang memiliki kedalaman besar akan cenderung memiliki kestabilan yang tinggi karena tidak dipengaruhi oleh oleh gesekan dasar. Sementara itu, pada kedalaman yang rendah akan membentuk pola ketidakstabilan akibat adanya gesekan dasar perairan. 

Dalam model 4, dilakukan untuk memodelkan peristiwa gelombang laut di suatu perairan yang dipengaruhi oleh beberapa parameter. Pada praktikum kali ini, hasil dari pemodelan hidrodinamika 2 dimensi adalah grafik parameter oseanografi yang mempengaruhi gelombang setiap pergantian waktu. Ketika memodelkan kasus tersebut adanya parameter yang dikaji yaitu tekanan (_pressure_), kecepatan angin (_wind speed_), arah angin (_wind direction_), dan suhu perairan (_water temperature_) dan anomali.	Anomali sering kali ditemukan dalam melakukan pemodelan oseanografi atau pemodelan lainnya. Anomali merupakan penyimpangan dari keadaan normal dalam suatu lingkungan. Anomali suatu nilai dapat dikarenakan adanya perubahan pada jangka waktu ketika terjadinya kenaikan atau penurunan nlai karena faktor perubahan musim, curah hujan, badai, dan angin siklon sehingga mampu mengubah nilai pada parameter dan berdampak pada hasil dari pemodelan yang berbeda. Anomali dalam grafik terlihat dari grafik yang putus-putus dan adanya kekosongan pada grafik.

**Grafik**
![Hasil modul 4 (1)](https://user-images.githubusercontent.com/105702913/169522601-39369da4-0dff-432b-a403-9d48569a6df1.png)

Kesimpulan dari grafik tersebut dapat dilihat dari adanya korelasi antar parameter kecepatan angin, arah angin, suhu perairan. Menurut Suhanda _et al._(2021), gradien tekanan dapat memengaruhi distribusi angin dan suhu. Dengan kata lain, gradien tekanan yang berbeda dapat menyebabkan bertiupnya angin yang merupakan faktor utama penyebab gelombang laut. arus yang dihasilkan oleh angin membawa massa air bersuhu tinggi bergerak dari tekanan tinggi ke tekanan rendah. Selanjutnya, hubungan antara suhu dan gradien tekanan berbanding terbalik. Hal tersebut dijelaskan pada Haryanto _et al_.(2020), yang menjelaskan bahwa massa udara bergerak dari wilayah yang memiliki suhu lebih rendah dan memiliki tekanan yan lebih tinggi begitu pula sebaliknya.  

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

Contoh penerapan : meneliti konsentrasi unsur kimia di perairan A, ketika memodelkan dalam skema 1 dimensi maka akan memodelkan terhadap kedalaman nya saja (1 arah); tetapi kita ingin meniliti unsur kimia berdasarkan kedalaman dan luas nya (2 arah) misalkan dari panjang alirannya dan berapa kedalamannya lalu meninjau konsentrasi unsur kimianya maka diperlukan skema 2 dimensi. Contoh lainnya ketika meneliti _oil spil_ (tumpahan zat di laut) namun ketika meninjau nya di 1 titik aja itu hanya perlu memodelkan menggunakan skema 1 dimensi; namun ketika adanya perbedaan ketinggian topografi maka dapat memodelkan menggunakan skema 2 dimensi


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
