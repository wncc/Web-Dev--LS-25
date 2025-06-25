# 💻 What is Django?

**Django** is a high-level Python web framework that promotes rapid development and clean, pragmatic design. Built by experienced developers, Django takes care of much of the hassle of web development, so you can focus on writing your app without reinventing the wheel.

It follows the **Model-View-Template (MVT)** architectural pattern and includes many built-in features such as authentication, admin interface, ORM, and more.

---

## ✅ Benefits of Django

| Feature             | Description                                                             |
|---------------------|-------------------------------------------------------------------------|
| 🔐 Secure            | Protects against threats like SQL injection, CSRF, XSS, etc.           |
| ✨ Rapid Development | Built-in admin, ORM, and other features reduce development time.       |
| 🚀 Scalable          | Used by large-scale companies such as Instagram and Pinterest.         |
| 🧰 Modular           | Follows a modular architecture and supports reusable components.       |
| 🛠️ Admin Interface   | Automatically generates admin dashboard from models.                   |
| 🔍 ORM               | Allows database interaction using Python code instead of SQL.          |

---

## 💡 Real-Life Examples Using Django

| Website              | Description                                          |
|----------------------|------------------------------------------------------|
| 🌐 Instagram          | Uses Django for backend services.                    |
| 📰 The Washington Post | Manages large volumes of editorial content.         |
| 💬 Disqus             | Built its entire comment platform using Django.     |

---

## 🚀 How to Set Up Django (Step-by-Step)

### 📌 Prerequisites
- Python 3.8+
- Basic knowledge of Python programming

### ⚙️ Step 1: Install Virtual Environment (Optional)
```bash
pip install virtualenv
virtualenv venv
```
Activate it:
```bash
# Windows
venv\Scripts\activate

# macOS/Linux
source venv/bin/activate
```

### ⚙️ Step 2: Install Django
```bash
pip install django
django-admin --version
```

### ⚙️ Step 3: Create a Django Project
```bash
django-admin startproject mysite
cd mysite
python manage.py runserver
```
Open in browser: [http://127.0.0.1:8000](http://127.0.0.1:8000)

### ⚙️ Step 4: Create a Django App
```bash
python manage.py startapp blog
```
Add `'blog'` to `INSTALLED_APPS` in `mysite/settings.py`

### ⚙️ Step 5: Run Migrations
```bash
python manage.py migrate
```

### ⚙️ Step 6: Create Admin User (Optional)
```bash
python manage.py createsuperuser
```

---

## 💻 Django Video Learning Resources

- 🔹 [Django One Shot in English](https://youtu.be/PtQiiknWUcI?si=7eenzVR29bCYD-0P)

   Follow this timeline:
   | **Topic**                     | **Time Start**         |
   |-------------------------------|------------------------|
   | What is Django                | 5:27                   |
   | Installation & Setup          | 15:59                  |
   | Views & URLs                  | 31:28                  |
   | Templates                     | 39:55                  |
   | Admin Panel & Database        | 1:04:25                |
   | CRUD Operations               | 1:39:00                |
   | User Auth (Login, Logout)     | 2:22:27 → 2:39:03      |

- 🔹 [Basic Overview in English (after 22:00 min)](https://youtu.be/rHux0gMZ3Eg?si=0TB_P5_seRAXyGIC)
- 🔹 [Admin Panel](https://youtu.be/iLhcV7t3zug?si=nGbxyNHy25nV-kPh)
- 🔸 [Django Tutorial in Hindi](https://youtu.be/JxzZxdht-XY?si=i4PaPNe4kzVm2p29)

## Reading Resources

- 📖 [W3Schools Django](https://www.w3schools.com/django/)
- 📖 [GeeksforGeeks Django](https://www.geeksforgeeks.org/python/django-tutorial/)

## Optional Guided Video
- 🎓 [Guided Project (Optional)](https://youtu.be/Bu8_77S9w6g?si=2JkmBAfOZ3bWzmJr)

---

# ⚡️ Django REST API & JWT Authentication – Secure Your Backend Like a Pro

Welcome to **Week 3** of your Web Development journey. In this phase, you will explore how the backend powers full-stack applications, how REST APIs work, and how to secure them using token-based authentication such as **JWT**.

You’ll use **Django REST Framework (DRF)** — a powerful extension to Django that simplifies building RESTful APIs — and then secure those APIs with stateless JWT authentication, just like modern production apps.

---

## 🔒 Django REST API – Understanding the Backend

### 🔍 What is Django REST Framework (DRF)?

Django REST Framework is a toolkit that helps you build Web APIs using Django models and views. It allows your backend to communicate with the frontend (React here) or even external services by exposing JSON data over HTTP.

It works by converting your Django models into serializable data (like JSON), which can then be accessed and modified by API views and routes.

**Key components:**

- **Serializers** – Convert Django models to/from JSON.  
- **API Views** – Endpoints that respond with data, not HTML.  
- **Routers** – Automatically generate URLs for views.  
- **Browsable Interface** – You can test your API in a web browser.

Once you’ve defined your models and serializers, DRF allows you to perform **CRUD operations** — Create, Read, Update, and Delete — through standard HTTP methods (`GET`, `POST`, `PUT`, `DELETE`).

---

## 🔐 Authentication in Django REST Framework

### 🔍 How Does Authentication Work in APIs?

Authentication ensures that a user is who they claim to be. In web apps, authentication protects user data and prevents unauthorized access.

Django REST Framework provides multiple authentication mechanisms:

- **Session Authentication**  
  Based on Django’s default session and cookie system — best for websites using Django templates.

- **Basic Authentication**  
  Credentials are passed with each request — simple but insecure if not used with HTTPS.

- **Token Authentication**  
  Users receive a unique token after login and must include it in the `Authorization` header of all protected requests.

---

## 📘 Resources

### 📘 Reading Resource
[GeeksforGeeks](https://www.geeksforgeeks.org/node-js/rest-api-introduction/)

### ▶️ Videos

- [Must-Watch Intro Video](https://youtu.be/OTnuTerIUlo?si=LaEySnVLjiVPR3RX)
- [Django REST API Crash Course (English)](https://youtu.be/NoLF7Dlu5mc?si=1qT6PcJGLSui5M0a)
- [Full Django REST API Tutorial (English)](https://youtu.be/t-uAgI-AUxc?si=4tNm0zH8sn-pXbwe)
- [Django REST API Playlist (Hindi)](https://youtu.be/DNFTUtZf1Zc?si=eYclIuA4hJ_mBJcC)

---

## 🔑 JWT Authentication – Stateless and Secure Login System

### 🔍 What is JWT and Why Use It?

**JWT (JSON Web Token)** is a modern, stateless, token-based authentication system. It’s especially useful when you're building APIs that need to be accessed by JavaScript apps, mobile apps, or other frontend clients.

When a user logs in, the server returns:

- **Access Token** – Used for authentication on each API request (short-lived)
- **Refresh Token** – Used to generate new access tokens when the original one expires

---

## 📘 JWT Authentication Resources

### 📘 Reading Guide  
[DRF Official Authentication Docs](https://www.django-rest-framework.org/api-guide/authentication/)

### ▶️ Videos

- [JWT Authentication in Django REST Framework (English)](https://youtu.be/Xp0-Yy5ow5k?si=4_Qphsne0T2jhCn0)
- [JWT Authentication in Django (Hindi)](https://youtu.be/fXOKBbnMQow?si=iOHoNpMTULFgAAID)

---

Stay consistent. Practice daily. Your backend journey has just begun.

<p align="center">Created with ❤️ by WnCC</p>  


