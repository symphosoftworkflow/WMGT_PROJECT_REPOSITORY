<img src="https://www.symphosoft.com/logo/symphosoftLogo.png" alt="Symphosoft Logo" width="200"/>

# เอกสาร สรุปความต้องการของระบบงาน (SOFTWARE REQUIREMENT SPECIFICATION)

  
**ชื่อระบบงาน[TH]**: ระบบจัดการการจัดเก็บขยะรีไซเคิล  
**ชื่อระบบงาน[EN]**: Recycle Waste Collecting Management System  
  
    
**เวอร์ชัน**: 1.0  
**จัดทำโดย**: นายวีระ เนียมโภคะ (TL)  
**วันที่จัดทำเอกสาร**: [15 เมษายน พ.ศ. 2567]  
  
---

## ประวัติการจัดทำเอกสาร

| ลำดับ | เวอร์ชัน | รายละเอียดการดำเนินการ                 | ผู้ดำเนินการ | วันที่ดำเนินการ |
|-------|----------|-----------------------------------------|--------------|-----------------|
| 1     | 0.1      | จัดทำ สรุปความต้องการของระบบงาน         | นายวีระ เนียมโภคะ (TL)  | [10 เมษายน พ.ศ. 2567]        |
| 2     | 1.0      | อนุมัติ สรุปความต้องการของระบบงาน       | นางสาวปวริศา จันทรสถาพร (PM)  | [15 เมษายน พ.ศ. 2567]        |

---

## สารบัญ

1. [บทนำ (Introduction)](#1-บทนำ-introduction)  
2. [ความต้องการของระบบ (System Requirements)](#2-ความต้องการของระบบ-system-requirements)  
   - 2.1 ภาพรวมความต้องการของระบบ (System Requirement Overview)  
   - 2.2 ความสามารถของระบบ (Requirements Functionality)  
   - 2.3 ส่วนต่อประสานภายนอก (External Interfaces)  
3. [ความต้องการทางซอฟต์แวร์ (Software Requirements)](#3-ความต้องการทางซอฟต์แวร์-software-requirements)  
   - 3.1 ภาพรวมความต้องการทางซอฟต์แวร์ (Software Requirement Overview)  
   - 3.2 ความสามารถของระบบ (Requirements Functionality)  
   - 3.3 ส่วนต่อประสานภายนอก (External Interfaces)  
4. [ความต้องการที่ไม่ใช่การทำงานของระบบ (Non-functional Requirements)](#4-ความต้องการที่ไม่ใช่การทำงานของระบบ-non-functional-requirements)  
   - 4.1 ส่วนต่อประสานผู้ใช้ (User Interface)  
   - 4.2 การใช้งานง่าย (Usability and Ease of Use)  
   - 4.3 ประสิทธิภาพ (Efficiency)  
   - 4.4 ความน่าเชื่อถือ (Reliability)

---

## 1. บทนำ (Introduction)

Recycle Waste Collecting Management System เป็นระบบที่ใช้ในการจัดการคำร้องขอเก็บขยะรีไซเคิลจากลูกค้าและจัดการคำสั่งงานสำหรับผู้เก็บขยะ เพื่อประสิทธิภาพสูงสุดในการจัดการเส้นทางเก็บขยะและการชำระเงิน

---

## 2. ความต้องการของระบบ (System Requirements)

### 2.1 ภาพรวมความต้องการของระบบ (System Requirement Overview)
ระบบนี้ออกแบบมาเพื่อให้ลูกค้า ผู้เก็บขยะ และผู้ดูแลระบบ สามารถจัดการคำร้องขอเก็บขยะ ตรวจสอบสถานะ และชำระเงินได้อย่างรวดเร็วและง่ายดาย

### 2.2 ความสามารถของระบบ (Requirements Functionality)

#### 2.2.1 ความต้องการจากลูกค้า (Customers)

| Requirement ID | รายละเอียด |
|----------------|------------|
| REQ1.1         | ลูกค้าสามารถส่งคำร้องขอเก็บขยะโดยระบุข้อมูลที่จำเป็น เช่น สถานที่ วันที่และเวลา และรูปถ่ายของขยะ |
| REQ1.2         | ลูกค้าสามารถตรวจสอบสถานะคำร้อง เช่น "มอบหมายให้ผู้เก็บขยะ", "เก็บแล้ว", และ "จ่ายเงินแล้ว" |
| REQ1.3         | ลูกค้าสามารถดูประวัติการชำระเงินที่ได้รับจากการขายวัสดุรีไซเคิล |
| REQ1.4         | ลูกค้าสามารถตรวจสอบราคาวัสดุรีไซเคิลที่อัปเดตทุกวัน |

#### 2.2.2 ความต้องการจากผู้เก็บขยะ (Collectors)

| Requirement ID | รายละเอียด |
|----------------|------------|
| REQ2.1         | ผู้เก็บขยะสามารถดูคำร้องที่ได้รับมอบหมายจากผู้ดูแลระบบ |
| REQ2.2         | ผู้เก็บขยะสามารถยอมรับหรือปฏิเสธคำร้องที่ได้รับมอบหมาย |
| REQ2.3         | ผู้เก็บขยะสามารถจัดการเส้นทางการเก็บขยะเพื่อเพิ่มประสิทธิภาพ |
| REQ2.4         | ผู้เก็บขยะสามารถอัปเดตสถานะการเก็บขยะ เช่น น้ำหนัก ราคา และยอดรวม |

#### 2.2.3 ความต้องการจากผู้ดูแลระบบ (Administrators)

| Requirement ID | รายละเอียด |
|----------------|------------|
| REQ3.1         | ผู้ดูแลระบบสามารถตรวจสอบและมอบหมายคำร้องของลูกค้าให้กับผู้เก็บขยะที่เหมาะสม |
| REQ3.2         | ผู้ดูแลระบบสามารถตรวจสอบสถานะการเก็บขยะในเวลาจริง |
| REQ3.3         | ผู้ดูแลระบบสามารถจัดการและอัปเดตข้อมูลการชำระเงินของลูกค้า |
| REQ3.4         | ผู้ดูแลระบบสามารถกำหนดและอัปเดตราคาวัสดุรีไซเคิลประจำวัน |

### 2.3 ส่วนต่อประสานภายนอก (External Interfaces)
- ระบบเชื่อมต่อกับ **Payment Gateway** เพื่อให้บริการชำระเงินแก่ลูกค้า  
- ใช้ **Mapping API** เพื่อช่วยในการวางแผนเส้นทางและแสดงจุดเก็บขยะ

---

## 3. ความต้องการทางซอฟต์แวร์ (Software Requirements)

### 3.1 ภาพรวมความต้องการทางซอฟต์แวร์ (Software Requirement Overview)
Recycle Waste Collecting Management System พัฒนาด้วยเทคโนโลยี **Next.js** ที่ทำงานร่วมกับฐานข้อมูล **MySQL** และใช้ **Redis** ในการแคชข้อมูล เพื่อเพิ่มประสิทธิภาพการทำงานของระบบ

### 3.2 ความสามารถของระบบ (Requirements Functionality)
ระบบจะรองรับการทำงานดังนี้:
- รองรับคำร้องของลูกค้าได้ถึง 100 คำร้องพร้อมกัน
- ข้อมูลของลูกค้าจะถูกเข้ารหัสและมีการตรวจสอบสิทธิ์การเข้าถึง

### 3.3 ส่วนต่อประสานภายนอก (External Interfaces)
- ระบบเชื่อมต่อกับ **RabbitMQ** สำหรับการส่งข้อความระหว่างระบบต่างๆ เพื่อประสิทธิภาพในการประมวลผล

---

## 4. ความต้องการที่ไม่ใช่การทำงานของระบบ (Non-functional Requirements)

### 4.1 ส่วนต่อประสานผู้ใช้ (User Interface)
User Interface ถูกออกแบบมาให้ใช้งานง่าย โดยใช้ **NextUI** ในการจัดการส่วนติดต่อผู้ใช้ และ **Tailwind CSS** ในการตกแต่ง

### 4.2 การใช้งานง่าย (Usability and Ease of Use)
ระบบออกแบบมาให้ใช้งานง่ายสำหรับผู้ใช้ทุกกลุ่ม โดยผู้ใช้สามารถเข้าถึงฟังก์ชันที่ต้องการได้อย่างรวดเร็ว

### 4.3 ประสิทธิภาพ (Efficiency)
ใช้ **Redis** ในการแคชข้อมูลเพื่อเพิ่มความเร็วในการเข้าถึงข้อมูล และลดการโหลดของฐานข้อมูล

### 4.4 ความน่าเชื่อถือ (Reliability)
ระบบจะมีความเสถียรสูง ด้วยการออกแบบให้มีเวลาหยุดทำงาน (downtime) น้อยกว่า 0.5% ต่อเดือน

---

## รูปแบบของหน้าจอการใช้งาน (User Interface Design)

การออกแบบ UI สำหรับแอปพลิเคชันมือถือจะนำเสนอภาพของหน้าจอต่างๆ ตามที่กำหนดไว้ในไฟล์ `allUI.puml`

---
