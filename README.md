# Cara Membuat Aplikasi Social Distancing Dengan React Native

link youtube: 

## Spesifikasi Kebutuhan

- Android atau IOS di tutorial kali ini saya akan menggunakan Android
- JAVA SDK
- ANDROID SDK
- NODE.JS
- OS UBUNTU/WINDOWS/MAC di tutorial ini saya menggunakan ubuntu 20.04
- FIREBASE
- GOOGLE MAPS API KEY

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
      <uses-library android:name="org.apache.http.legacy" android:required="false"/>
```

sekarang buka ```App.js``` anda lalu hapus semua kodingan dan ganti dengan kode berikut

```
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';
import MapView, { PROVIDER_GOOGLE } from 'react-native-maps'; 
export default function App() {
  return (

    <View style={styles.container}>
     <MapView
       provider={PROVIDER_GOOGLE} // remove if not using Google Maps
       style={styles.map}
       region={{
         latitude: 37.78825,
         longitude: -122.4324,
         latitudeDelta: 0.015,
         longitudeDelta: 0.0121,
       }}
     >
     </MapView>
   </View>
  );
}

const styles = StyleSheet.create({
  container: {
    ...StyleSheet.absoluteFillObject,
    height: "100%",
    width: 400,
    justifyContent: 'flex-end',
    alignItems: 'center',
  },
  map: {
    ...StyleSheet.absoluteFillObject,
  },
 });
 
```

lalu anda akan mendapatkan maps seperti dibawah ini

![s](https://imgur.com/download/AZ3YjU0)

8. Sekarang kita buat firebase nya, firebase disini digunakan untuk mendapatkan koordinat dan juga apakah kita online atau tidak. Untuk melakukan ini kita harus punya akun firebase pertama tama buka firebase console https://console.firebase.google.com/

klik icon android karena kita akan membuat aplikasi android

![s](https://imgur.com/download/mzmEp8n)

beri nama package android sesuai nama di AndroidManifest.xml

![s](https://imgur.com/download/wWxPbUM)

![s](https://imgur.com/download/MJmcIEe)

setelah itu klik "Register App" lalu anda akan mendapatkan google-services.json download file tersebut lalu letakkan pada folder android/app

![s](https://imgur.com/download/yr0pwAJ) 

masukkan kode berikut ke android/build.gradle

```
 buildscript {
  dependencies {
    // ... other dependencies
    classpath 'com.google.gms:google-services:4.3.3'
    // Add me --- /\
  }
}
```
lalu tambahkan kode berikut ke dalam android/app/build.gradle

```
apply plugin: 'com.android.application'
apply plugin: 'com.google.gms.google-services' // <- Add this line
```

setelah itu run kode berikut 

```
npx react-native run-android
```

setelah selesai buka aplikasi expo kembali setelah itu kita jalankan perintah berikut untuk menginstall library realtime database

```
yarn add @react-native-firebase/database
expo start
```

lalu jalankan expo dan scan barcodenya

9. 




# Referensi

https://github.com/react-native-community/react-native-maps/

https://rnfirebase.io/





# How to Create a Social Distancing Application With React Native

youtube link:

## Requirement Specifications

- Android or IOS in this tutorial I will use Android
- JAVA SDK
- ANDROID SDK
- NODE.JS
- OS UBUNTU / WINDOWS / MAC in this tutorial I use ubuntu 20.04
- FIREBASE
- GOOGLE MAPS API KEY

1. First of all we install "expo" which is a tool used to create React Native templates

``
npm install -g expo-cli
``

2.After finishing create the React Native application using the command below

``
expo init android
``

** android ** here is the name of the application if you want to name it with another name please

we choose the minimum as shown below

! [s] (https://imgur.com/download/80tO1ka)

3. When finished creating the application with __expo__ we run the following command

``
android cd
``

then we run the command

``
export ANDROID_SDK_ROOT = <where android sdk>
expo start
``
for example the location of android sdk `` / home / panda / Android / Sdk```
the command `` expo start '' here is used to run the application at the expo, expo is an android application used to run React Native, you can get it on the google play store

4. Make sure your cellphone and laptop are on the same network, then scan the QR code using the expo application

! [s] (https://imgur.com/download/WwcKp4V)

after success you will get a __screen__ like this

! [s] (https://imgur.com/download/UDnSfWP)

5. After that open __VSCODE__ or any other editor application and open the react native application folder that you created for me, I use the name ** android **, please note that you can use any name to make this application work if you will see the directory applications like the following

! [s] (https://imgur.com/download/XlDurB0)

6.Now we try to edit the `` App.js '' `because this is where our application runs.
we try to change the words `` Open up App.js to start working on your app! '' to become `` hi ''

! [s] (https://imgur.com/download/znzyLKG)

! [s] (https://imgur.com/download/1CKvvDb)

! [s] (https://imgur.com/download/OcOOhsK)

then our application text will change automatically

7. Now we add maps to our application, run the following command

``
yarn add react-native-maps -E
``

after that add this to `` android / app / build.gradle``` in the `` dependencies ('' column

``
implementation (project (': react-native-maps')) {
       exclude group: 'com.google.android.gms', module: 'play-services-base'
       exclude group: 'com.google.android.gms', module: 'play-services-maps'
   }
   implementation 'com.google.android.gms: play-services-base: 17.2.1'
   implementation 'com.google.android.gms: play-services-maps: 17.0.0'
``

after that add meta-data in `` ʻandroid / app / src / main / AndroidManifest.xml```, make sure your meta data is in <application>

``
 <meta-data
     android: name = "com.google.android.geo.API_KEY"
     android: value = "Fire your key here" />
      <uses-library android: name = "org.apache.http.legacy" android: required = "false" />
``

Now open your `` ʻApp.js``` then delete all code and replace it with the following code

``
import React from 'react';
import {StyleSheet, Text, View} from 'react-native';
import MapView, {PROVIDER_GOOGLE} from 'react-native-maps';
export default function App () {
  return (

    <View style = {styles.container}>
     <MapView
       provider = {PROVIDER_GOOGLE} // remove if not using Google Maps
       style = {styles.map}
       region = {{
         latitude: 37.78825,
         longitude: -122.4324,
         latitudeDelta: 0.015,
         longitudeDelta: 0.0121,
       }}
     >
     </MapView>
   </View>
  );
}

const styles = StyleSheet.create ({
  container: {
    ... StyleSheet.absoluteFillObject,
    height: "100%",
    width: 400,
    justifyContent: 'flex-end',
    alignItems: 'center',
  },
  map: {
    ... StyleSheet.absoluteFillObject,
  },
 });
 
``

then you will get maps as below

! [s] (https://imgur.com/download/AZ3YjU0)

8. Now we make the firebase, firebase here is used to get coordinates and also whether we are online or not. To do this we must have a firebase account first open the firebase console https://console.firebase.google.com/

click the android icon because we will create an android application

! [s] (https://imgur.com/download/mzmEp8n)

name the android package according to the name in AndroidManifest.xml

! [s] (https://imgur.com/download/wWxPbUM)

! [s] (https://imgur.com/download/MJmcIEe)

after that click "Register App" then you will get google-services.json download the file and place it in the android / app folder

! [s] (https://imgur.com/download/yr0pwAJ)

enter the following code into android / build.gradle

``
 buildscript {
  dependencies {
    // ... other dependencies
    classpath 'com.google.gms: google-services: 4.3.3'
    // Add me --- / \
  }
}
``
then add the following code into android / app / build.gradle



