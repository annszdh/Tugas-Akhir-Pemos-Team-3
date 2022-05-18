# Tugas-Akhir-Pemos-Team-3
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

# 2. Teori Dasar Model Hidrodinamika
Hidrodinamika merupakan salah satu cabang ilmu yang berhubungan dengan gerak liquid atau lebih dikhususkan pada gerak air. Skala atau lingkup analisis ilmu ini adalah pada gerak partikel air atau dapat disebut dalam skala makroskopik. Skala makroskopik disini memiliki maksud air tersusun dari partikel-partikel fluida. Fluida bukanlah partikel dengan skala terkecil, tetapi partikel atomlah yang merupakan partikel skala terkecil di air. Bidang hidrodinamika merupakan aplikasi matematik bukan fisika. Model hidrodinamika adalah model yang disarankan kepada deskripsi proses-proses yang memengaruhi sirkulasi dan pencampuran massa air. Pembangun nya yaitu hukum konservasi massa dan hukum kekelan momentum. Model ini dapat mensimulasikan variasi tinggi muka air laut dan aliran arus yang dibangkitkan oleh parameter angin, pasang surut, gelombang laut, debit perairan, dan lain-lain.

sebelum ke metodenya jelasin dulu soal pengertian Model Hidrodinamika, dasar simulasi model (parameter dan anomali jelasin), persamaan persamaan dan perbedaan model hidrodinamika 1D dan 2D (dikerjain sama 2 orang)

# 3. Pembuatan _Script Python (.ipynb)_
Pembuatan Script Pyhton dapat dilakukan dengan menggunakan Miniconda atau menggunakan Google Colaboratory. Setup Miniconda dapat diunduh pada File Terlampir
Adapun langkah pembuatan script sebagai berikut :
1. Pengguna dapat mengunduh **setup miniconda** terlebih dahulu kemudian dilakukan instalasi
2. Setelah itu, pengguna dapat membuka **Anaconda Prompt** 
![1](https://user-images.githubusercontent.com/76476526/168938548-9f5fcaeb-66ec-4aa1-9d76-a03874283c4f.png)
3. Kemudian dilakukan **instalasi Library Matplotlib** untuk membangun objek visual berupa grafik dan **Numpy** untuk perhitungan numerik
![2](https://user-images.githubusercontent.com/76476526/168938574-708aa546-1df3-4989-9e4d-c5e48f089070.png)
![3](https://user-images.githubusercontent.com/76476526/168938581-59a2e20e-2aec-4276-be7b-43287c58998e.png)
4. Selanjutnya **Anaconda Promp** dibuka dan dilakukan perintah **jupyter notebook** kemudian enter
![4](https://user-images.githubusercontent.com/76476526/168938615-af06021c-3227-4fff-91cf-67ac1b128d24.png)
5. Maka akan muncul laman jupyter notebook kemudian dipilih _new phyton 3_ untuk membuat script
![13](https://user-images.githubusercontent.com/76476526/168938644-84a816b9-967b-440c-87a9-ddd69e17463c.PNG)
6. Setelah itu, dilakukan **import library python matplotlib** dan **numpy**
![5](https://user-images.githubusercontent.com/76476526/168938673-e9d229be-3649-4da6-9db6-1127555f524e.png)
7. Langkah selanjutnya dimasukkan parameter yang akan digunakan 
![6](https://user-images.githubusercontent.com/76476526/168938702-24782b41-815f-4485-8970-8943018b4d3c.png)
8. Kemudian dibuat _script_ perhitungan 
![7](https://user-images.githubusercontent.com/76476526/168938721-b8bd682a-85f6-42b5-9dc8-a6b6a482a50d.png)
9. Langkah berikutnya membuat script untuk grafik Perubahan Kecepatan Arus Dalam _Grid_ Tertentu di Sepanjang Waktu
![8](https://user-images.githubusercontent.com/76476526/168938751-0614c475-c2c8-4acc-9a8e-13b42711be44.PNG)
10. Selanjutnya dibuat _script_ untuk grafik Perubahan Elevasi Permukaan Air Dalam _Grid_ Tertentu di Sepanjang Waktu
![9](https://user-images.githubusercontent.com/76476526/168938780-a50af0f5-8d0b-4136-a236-4c523dab1b76.PNG)
11. Kemudian dibuat _script_ untuk grafik Perubahan Kecepatan Arus Dalam Waktu Tertentu di sepanjang _Grid_
![10](https://user-images.githubusercontent.com/76476526/168938813-9df167ad-e4bd-4791-b64e-e0967d2840b3.PNG)
12. Berikutnya dibuat _script_ untuk grafik Perubahan Elevasi Permukaan Air Dalam Waktu Tertentu di Sepanjang _Grid_ dan menampilkan hasil grafik secara keseluruhan
![11](https://user-images.githubusercontent.com/76476526/168938845-a05e65ca-e402-4a73-9cd5-b493f00e5c19.PNG)
13. Langkah terakhir _running script_ pada menu _cell_ dan dipilih _running all_
![14](https://user-images.githubusercontent.com/76476526/168939038-dfd3beb2-a039-4777-9f3e-4dee1012870c.PNG)


# 4. Metode Pengerjaan
step by step maksud script modul 3 (flowchart dan script python yang digunakan mulai dari persamaan hidrodinamikanya, persamaan pembangun, persamaan transport, diskretitasi, penyelesaian analitik). bagian ini cara nulisnya sama kaya yang contoh asisten kirim. (dikerjain sama 3 orang)

# 5. Kegunaan dan Penerapan Script dalam Oseanografi
ini lebih ke penjelasan dari kegunaan dan penerapannya di ose bisa buat apa aja, tambahin kekurangan dan kelebihan dari penggunaan model hidrodinamika

# 6. Penutup
yang kebagian ini berarti otomatis nulis juga bagian kegunaan dan penerapan script (dikerjain sama 1 orang)

# 7. Referensi
Diisi jurnal atau buku semisal mengambil materi dari pustaka
