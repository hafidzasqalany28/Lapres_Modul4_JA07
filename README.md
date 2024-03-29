# Lapres_Modul4_JA07

## VLSM
### perhitungan VLSM ( CPT )

<b>Langkah 1</b>-tentukan jumlah subnet yang ada di dalam topologi tersebut.

![image](https://user-images.githubusercontent.com/45744801/68526375-a4a5aa00-030d-11ea-9ec0-5f85f3a679cb.png)

<b>Langkah 2</b>-Tentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan lakukan labelling netmask berdasarkan jumlah IP yang dibutuhkan. 

![image](https://user-images.githubusercontent.com/45744801/68526465-c05d8000-030e-11ea-82f1-649d9c78e479.png)

<b>Langkah 3</b>-Hitung pembagian IP berdasarkan NID dan netmask 192.168.0.0/19 menggunakan pohon dan Lakukan subnetting dengan menggunakan pohon tersebut untuk pembagian IP sesuai dengan kebutuhan masing-masing subnet yang ada.

![vlsm hitung](https://user-images.githubusercontent.com/45744801/68526951-09fc9980-0314-11ea-851e-441b2b310202.jpg)

khusus IP server menggunakan IP DMZ yaitu, 10.151.73.64/29.

![image](https://user-images.githubusercontent.com/45744801/68527040-22b97f00-0315-11ea-9b23-0eef388c177e.png)

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

note : CLOUD diberikan IP TUNTAP

<b>langkah 5</b>-Routing setiap router yang ada. Routing dapat dilakukan pada menu Config > Routing > Static pada device Router. Lalu isi Static Routes seperti gambar dibawah pada PIKACHU dan tekan tombol Add

![image](https://user-images.githubusercontent.com/45744801/68526856-bfc6e880-0312-11ea-9842-546349221073.png)

Pada static routing juga dibutuhkan default routing agar router dapat mengirimkan paket sesuai dengan tujuan. Default routing dibutuhkan untuk router yang berada di bawah router utama (router yang terhubung internet), contohnya VENUSAUR

![image](https://user-images.githubusercontent.com/45744801/68526866-fa308580-0312-11ea-81b7-a309ac4d64c6.png)

Agar semua subnet dapat saling terhubung, tambahkan static routing berikut :

1. Pada PIKACHU

```
192.168.31.108/30 via 192.168.31.106
192.168.31.80/29 via 192.168.31.106
192.168.31.0/26 via 192.168.31.106
192.168.0.0/21 via 192.168.31.106
192.168.31.88/30 via 192.168.31.106
192.168.28.0/23 via 192.168.31.106
192.168.20.0/22 via 192.168.31.106 
192.168.31.64/28 via 192.168.31.106
192.168.24.0/23 via 192.168.31.106
192.168.31.92/30 via 192.168.31.102
192.168.30.0/24 via 192.168.31.102
192.168.31.96/30 via 192.168.31.102
192.168.26.0/23 via 192.168.31.102
192.168.16.0/22 via 192.168.31.102
192.168.8.0/21 via 192.168.31.102
10.151.73.68/30 via 192.168.31.102
```

2. Pada VENUSAUR

```
192.168.30.0/24 via 192.168.31.94
192.168.26.0/23 via 192.168.31.98
192.168.16.0/22 via 192.168.31.98
192.168.8.0/21 via 192.168.31.98
10.151.73.68/30 via 192.168.31.98
0.0.0.0/0 via 192.168.31.101
```

3. Pada CHARIZARD

```
0.0.0.0/0 via 192.168.31.93
```

4. Pada ARCEUS

```
0.0.0.0/0 via 192.168.31.97
```

5. Pada BLASTOISE

```
192.168.31.80/29 via 192.168.31.110
192.168.31.0/26 via 192.168.31.110
192.168.28.0/23 via 192.168.31.90
192.168.20.0/22 via 192.168.31.90
192.168.31.64/28 via 192.168.31.90
192.168.24.0/23 via 192.168.31.90
0.0.0.0/0 via 192.168.31.105
```

6. Pada GIRATINA

``
0.0.0.0/0 via 192.168.31.109
``

7. Pada LUGIA

```
0.0.0.0/0 via 192.168.31.89
192.168.24.0/23 via 192.168.20.3
192.168.31.64/28 via 192.168.20.3
```

8. PadA DIALGA

``
0.0.0.0/0 via 192.168.20.1
``

## perhitungan CIDR

<b>Langkah 1</b>-Tentukan subnet yang ada dalam topologi dan lakukan labelling netmask terhadap masing-masing subnet. Contohnya dapat dilihat pada gambar berikut.

![image](https://user-images.githubusercontent.com/45744801/68526375-a4a5aa00-030d-11ea-9ec0-5f85f3a679cb.png)

<b>Langkah 2</b>-Gabungkan subnet paling bawah di dalam topologi. Paling bawah berarti subnet yang paling jauh dari internet (gambar awan). netmask yang dipakai adalah netmask terbesar dari penggabungan subnet di naikin 1. contoh A16 /28 dan A17 /23 maka netmask penggabungan menjadi /24. Lalu ulangi langkah tersebut sampai menjadi sebuah subnet besar yang mencakup 1 topologi yang kita miliki. Maka didapat netmask /16.

<b>Langkah 3</b>-Dari proses penggabungan yang telah dilakukan, didapatkan sebuah subnet besar dengan netmask /16. Kali ini dapat menggunakan NID 192.168.0.0/16.

<b>Langkah 4</b>-Hitung pembagian IP dengan pohon berdasarkan penggabungan subnet yang telah dilakukan.

![cidr](https://user-images.githubusercontent.com/45744801/68527752-294bf480-031d-11ea-9bcf-055cbb815b39.jpg)

### konfigurasi CIDR di UML
<b>Langkah 1</b>-membuat topologi sesuai dengan soal.
```
# Switch
uml_switch -unix switch0 > /dev/null < /dev/null &
uml_switch -unix switch1 > /dev/null < /dev/null &
uml_switch -unix switch2 > /dev/null < /dev/null &
uml_switch -unix switch3 > /dev/null < /dev/null &
uml_switch -unix switch4 > /dev/null < /dev/null &
uml_switch -unix switch5 > /dev/null < /dev/null &
uml_switch -unix switch6 > /dev/null < /dev/null &
uml_switch -unix switch7 > /dev/null < /dev/null &
uml_switch -unix switch8 > /dev/null < /dev/null &
uml_switch -unix switch9 > /dev/null < /dev/null &
uml_switch -unix switch10 > /dev/null < /dev/null &
uml_switch -unix switch11 > /dev/null < /dev/null &
uml_switch -unix switch12 > /dev/null < /dev/null &

uml_switch -unix switch13 > /dev/null < /dev/null &
uml_switch -unix switch14 > /dev/null < /dev/null &
uml_switch -unix switch15 > /dev/null < /dev/null &
uml_switch -unix switch16 > /dev/null < /dev/null &
uml_switch -unix switch17 > /dev/null < /dev/null &
uml_switch -unix switch18 > /dev/null < /dev/null &

# Router
xterm -T PIKACHU -e linux ubd0=PIKACHU,jarkom umid=PIKACHU eth0=tuntap,,,10.151.72.8 eth1=daemon,,,switch0 eth2=daemon,,,switch13 eth3=daemon,,,switch14 mem=64M &
xterm -T VENOSAUR -e linux ubd0=VENOSAUR,jarkom umid=VENOSAUR eth0=daemon,,,switch13 eth1=daemon,,,switch15 eth2=daemon,,,switch16 mem=64M &
xterm -T CHARIZARD -e linux ubd0=CHARIZARD,jarkom umid=CHARIZARD eth0=daemon,,,switch15 eth1=daemon,,,switch1 mem=64M &
xterm -T ARCEUS -e linux ubd0=ARCEUS,jarkom umid=ARCEUS eth0=daemon,,,switch16 eth1=daemon,,,switch2 eth2=daemon,,,switch3 eth3=daemon,,,switch4 eth4=daemon,,,switch5 mem=64M &
xterm -T BLASTOISE -e linux ubd0=BLASTOISE,jarkom umid=BLASTOISE eth0=daemon,,,switch14 eth1=daemon,,,switch17 eth2=daemon,,,switch18 eth3=daemon,,,switch6 mem=64M &
xterm -T LUGIA -e linux ubd0=LUGIA,jarkom umid=LUGIA eth0=daemon,,,switch17 eth1=daemon,,,switch7 eth2=daemon,,,switch8 mem=64M &
xterm -T GIRATINA -e linux ubd0=GIRATINA,jarkom umid=GIRATINA eth0=daemon,,,switch18 eth1=daemon,,,switch12 eth2=daemon,,,switch11 mem=64M &
xterm -T DIALGA -e linux ubd0=DIALGA,jarkom umid=DIALGA eth0=daemon,,,switch8 eth1=daemon,,,switch9 eth2=daemon,,,switch10 mem=64M &

# DNS + Web Server
xterm -T ARTICUNO -e linux ubd0=ARTICUNO,jarkom umid=ARTICUNO eth0=daemon,,,switch0 mem=64M &
xterm -T MEWTWO -e linux ubd0=MEWTWO,jarkom umid=MEWTWO eth0=daemon,,,switch2 mem=64M &

# Klien
xterm -T PIPLUP -e linux ubd0=PIPLUP,jarkom umid=PIPLUP eth0=daemon,,,switch1 mem=64M &
xterm -T PSYDUCK -e linux ubd0=PSYDUCK,jarkom umid=PSYDUCK eth0=daemon,,,switch3 mem=64M &
xterm -T SNORLAX -e linux ubd0=SNORLAX,jarkom umid=SNORLAX eth0=daemon,,,switch4 mem=64M &
xterm -T CUBONE -e linux ubd0=CUBONE,jarkom umid=CUBONE eth0=daemon,,,switch5 mem=64M &
xterm -T SLOWBRO -e linux ubd0=SLOWBRO,jarkom umid=SLOWBRO eth0=daemon,,,switch8 mem=64M &
xterm -T BEWEAR -e linux ubd0=BEWEAR,jarkom umid=BEWEAR eth0=daemon,,,switch10 mem=64M &
xterm -T BUIZEL -e linux ubd0=BUIZEL,jarkom umid=BUIZEL eth0=daemon,,,switch10 mem=64M &
xterm -T ARON -e linux ubd0=ARON,jarkom umid=ARON eth0=daemon,,,switch9 mem=64M &
xterm -T HOOTHOOT -e linux ubd0=HOOTHOOT,jarkom umid=HOOTHOOT eth0=daemon,,,switch7 mem=64M &
xterm -T SWABLU -e linux ubd0=SWABLU,jarkom umid=SWABLU eth0=daemon,,,switch6 mem=64M &
xterm -T KADABRA -e linux ubd0=KADABRA,jarkom umid=KADABRA eth0=daemon,,,switch11 mem=64M &
xterm -T ABRA -e linux ubd0=ABRA,jarkom umid=ABRA eth0=daemon,,,switch12 mem=64M &
```

<b>Langkah 2</b>-bash topologi.

<b>Langkah 3</b>-login setiap UML.

<b>Langkah 4</b>-Pada semua router lakukan setting sysctl dengan mengetikkan perintah nano `/etc/sysctl.conf`. Hilangkan tanda pagar (#) pada bagian `net.ipv4.ip_forward=1`. lalu ketikkan `sysctl -p` untuk mengaktifkan perubahan yang ada. Dengan mengaktifkan fungsi IP Forward ini maka Linux nantinya dapat menentukan jalur mana yang dipilih untuk mencapai jaringan tujuan.

<b>Langkah 5</b>-Setting IP pada setiap UML dengan mengetikkan nano /etc/network/interfaces Lalu setting IPnya sebagai berikut:

(Sebagai Router)

PIKACHU 
```
```

VENUSAUR
```
```
CHARIZARD
```
```
ARCEUS
```
```
BLASTOISE
```
```
GIRATINA
```
```
LUGIA
```
```
(sebagai server )

ARTICUNO
```
```
MEWTWO
```
```
(sebagai client )

PIPLUP
```
```
PYSDUCK
```
```
SNORLAX
```
```
CUBONE
```
```
SLOWBRO
```
```
ABRA
```
```
KADABRA
```
```
SWABLU
```
```
HOOTHOOT
```
```
SLOWBRO
```
```
BEWEAR
```
```
BUIZEL
```
```
ARON
```
```

<b>Langkah 6</b>-Restart network setiap uml dengan mengetikkan `service networking restart`.

<b>Langkah 7</b>-Ketikkan `iptables –t nat –A POSTROUTING –o eth0 –j MASQUERADE –s 192.168.0.0/16` pada router PIKACHU agar bisa terhubung ke jaringan luar. 

<b>Langkah 8</b>-routing semua router uml. routing dapat dilakukan pada device router dengan perintah :
``
route add -net <NID subnet> netmask <netmask> gw <IP gateway>
``
