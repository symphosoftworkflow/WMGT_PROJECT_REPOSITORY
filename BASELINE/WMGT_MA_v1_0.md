<img src="https://www.symphosoft.com/logo/symphosoftLogo.png" alt="Symphosoft Logo" width="200"/>

# คู่มือการบำรุงรักษาระบบ (Maintenance Documentation)
**ชื่อระบบงาน**: Recycle Waste Collecting Management System  
**เวอร์ชัน**: 1.0  
**จัดทำโดย**: นายประกาศิต ทองนอก  
**วันที่อนุมัติเอกสาร**: 03 ตุลาคม พ.ศ. 2567  
  
---

## ประวัติการจัดทำเอกสาร

| ลำดับ | เวอร์ชัน | รายละเอียดการดำเนินการ                 | ผู้ดำเนินการ | วันที่ดำเนินการ |
|-------|----------|-----------------------------------------|--------------|-----------------|
| 1     | 0.1      | จัดทำ คู่มือการปฏิบัติงานสำหรับผู้ดูแลระบบ         | นายประกาศิต ทองนอก  (TESTER)  | 30 กันยนายน พ.ศ. 2567        |
| 2     | 1.0      | อนุมัติ คู่มือการปฏิบัติงานสำหรับผู้ดูแลระบบ       | นางสาวปวริศา จันทรสถาพร (PM)  | 03 ตุลาคม พ.ศ. 2567        |  

---

## สารบัญ

1. [การตั้งค่าและการกำหนดค่าของระบบ (System and Software Configuration)](#1-การตั้งค่าและการกำหนดค่าของระบบ)
    - 1.1 [การตั้งค่าระบบ Production (Production Configuration)](#11-การตั้งค่าระบบ-production)
    - 1.2 [การตั้งค่าระบบ Development (Development Configuration)](#12-การตั้งค่าระบบ-development)
2. [การควบคุมรายการกำหนดค่า (Configuration Item Control)](#2-การควบคุมรายการกำหนดค่า)
    - 2.1 [การควบคุมเวอร์ชัน (Version Control)](#21-การควบคุมเวอร์ชัน)
    - 2.2 [รายการที่ไม่ต้องส่งมอบ (Non-deliverable Items)](#22-รายการที่ไม่ต้องส่งมอบ)
3. [การตรวจสอบและบำรุงรักษาระบบประจำ (Routine Maintenance)](#3-การตรวจสอบและบำรุงรักษาระบบประจำ)
    - 3.1 [การบำรุงรักษาระบบฐานข้อมูล](#31-การบำรุงรักษาระบบฐานข้อมูล)
    - 3.2 [การบำรุงรักษาเซิร์ฟเวอร์และระบบเครือข่าย](#32-การบำรุงรักษาเซิร์ฟเวอร์และระบบเครือข่าย)
4. [การบริหารจัดการเหตุการณ์และปัญหา (Incident and Problem Management)](#4-การบริหารจัดการเหตุการณ์และปัญหา)
    - 4.1 [การแจ้งเตือนเหตุการณ์](#41-การแจ้งเตือนเหตุการณ์)
    - 4.2 [การแก้ไขปัญหาและการตรวจสอบ (Root Cause Analysis)](#42-การแก้ไขปัญหาและการตรวจสอบ)
5. [การอัปเดตและการปรับปรุงระบบ (System Updates and Improvements)](#5-การอัปเดตและการปรับปรุงระบบ)
    - 5.1 [กระบวนการอัปเดตระบบ](#51-กระบวนการอัปเดตระบบ)
    - 5.2 [การทดสอบการอัปเดต](#52-การทดสอบการอัปเดต)

---

## 1. การตั้งค่าและการกำหนดค่าของระบบ

### 1.1 การตั้งค่าระบบ Production (Production Configuration)
- **เซิร์ฟเวอร์**: ใช้เซิร์ฟเวอร์ที่เชื่อถือได้ในระบบ Cloud เช่น AWS หรือ Google Cloud เพื่อรองรับการทำงานในระดับ Production
- **ฐานข้อมูล**: ใช้ฐานข้อมูล MySQL เวอร์ชันล่าสุดในการจัดเก็บข้อมูลลูกค้า การทำธุรกรรม และประวัติการเก็บขยะ
- **การแคชข้อมูล**: ใช้ Redis สำหรับการแคชข้อมูล เพื่อเพิ่มประสิทธิภาพในการตอบสนองของระบบ โดยเฉพาะข้อมูลการร้องขอและข้อมูลสถานะการเก็บขยะ
- **การรักษาความปลอดภัย**: ใช้ SSL/TLS ในการเข้ารหัสข้อมูลที่ส่งผ่านเครือข่าย และมีการตรวจสอบสิทธิ์การเข้าถึงด้วยระบบ OAuth 2.0
- **การสำรองข้อมูล**: มีการสำรองข้อมูลอัตโนมัติทุก 24 ชั่วโมง เพื่อป้องกันการสูญหายของข้อมูล

### 1.2 การตั้งค่าระบบ Development (Development Configuration)
- **สภาพแวดล้อมการพัฒนา**: ใช้ Docker ในการจำลองสภาพแวดล้อมการพัฒนาเหมือนกับ Production เพื่อลดความเสี่ยงจากการแตกต่างของสภาพแวดล้อม
- **การจัดการเวอร์ชัน**: ระบบถูกจัดการผ่าน Git โดยมีการใช้ branches สำหรับการพัฒนา ทดสอบ และ Production เพื่อควบคุมการเปลี่ยนแปลงของระบบ
- **การทดสอบระบบ**: มีการใช้เครื่องมือ CI/CD เช่น Jenkins หรือ GitLab CI เพื่ออัตโนมัติการทดสอบในทุกขั้นตอน

---

## 2. การควบคุมรายการกำหนดค่า

### 2.1 การควบคุมเวอร์ชัน (Version Control)
- ส่วนประกอบของระบบเช่น ฐานข้อมูล ซอฟต์แวร์ และ API ต่างๆ ถูกควบคุมเวอร์ชันโดยใช้ Git และระบบ CI/CD
- เวอร์ชันของแต่ละส่วนจะถูกตรวจสอบและอัปเดตอย่างสม่ำเสมอเพื่อความปลอดภัยและการทำงานที่มีประสิทธิภาพ
- **การบันทึกการเปลี่ยนแปลง (Changelog)**: มีการบันทึกการเปลี่ยนแปลงของระบบทุกครั้งที่มีการอัปเดต

### 2.2 รายการที่ไม่ต้องส่งมอบ (Non-deliverable Items)
รายการต่อไปนี้เป็นรายการที่ติดตามภายในองค์กร แต่ไม่ต้องส่งมอบแก่ลูกค้า:
1. **แผนโครงการ (Project Plan)**
2. **คำร้องขอเปลี่ยนแปลง (Change Request)**
3. **บันทึกการตรวจสอบและการทดสอบ (Test Cases and Reports)**
4. **รายงานความคืบหน้า (Progress Status Record)**
5. **บันทึกการประชุม (Meeting Records)**

---

## 3. การตรวจสอบและบำรุงรักษาระบบประจำ

### 3.1 การบำรุงรักษาระบบฐานข้อมูล
- ตรวจสอบและปรับแต่งฐานข้อมูล MySQL ให้ทำงานอย่างมีประสิทธิภาพ เช่น การปรับแต่งดัชนี (Index) การล้างแคช และการสำรองข้อมูล
- **การสำรองข้อมูล (Backup)**: ควรมีการสำรองข้อมูลทุกเดือนและจัดเก็บข้อมูลสำรองในที่ปลอดภัย

### 3.2 การบำรุงรักษาเซิร์ฟเวอร์และระบบเครือข่าย
- ตรวจสอบการทำงานของเซิร์ฟเวอร์เป็นระยะ เพื่อป้องกันการทำงานผิดพลาดที่อาจทำให้ระบบล่ม
- อัปเดตซอฟต์แวร์และเฟิร์มแวร์ของเซิร์ฟเวอร์และอุปกรณ์เครือข่ายเป็นประจำ
- ตรวจสอบความปลอดภัยของระบบโดยการสแกนหาช่องโหว่และทำการอัปเดตแพตช์ที่จำเป็น

---

## 4. การบริหารจัดการเหตุการณ์และปัญหา

### 4.1 การแจ้งเตือนเหตุการณ์
- มีการตั้งค่าระบบการแจ้งเตือนผ่านอีเมลและการแจ้งเตือนแบบเรียลไทม์ (real-time alerts) ในกรณีที่เกิดเหตุการณ์ผิดปกติในระบบ เช่น เซิร์ฟเวอร์ล่มหรือฐานข้อมูลเต็ม

### 4.2 การแก้ไขปัญหาและการตรวจสอบ (Root Cause Analysis)
- หลังจากเหตุการณ์ผิดปกติเกิดขึ้น ทีมงานต้องทำการตรวจสอบหาสาเหตุหลักของปัญหา และดำเนินการแก้ไขอย่างเหมาะสม
- มีการบันทึกและวิเคราะห์ปัญหาเพื่อป้องกันไม่ให้เกิดซ้ำในอนาคต
- กำหนด SLA 

---

## 5. การอัปเดตและการปรับปรุงระบบ

### 5.1 กระบวนการอัปเดตระบบ
- ระบบจะมีการอัปเดตเวอร์ชันใหม่ตามกำหนดการที่วางไว้ล่วงหน้า โดยอัปเดตทั้งฟีเจอร์ใหม่และการแก้ไขข้อบกพร่องที่พบในระบบ
- ก่อนการอัปเดต จะมีการสำรองข้อมูลและทดสอบการทำงานในสภาพแวดล้อมทดสอบ (staging) เพื่อป้องกันการทำงานผิดพลาดในระบบจริง

### 5.2 การทดสอบการอัปเดต
- การอัปเดตทุกครั้งจะผ่านการทดสอบทั้งในด้านความปลอดภัย ประสิทธิภาพ และความเข้ากันได้กับระบบอื่นๆ เพื่อให้มั่นใจว่าระบบทำงานได้ตามปกติ
- มีการทดสอบในหลายระดับ เช่น การทดสอบหน่วย (Unit Testing) การทดสอบการทำงานรวม (Integration Testing) และการทดสอบภาระงาน (Load Testing)

## 6.  SLA [Service Level Agreement]  
  
| ระดับความรุนแรง | ความหมาย                                  | ระยะเวลาในการแก้ไข | ช่องทางการติดต่อ                        | ช่วงเวลาทำการ               |
|-----------------|--------------------------------------------|--------------------|-----------------------------------------|----------------------------|
| Critical        | ปัญหาที่มีผลกระทบต่อการทำงานหลักของระบบทั้งหมด | ภายใน 6 ชั่วโมง    | โทร 063 629 6999 (ปริญญา)             | 24 ชั่วโมง                 |
| Major           | ปัญหาที่มีผลกระทบต่อการทำงานในส่วนสำคัญ แต่ไม่ทำให้ระบบหยุดทำงานทั้งหมด | ภายใน 3 วัน        | e-mail: support@symphosoft.com         | ทุกวัน ยกเว้นวันหยุดราชการ |
| Minor           | ปัญหาทั่วไปที่ไม่มีผลกระทบต่อการทำงานหลักของระบบ | ภายใน 2 สัปดาห์   | e-mail: support@symphosoft.com         | ทุกวัน ยกเว้นวันหยุดราชการ |  

## 7. ระยะเวลาการรับประกัน [Warranty Period]  
  

| ระยะเวลาการรับประกัน | เริ่ม              | สิ้นสุด             | ช่องทางการติดต่อ                              | ช่วงเวลาติดต่อ                          |
|----------------------|-------------------|--------------------|---------------------------------------------|--------------------------------------|
| 1 ปี               | 24 October 2024 | 24 October 2025 | email: symphosoft@gmail.com / call: 063 629 6999 | 8:30 - 17:30  วันจันทร์ - ศุกร์ ยกเว้นวันหยุดราชการ |  
  
