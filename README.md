# 🛒 ByteStore

### Implementasi Web Server E-Commerce Menggunakan Ubuntu Server

---

## 📖 Project Overview

ByteStore merupakan proyek implementasi web server e-commerce berbasis Ubuntu Server yang dirancang untuk mensimulasikan lingkungan produksi toko online modern. Sistem memanfaatkan WordPress sebagai Content Management System (CMS) dan tema Catch Shop Dark untuk menghadirkan antarmuka e-commerce yang responsif, modern, dan mudah dikelola.

Selain menyediakan layanan web, server juga dilengkapi dengan Cockpit Dashboard untuk monitoring dan administrasi sistem secara real-time melalui antarmuka web.

---

## 🖥️ Server Specifications

### Hardware Configuration (Virtual Machine)

| Component        | Specification           |
| ---------------- | ----------------------- |
| Processors       | 4 vCPU                  |
| Base Memory      | 4096 MB (4 GB RAM)      |
| Storage          | 25 GB                   |
| Operating System | Ubuntu Server 22.04 LTS |

### Software Stack

| Component            | Technology      |
| -------------------- | --------------- |
| Operating System     | Ubuntu Server   |
| Web Server           | Apache2         |
| Database             | MySQL Server    |
| Backend Language     | PHP 8.1         |
| CMS                  | WordPress       |
| Theme                | Catch Shop Dark |
| Management Dashboard | Cockpit         |

---

## 🎯 Project Objectives

* Membangun web server e-commerce berbasis Linux.
* Mengimplementasikan layanan Apache, PHP, dan MySQL dalam satu server.
* Menerapkan WordPress sebagai platform pengelolaan konten.
* Menyediakan antarmuka toko online menggunakan tema Catch Shop Dark.
* Mengelola server secara real-time menggunakan Cockpit Dashboard.
* Mempelajari deployment, konfigurasi, dan administrasi server Ubuntu.

---

## 🏗️ System Architecture

```text
Client Browser
      │
      ▼
Apache2 Web Server
      │
      ▼
WordPress CMS
      │
      ▼
Catch Shop Dark Theme
      │
      ▼
MySQL Database

Administrator
      │
      ▼
Cockpit Dashboard
```

---

## 🚀 Installation & Deployment

### 1. Update System

```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Install Apache Web Server

```bash
sudo apt install apache2 -y
sudo systemctl enable apache2
sudo systemctl start apache2
```

### 3. Install MySQL Server

```bash
sudo apt install mysql-server -y
sudo systemctl enable mysql
sudo systemctl start mysql
```

### 4. Install PHP and Extensions

```bash
sudo apt install php php-mysql php-xml php-gd php-mbstring php-curl php-zip php-intl php-soap libapache2-mod-php -y
```

### 5. Install Cockpit Dashboard

```bash
sudo apt install cockpit -y
sudo systemctl enable --now cockpit.socket
```

Access:

```text
https://SERVER-IP:9090
```

### 6. Download and Deploy WordPress

```bash
cd /tmp
wget https://wordpress.org/latest.tar.gz
tar -xvf latest.tar.gz

sudo cp -R wordpress/* /var/www/html/
sudo chown -R www-data:www-data /var/www/html
sudo chmod -R 755 /var/www/html
```

### 7. Configure MySQL Database

```sql
CREATE DATABASE bytestore_db;
CREATE USER 'bytestore_user'@'localhost' IDENTIFIED BY 'StrongPassword123!';
GRANT ALL PRIVILEGES ON bytestore_db.* TO 'bytestore_user'@'localhost';
FLUSH PRIVILEGES;
```

### 8. Complete WordPress Setup

Open browser:

```text
http://SERVER-IP
```

Complete installation wizard and connect to the MySQL database.

### 9. Install Catch Shop Dark Theme

Dashboard:

```text
Appearance
→ Themes
→ Add New Theme
→ Search "Catch Shop Dark"
→ Install
→ Activate
```

---

## 🌐 Network Configuration

### Services and Ports

| Service           | Protocol | Port |
| ----------------- | -------- | ---- |
| HTTP              | TCP      | 80   |
| Cockpit Dashboard | TCP      | 9090 |
| MySQL             | TCP      | 3306 |

---

## 🔐 Security Configuration

Enable firewall:

```bash
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw allow 9090/tcp
sudo ufw enable
```

Verify status:

```bash
sudo ufw status
```

---

## 📊 System Monitoring

Cockpit Dashboard provides:

* CPU Monitoring
* Memory Monitoring
* Disk Usage Monitoring
* Service Management
* Network Monitoring
* System Logs

Access Dashboard:

```text
https://SERVER-IP:9090
```

---

## 📸 Project Screenshots

### Ubuntu Server

<img width="806" height="435" alt="image" src="https://github.com/user-attachments/assets/a4323501-e664-46c9-9f3f-104376912ff6" />



### Cockpit Dashboard

<img width="1917" height="926" alt="Dashboard" src="https://github.com/user-attachments/assets/34d19ad2-b370-4e1c-a706-4020a5596a71" />


### WordPress Dashboard

<img width="1912" height="906" alt="image" src="https://github.com/user-attachments/assets/a93be233-5df0-4347-b7a2-ba6cc4d911a8" />


### ByteStore Homepage

<img width="1906" height="827" alt="Halaman_Webpng" src="https://github.com/user-attachments/assets/8a9858cb-36c1-4049-b7b9-8cdc0d15882d" />


---

## 👨‍💻 Author

marckdekeyn

Implementation of an E-Commerce Web Server Using Ubuntu Server

Built using:

* Ubuntu Server
* Apache2
* MySQL
* PHP
* WordPress
* Catch Shop Dark Theme
* Cockpit Dashboard
