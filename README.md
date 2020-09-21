# Cara Membuat Aplikasi Social Distancing Dengan React Native

link youtube: 

## Spesifikasi Kebutuhan

- Android atau IOS di tutorial kali ini saya akan menggunakan Android
- JAVA SDK
- ANDROID SDK
- NODE.JS
- OS UBUNTU/WINDOWS/MAC di tutorial ini saya menggunakan ubuntu 20.04

1. Pertama tama kita install "expo" yaitu piranti yang digunakan untuk membuat template react native

```
npm install -g expo-cli
```

2. setelah selesai buat aplikasi react native dengan menggunakan perintah di bawah ini

```
expo init android
```

**android** disini adalah nama dari aplikasi tersebut jika anda ingin menamainya dengan nama lain silahkan

kita pilih minimal seperti gambar dibawah ini

![s](https://imgur.com/download/80tO1ka)

3. Setelah selesai membuat aplikasi dengan __expo__ kita jalankan perintah berikut

```
cd android
```

lalu kita jalankan perintah

```
export ANDROID_SDK_ROOT=<letak android sdk>
expo start
```
contoh letak android sdk ```/home/panda/Android/Sdk```
perintah ```expo start``` disini digunakan untuk menjalankan aplikasi di expo, expo adalah aplikasi android yang digunakan untuk menjalankan react native anda bisa mendapatkannya di google play store

4. Pastikan hp anda dan laptop anda berada di jaringan yang sama setelah itu lakukan Scan QR code menggunakan aplikasi expo

![s](https://imgur.com/download/WwcKp4V)

setelah sukses anda akan mendapatakan __screen__ seperti ini

![s](https://imgur.com/download/UDnSfWP)

5. Setelah itu buka __VSCODE__ atau aplikasi editor lainnya dan buka folder aplikasi react native yang anda buat tadi untuk saya, saya memakai nama **android** perlu diketahui anda bisa memakai nama apa saja untuk membuat aplikasi ini bekerja jika sudah anda akan melihat direktori aplikasi seperti berikut

![s](https://imgur.com/download/XlDurB0)

6. Sekarang kita coba untuk mengedit ```App.js``` karena dari sinilah aplikasi kita berjalan.
kita coba ubah kata kata ```Open up App.js to start working on your app!``` menjadi ```hai```

![s](https://imgur.com/download/znzyLKG)

![s](https://imgur.com/download/1CKvvDb)

![s](https://imgur.com/download/OcOOhsK)

maka text aplikasi kita akan berubah otomatis

7. Sekarang kita tambah maps pada aplikasi kita jalankan perintah berikut

```
yarn add react-native-maps -E
```

setelah itu tambahkan ini ke ```android/app/build.gradle``` pada kolom ```dependencies {```

```
implementation(project(':react-native-maps')){
       exclude group: 'com.google.android.gms', module: 'play-services-base'
       exclude group: 'com.google.android.gms', module: 'play-services-maps'
   }
   implementation 'com.google.android.gms:play-services-base:17.2.1'
   implementation 'com.google.android.gms:play-services-maps:17.0.0'
```

setelah itu tambah meta-data di ```android/app/src/main/AndroidManifest.xml``` pastikan meta data anda berada di dalam <application>

```
 <meta-data
     android:name="com.google.android.geo.API_KEY"
     android:value="Api key anda disini"/>
```

sekarang buka ```App.js``` anda lalu tambahkan import pada bagian atas

```
import MapView, { PROVIDER_GOOGLE } from 'react-native-maps'; 
```

![s](https://imgur.com/download/BY0ns3x)




# Referensi

https://github.com/react-native-community/react-native-maps/







