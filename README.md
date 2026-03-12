# 📧 Firebase Email Verification with Postman

![Firebase](https://img.shields.io/badge/Firebase-Authentication-FFCA28?logo=firebase&logoColor=black)
![Postman](https://img.shields.io/badge/Postman-API%20Testing-FF6C37?logo=postman&logoColor=white)
![Status](https://img.shields.io/badge/Status-Learning-blue)

![Nama](https://img.shields.io/badge/Nama-Helen%20Oktaviani-4CAF50)
![NIM](https://img.shields.io/badge/NIM-1123150205-2196F3)
![Kelas](https://img.shields.io/badge/Kelas-TI%20SE%2023%20M-9C27B0)

## Overview
Dokumentasi ini menjelaskan implementasi verifikasi email menggunakan Firebase Authentication dan pengujian API menggunakan Postman.

---

## 1. Setup Firebase Project

Langkah pertama adalah membuat project baru di Firebase Console.

1. Buka https://console.firebase.google.com
![Firebase dashboard](assets/images/firebase-dashboard.png)
2. Klik **Add Project**
3. Masukkan nama project
4. Klik **Continue** sampai selesai
---

### Tampilan pembuatan project

![Create Firebase Project](assets/images/create-project.png)

---

Setelah project berhasil dibuat, kita akan diarahkan ke dashboard Firebase.

![Halaman Project Firebase](assets/images/dashboard-project.png)

---

# 2. Enable Authentication

Aktifkan fitur Firebase **Authentication**.

Langkah-langkahnya:

1. Pada sidebar Firebase klik **Build**
2. Pilih menu **Authentication**
3. Klik **Get Started**

---

### Menu Authentication

![Firebase Authentication Menu](assets/images/menu-authentication.png)

---

Setelah itu kita harus mengaktifkan metode login **Email/Password** dan **Google**.

Langkahnya:

1. Masuk ke tab **Sign-in Method**
2. Klik **Email/Password**
3. Aktifkan **Enable**
4. Klik **Save**
4. Setelah itu Klik **Add New Provider** dan Pilih Menu/Logo **Google**

---

### Enable Email Password

![Enable Email Password](assets/images/emailpass.png)

### Enable Google

![Enable Google](assets/images/google.png)

