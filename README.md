# 📌 E-commerce DIY Store

## 🔍 เกี่ยวกับโปรเจกต์
โปรเจกต์นี้เป็น เว็บไซต์ E-commerce ในรายวิชาการเขียนโปรแกรมแบบเว็บฝั่งเซิร์ฟเวอร์และรายวิชาการเขียนโปรแกรมแบบเว็บฝั่งไคลเอนต์ มีวัตถุประสงค์เพื่อให้เข้าใจการพัฒนาเว็บไซต์ของฝั่ง Frontend และ Backend รวมถึงเรียนรู้การเขียนโปรแกรมด้วยภาษา Golang สำหรับพัฒนาฝั่ง Backend และเรียนรู้การเขียนโปรแกรมด้วยภาษา JavaScript สำหรับพัฒนาฝั่ง Frontend โดยโปรเจกต์นี้ทีมพัฒนาได้ทำเกี่ยวกับเว็บไซต์ E-commerce ร้านสินค้าแฮนด์เมด ที่นำเอาความรู้จากการเรียนมาพัฒนาให้เว็บไซต์นี้สำเร็จ

พัฒนาโดยทีมงานทั้งหมด **5 คน** ซึ่งมีหน้าที่ดังนี้:

## 👥 ทีมพัฒนา  
| ชื่อ | บทบาท | รายละเอียด |
|------|------|----------|
| **อารดา แว่นวงษ์** | Backend Developer | พัฒนาและออกแบบฝั่ง Backend รวมถึงจัดการฐานข้อมูล |
| **สมัญญา กี่สุข** | Backend Developer | พัฒนาและออกแบบฝั่ง Backend |
| **สุพิพัฒน์ แสงสอน** | Frontend Developer | พัฒนาและออกแบบฝั่ง Frontend |
| **อัญชลี สกุลฑิฆัมพร** | Frontend Developer | พัฒนาและออกแบบฝั่ง Frontend รวมถึงออกแบบ UI/UX |
| **อภิญญา แซ่อึ้ง** | Frontend Developer | พัฒนาและออกแบบฝั่ง Frontend |

## 🛠 เทคโนโลยีที่ใช้  
- **Frontend:** React  
- **Backend:** Rest Api with Golang
- **Database:** PostgreSQL  
- **อื่น ๆ:** Docker

## 🚀 วิธีติดตั้งและใช้งาน
- ทำการ Get storedatabase ก่อน จาก [store database](https://github.com/arada2003/storedatabase)
  (ก่อนทำการ Run Docker คุณสามารถแก้ไขไฟล์ .env ให้เป็น environment ของคุณเองได้ เช่น eamil, password)
```bash
# PostgreSQL Environment Variables
POSTGRES_DB=ecommerce
POSTGRES_USER=ecommerce_user
POSTGRES_PASSWORD=your_strong_password  # สามารถแก้ไขได้
POSTGRES_PORT=5432

# pgAdmin Environment Variables
PGADMIN_DEFAULT_EMAIL=admin123@gmail.com  # สามารถแก้ไขได้
PGADMIN_DEFAULT_PASSWORD=admin123  # สามารถแก้ไขได้
PGADMIN_PORT=5050
```
- Run Folder ด้วย Docker ใช้คำสั่ง
```bash
docker-compose up -d
```
- จากนั้นทำการ Get apiecommerce จาก [api ecommerce](https://github.com/arada2003/apiecommerce)
- แก้ไขไฟล์ .env เพื่อเปลี่ยน IP Host ในการเรียก environment ของ Database ที่เราได้สร้างไว้ก่อนหน้า
```bash
# เปิด terminal ใน VS code หรือ command line หรือ power shell ก็ได้
# ค้นหา IP address ของ IPv4 ด้วยคำสั่ง
ipconfig

# copy IPv4 จากนั้นทำการเปลี่ยน Host ในไฟล์ .env
# App
APP_PORT=8080

# Database
POSTGRES_HOST=192.168.88.33  # เอา IPv4 ที่ copy มาใส่แทน
POSTGRES_PORT=5435
POSTGRES_USER=ecommerce_user
POSTGRES_PASSWORD=your_strong_password  # ถ้าใน storedatabase ที่เราได้ Get มาก่อนหน้ามีการเปลี่ยน password ในไฟล์ .env ตรงนี้ก็ต้องเปลี่ยนเหมือนกัน
POSTGRES_DBNAME=ecommerce
POSTGRES_SSLMODE=disable
```
- Run Folder ด้วย Docker ใช้คำสั่ง
```bash
docker-compose up -d
```
- จะเปิด localhost:5050 สำหรับ PostgreSQL
- จะเปิด localhost:8080 สำหรับ Rest Api

- ทำการ Get diyecommerce จาก [diy ecommerce](https://github.com/arada2003/diyecommerce)
- เพิ่ม Proxy สำหรับเชื่อมต่อกับฝั่ง Backend ในไฟล์ package.json เพิ่มไปยังส่วนสุดท้ายของไฟล์ก็ได้
```bash
"proxy": "http://localhost:8080"
```
- Run Server
```bash
npm start
```
- จะเปิด localhost:3000 สำหรับ react
