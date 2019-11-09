# Lapres_Modul4_JA07

## VLSM
### perhitungan VLSM ( CPT )

<b>Langkah 1</b>-tentukan jumlah subnet yang ada di dalam topologi tersebut.

![image](https://user-images.githubusercontent.com/45744801/68526375-a4a5aa00-030d-11ea-9ec0-5f85f3a679cb.png)

<b>Langkah 2</b>-Tentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan lakukan labelling netmask berdasarkan jumlah IP yang dibutuhkan.

![image](https://user-images.githubusercontent.com/45744801/68526465-c05d8000-030e-11ea-82f1-649d9c78e479.png)

<b>Langkah 3</b> Hitung pembagian IP berdasarkan NID dan netmask 192.168.0.0/19 menggunakan pohon dan Lakukan subnetting dengan menggunakan pohon tersebut untuk pembagian IP sesuai dengan kebutuhan masing-masing subnet yang ada.




### konfigurasi VLSM di CISCO PACKET TRACER ( CPT )

![Capture](https://user-images.githubusercontent.com/45744801/68525775-a9675f80-0307-11ea-9612-4e9b074c954f.PNG).

<b>Langkah 1</b>-buatlah topologi di CPT sesuai dengan gambar diatas.

![image](https://user-images.githubusercontent.com/45744801/68525741-673e1e00-0307-11ea-87bc-579fd64bced2.png)

<b>Langkah 2</b>-tambahkan port <b>NM-2FE2W</b> pada semua router terlebih dahulu. khusus untuk router <b>ARCEUS<b> tambahkan port <b>NM-4E </b> 
  
<b>Langkah 3</b>-Sambungkan kabel(cable) sesuai dengan topolgi diatas. 

<b>Langkah 4</b>-Atur IP untuk masing-masing interface yang ada di setiap device sesuai dengan pembagian subnet pada pohon VLSM. interface dapat diatur pada menu Config > INTERFACE > “nama interface” (contoh: FastEthernet0/0). Isi alamat IP dan subnet mask dari subnet interface tersebut. Berikut contoh untuk mengatur IP pada subnet A1.

Atur IP pada interface CHARIZARD yang mengarah ke client PIPLUP dengan 192.168.30.1.

![image](https://user-images.githubusercontent.com/45744801/68526770-d587de00-0311-11ea-9175-6024b76272d5.png)

Atur IP pada client PIPLUP yang mengarah ke CHARIZARD seperti gambar dibawah.

![image](https://user-images.githubusercontent.com/45744801/68526808-38797500-0312-11ea-9021-85bf9e26d949.png)

Lakukan hal yang sama untuk mengatur alamat IP setiap interface pada device yang ada dalam topologi.

<b>langkah 5</b>-Routing setiap router yang ada. Routing dapat dilakukan pada menu Config > Routing > Static pada device Router. Lalu isi Static Routes seperti gambar dibawah pada PIKACHU dan tekan tombol Add

![image](https://user-images.githubusercontent.com/45744801/68526856-bfc6e880-0312-11ea-9842-546349221073.png)

Pada static routing juga dibutuhkan default routing agar router dapat mengirimkan paket sesuai dengan tujuan. Default routing dibutuhkan untuk router yang berada di bawah router utama (router yang terhubung internet), contohnya VENUSAUR

![image](https://user-images.githubusercontent.com/45744801/68526866-fa308580-0312-11ea-81b7-a309ac4d64c6.png)


