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

### Pastikan Authentication Semua Sudah Enable

![Enable All](assets/images/cek-auth.png)

---

# 3. Mendapatkan Firebase API Key

Untuk menggunakan Firebase API melalui Postman, kita memerlukan **API Key**.

Langkah-langkah:

1. Klik **Project Settings**
2. Masuk ke tab **General**
3. Scroll ke bagian **Your Apps**

---

### Firebase Project Settings

![Firebase Project Settings](assets/images/firebase-project-setting.png)

---

Kemudian salin atau simpan nilai:

API Key ini akan digunakan pada request Postman.

---

## 4. Setup Postman Environment

Buka aplikasi Postman dan buat environment baru.

Contoh variable:

| Variable | Value |
|--------|------|
| FIREBASE_API_KEY | API key dari Firebase |
| ID_TOKEN | token dari login |

![Postman Environment](assets/images/postman-environment.png)

---

## 5. Register User via Firebase API

Endpoint:

POST https://identitytoolkit.googleapis.com/v1/accounts:signUp?key={{FIREBASE_API_KEY}}

### Body Request

{
 "email":"user@email.com",
 "password":"12345678",
 "returnSecureToken":true
}

### Postman Headers

![Headers](assets/images/headers.png)

### Postman Body (raw JSON)

![Body](assets/images/body.png)

### Scripts

![Scripts](assets/images/scripts.png)

### Jika sudah, coba test Send dan lihat hasilnya dengan Beberapa Kemungkinan
1. <div style="background-color:#d4edda; padding:15px; border-radius:8px; border-left:6px solid #28a745;">
<b>200 OK - Request Berhasil</b>
Request berhasil diproses oleh Firebase Authentication.  
User berhasil dibuat dan Firebase mengembalikan response berupa token autentikasi seperti <b>idToken</b>, <b>refreshToken</b>, dan <b>expiresIn</b>.
Artinya proses registrasi atau login berjalan dengan sukses.
</div>

![Register Berhasil](assets/images/regist-berhasil.png)

---
2. <div style="background-color:#f8d7da; padding:15px; border-radius:8px; border-left:6px solid #dc3545;">
<b>400 Bad Request - Request Gagal</b>

Request gagal diproses oleh Firebase.  
Hal ini biasanya terjadi karena beberapa kemungkinan seperti: Email sudah terdaftar

Periksa kembali request yang dikirim melalui Postman.
</div>

![Register Gagal](assets/images/regist-gagal.png)

---

## 6. Send Email Verification

Endpoint:

POST https://identitytoolkit.googleapis.com/v1/accounts:sendOobCode?key={{FIREBASE_API_KEY}}

### Body Request

{
 "requestType":"VERIFY_EMAIL",
 "idToken":"{{ID_TOKEN}}"
}

### Body

![Body](assets/images/verif-email-body.png)

### Verify Success

![Body](assets/images/verifikasi-sukses.png)

