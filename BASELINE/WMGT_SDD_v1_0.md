<img src="https://www.symphosoft.com/logo/symphosoftLogo.png" alt="Symphosoft Logo" width="200"/>

# เอกสาร การออกแบบระบบ (SYMSTEM SOFTWARE DESIGN)  
  

**ชื่อระบบงาน[TH]**: ระบบจัดการการจัดเก็บขยะรีไซเคิล  
**ชื่อระบบงาน[EN]**: Recycle Waste Collecting Management System  
**เวอร์ชัน**: 1.0  
**จัดทำโดย**: นายวีระ เนียมโภคะ (TL) 
**วันที่อนุมัติเอกสาร**: [31 พฤษภาคม พ.ศ. 2567]  

---

## ประวัติการจัดทำเอกสาร

| ลำดับ | เวอร์ชัน | รายละเอียดการดำเนินการ | ผู้ดำเนินการ | วันที่ดำเนินการ |
|-------|----------|-------------------------|--------------|-----------------|
| 1     | 0.1      | จัดทำ Software Design Document | นายวีระ เนียมโภคะ| [28 พฤษภาคม พ.ศ. 2567]        |
| 2     | 1.0      | อนุมัติ Software Design Document | นางสาวปวริศา จันทรสถาพร | [31 พฤษภาคม พ.ศ. 2567]        |

---

## สารบัญ

1. [ภาพรวมการออกแบบระบบ (System and Software Design Overview)](#1-ภาพรวมการออกแบบระบบ)
2. [การออกแบบระบบ (System Design)](#2-การออกแบบระบบ)
   - 2.1 แนวคิดการออกแบบสถาปัตยกรรมและมาตรฐาน (Architecture Concept Design and Standard)
   - 2.2 รายละเอียดการออกแบบระบบ (System Detail Design)
3. [การออกแบบซอฟต์แวร์ (Software Design)](#3-การออกแบบซอฟต์แวร์)
   - 3.1 แนวคิดการออกแบบสถาปัตยกรรมและมาตรฐาน (Architecture Concept Design and Standard)
   - 3.2 รายละเอียดการออกแบบซอฟต์แวร์ (Software Detail Design)
   - 3.3 รายละเอียดส่วนติดต่อ (Interface Detail Design)
   - 3.4 การออกแบบข้อมูล (Data Element Design)
4. [แผนภาพประกอบ (Diagrams)](#4-แผนภาพประกอบ)
   - 4.1 แผนภาพ Component (Component Diagram)
   - 4.2 แผนภาพ Class (Class Diagram)
   - 4.3 แผนภาพ Sequence (Sequence Diagram)
   - 4.4 แผนภาพ Deployment (Deployment Diagram)
   - 4.5 แผนภาพ Use Case (Use Case Diagram)
   - 4.6 แผนภาพการออกแบบ API (API Design Diagram)
   - 4.7 แผนภาพการไหลของผู้ใช้ (User Flow Diagram)
5. [API Payload Specification](#5-api-payload-specification)

---

## 1. ภาพรวมการออกแบบระบบ (System and Software Design Overview)

Recycle Waste Collecting Management System ออกแบบมาเพื่อจัดการการเก็บขยะรีไซเคิลจากลูกค้า โดยผู้ใช้งานจะประกอบไปด้วยผู้เก็บขยะ ลูกค้า และผู้ดูแลระบบ เพื่อให้การจัดการเส้นทางการเก็บขยะมีประสิทธิภาพสูงสุด

---

## 2. การออกแบบระบบ (System Design)

### 2.1 แนวคิดการออกแบบสถาปัตยกรรมและมาตรฐาน (Architecture Concept Design and Standard)
ระบบนี้ใช้สถาปัตยกรรมแบบ **Microservices** และมีการเชื่อมต่อระหว่างบริการผ่าน **RabbitMQ** เพื่อเพิ่มประสิทธิภาพในการประมวลผลการสื่อสารระหว่างระบบย่อย

### 2.2 รายละเอียดการออกแบบระบบ (System Detail Design)

- ระบบเก็บขยะรีไซเคิลประกอบไปด้วยบริการหลัก 3 บริการ: บริการการจัดการลูกค้า บริการการจัดการคำร้อง และบริการการจัดการชำระเงิน
- การเชื่อมต่อระหว่างบริการใช้ **REST API** และ **WebSocket** สำหรับการอัปเดตสถานะทันที

---

## 3. การออกแบบซอฟต์แวร์ (Software Design)

### 3.1 แนวคิดการออกแบบสถาปัตยกรรมและมาตรฐาน (Architecture Concept Design and Standard)
ระบบนี้พัฒนาโดยใช้ **Next.js** สำหรับ Frontend และ **Node.js** สำหรับ Backend ที่เชื่อมต่อกับฐานข้อมูล **MySQL** และการแคชข้อมูลด้วย **Redis**

### 3.2 รายละเอียดการออกแบบซอฟต์แวร์ (Software Detail Design)

#### 3.2.1 การออกแบบสำหรับลูกค้า (Customers)

| Design ID | รายละเอียดการออกแบบ |
|-----------|----------------------|
| DES1.1    | หน้าจอส่งคำร้องขอเก็บขยะได้ โดยมีฟอร์มระบุสถานที่ วันที่ เวลา และแนบรูปถ่ายของขยะผ่านแอปพลิเคชันมือถือหรือเว็บไซต์ |
| DES1.2    | หน้าจอแสดงสถานะคำร้อง เช่น "มอบหมายให้ผู้เก็บขยะ", "เก็บแล้ว", และ "จ่ายเงินแล้ว" โดยใช้ฟีเจอร์การแจ้งเตือนเรียลไทม์ (real-time notification) |
| DES1.3    | หน้าจอแสดงประวัติการชำระเงินและยอดขายจากวัสดุรีไซเคิลที่ระบบจัดการเก็บไว้ในฐานข้อมูล |
| DES1.4    | หน้าจอแสดงข้อมูลราคาวัสดุรีไซเคิลอัปเดตทุกวันผ่าน API เชื่อมต่อกับแหล่งข้อมูลภายนอก และแสดงผลในหน้าราคาวัสดุ |

#### 3.2.2 การออกแบบสำหรับผู้เก็บขยะ (Collectors)

| Design ID | รายละเอียดการออกแบบ |
|-----------|----------------------|
| DES2.1    | หน้าจอแสดงคำร้องที่ได้รับมอบหมายจากผู้ดูแลระบบ เรียงตามเวลา |
| DES2.2    | หน้าจอที่ให้ผู้เก็บขยะสามารถยอมรับหรือปฏิเสธคำร้องที่ได้รับมอบหมายผ่านแอปพลิเคชันมือถือ พร้อมบันทึกสถานะลงในฐานข้อมูล |
| DES2.3    | หน้าจอแสดงใช้งานเส้นทางการเก็บขยะผ่านการบูรณาการกับ **Mapping API** เพื่อเพิ่มประสิทธิภาพการจัดการเส้นทาง |
| DES2.4    | หน้าจออัปเดตสถานะการเก็บขยะ เช่น น้ำหนัก ราคา และยอดรวม โดยข้อมูลเหล่านี้จะถูกบันทึกและคำนวณในระบบแบบเรียลไทม์ |

#### 3.2.3 การออกแบบสำหรับผู้ดูแลระบบ (Administrators)

| Design ID | รายละเอียดการออกแบบ |
|-----------|----------------------|
| DES3.1    | หน้าจอให้ผู้ดูแลระบบสามารถตรวจสอบคำร้องของลูกค้าและมอบหมายงานให้กับผู้เก็บขยะที่เหมาะสมผ่านหน้าจัดการภายใน |
| DES3.2    | หน้าจอให้ผู้ดูแลระบบสามารถดูสถานะการเก็บขยะในเวลาจริงผ่านแดชบอร์ดที่เชื่อมต่อกับระบบฐานข้อมูลและแจ้งเตือนสถานะ |
| DES3.3    | หน้าจอให้ผู้ดูแลระบบสามารถจัดการข้อมูลการชำระเงินของลูกค้าและอัปเดตข้อมูลที่เกี่ยวข้องกับคำร้องได้อย่างรวดเร็ว |
| DES3.4    | หน้าจอให้ผู้ดูแลระบบสามารถเข้าถึงฟังก์ชันการปรับปรุงราคาวัสดุรีไซเคิลรายวันในฐานข้อมูล ซึ่งจะถูกแสดงผลให้ลูกค้าทันทีผ่านระบบแสดงผลหน้าเว็บ |

### 3.3 รายละเอียดส่วนติดต่อ (Interface Detail Design)
- การเชื่อมต่อระหว่างระบบใช้ **REST API** โดยส่งข้อมูลในรูปแบบ **JSON**
- ระบบ Frontend ใช้ **Tailwind CSS** สำหรับการจัดการ UI

### 3.4 การออกแบบข้อมูล (Data Element Design)
- ระบบจัดเก็บข้อมูลการชำระเงินและคำร้องของลูกค้าในฐานข้อมูล **MySQL** โดยมี ERD ที่จะนำเสนอในส่วนของแผนภาพประกอบ

---

## 4. แผนภาพประกอบ (Diagrams)

### 4.1 แผนภาพ Component (Component Diagram)
![Component Diagram](https://symphosoft.com/wmgt/APIDesignDiagram.svg)

### 4.2 แผนภาพ Class (Class Diagram)
![Class Diagram](https://symphosoft.com/wmgt/ClassDiagramInternalStructure.svg)

### 4.3 แผนภาพ Sequence (Sequence Diagram)
![Sequence Diagram](https://symphosoft.com/wmgt/SequenceDiagram.png)

### 4.4 แผนภาพ Deployment (Deployment Diagram)
![Deployment Diagram](https://symphosoft.com/wmgt/DeploymentDiagram.svg)

### 4.5 แผนภาพ Use Case (Use Case Diagram)
![Use Case Diagram](https://symphosoft.com/wmgt/UseCaseDiagram.svg)

### 4.6 แผนภาพการออกแบบ API (API Design Diagram)
![API Design Diagram](https://symphosoft.com/wmgt/APIDesignDiagram.svg)

### 4.7 แผนภาพการไหลของผู้ใช้ (User Flow Diagram)
![User Flow Diagram](https://symphosoft.com/wmgt/UserFlowDiagram.svg)

### 4.8 แผนภาพ Enhanced Entity-Relationship (EER Model)  
![EER Diagram](https://symphosoft.com/wmgt/EerDiagramV3.svg)   
   
### 4.9 Data Dictionary   

| **Table Name**   | **Column Name**      | **Data Type**         | **Description**                                      | **Constraints**                           | **Default Value**   |
|------------------|----------------------|------------------------|------------------------------------------------------|-------------------------------------------|----------------------|
| **User**         | id                   | INT                    | Unique identifier for each user                      | Primary Key, Auto Increment               |                      |
|                  | name                 | VARCHAR(100)           | Name of the user                                     | NOT NULL                                  |                      |
|                  | email                | VARCHAR(100)           | Email address of the user                            | NOT NULL, Unique                          |                      |
|                  | role                 | ENUM                   | Role of the user (Customer, Collector, Administrator) | NOT NULL                                  |                      |
|                  | password             | VARCHAR(255)           | Password hash for authentication                     | NOT NULL                                  |                      |
| **Request**      | id                   | INT                    | Unique identifier for each request                   | Primary Key, Auto Increment               |                      |
|                  | customerId           | INT                    | ID of the customer who created the request           | Foreign Key → User(id), NOT NULL          |                      |
|                  | location             | VARCHAR(255)           | Location of the collection                           | NOT NULL                                  |                      |
|                  | date                 | DATE                   | Requested date for collection                        | NOT NULL                                  |                      |
|                  | time                 | ENUM                   | Preferred time for collection (BeforeNoon, AfterNoon) | NOT NULL                                  |                      |
|                  | status               | ENUM                   | Status of the request (Pending, Assigned, Collected, Paid) | NOT NULL                      | 'Pending'            |
|                  | photos               | TEXT                   | Photos of the waste (comma-separated URLs)           |                                           |                      |
| **Assignment**   | id                   | INT                    | Unique identifier for each assignment                | Primary Key, Auto Increment               |                      |
|                  | requestId            | INT                    | ID of the request being assigned                     | Foreign Key → Request(id), NOT NULL       |                      |
|                  | collectorId          | INT                    | ID of the collector assigned to the request          | Foreign Key → User(id), NULLABLE          | NULL                 |
|                  | routePlan            | VARCHAR(255)           | Optimized route details for collection               |                                           |                      |
|                  | status               | ENUM                   | Status of assignment (Assigned, Accepted, Completed) | NOT NULL                                  | 'Assigned'           |
| **Collection**   | id                   | INT                    | Unique identifier for each collection record         | Primary Key, Auto Increment               |                      |
|                  | requestId            | INT                    | ID of the request collected                          | Foreign Key → Request(id), NOT NULL       |                      |
|                  | collectorId          | INT                    | ID of the collector who handled the collection       | Foreign Key → User(id), NULLABLE          | NULL                 |
|                  | itemName             | VARCHAR(255)           | Name of the collected item                           | NOT NULL                                  |                      |
|                  | weight               | FLOAT                  | Weight of collected material                         | NOT NULL                                  |                      |
|                  | pricePerKg           | FLOAT                  | Price per kilogram for the material                  | NOT NULL                                  |                      |
|                  | totalAmount          | FLOAT                  | Total amount to be paid                              | NOT NULL                                  |                      |
|                  | collectionDate       | DATE                   | Date of collection                                   | NOT NULL                                  |                      |
| **Payment**      | id                   | INT                    | Unique identifier for each payment                   | Primary Key, Auto Increment               |                      |
|                  | requestId            | INT                    | ID of the request being paid                         | Foreign Key → Request(id), NOT NULL       |                      |
|                  | customerId           | INT                    | ID of the customer receiving payment                 | Foreign Key → User(id), NOT NULL          |                      |
|                  | amount               | FLOAT                  | Amount paid to the customer                          | NOT NULL                                  |                      |
|                  | paymentDate          | DATE                   | Date of payment                                      | NOT NULL                                  |                      |
|                  | paymentSlip          | VARCHAR(255)           | File path or URL to payment slip                     |                                           |                      |
| **Notification** | id                   | INT                    | Unique identifier for each notification              | Primary Key, Auto Increment               |                      |
|                  | recipientId          | INT                    | ID of the user receiving the notification            | Foreign Key → User(id), NOT NULL          |                      |
|                  | message              | TEXT                   | Content of the notification                          | NOT NULL                                  |                      |
|                  | status               | ENUM                   | Status of notification (Sent, Delivered, Read)       | NOT NULL                                  | 'Sent'               |
|                  | notificationDate     | DATE                   | Date the notification was sent                       | NOT NULL                                  |                      |  

---

## 5. API Payload Specification

```markdown
Detailed API Design:

1. Request Management API (Customer Flow)

1.1. Submit a New Request

• Endpoint: POST /api/requests

• Purpose: Allows the customer to submit a new waste collection request.

• Request Payload:


{
"customerId": 123,
"location": "123 Main St, City",
"date": "2024-10-19",
"time": "After noon",
"photos": ["photo1.jpg", "photo2.jpg"]
}


• Response Payload (on success):


{
"requestId": 456,
"status": "PENDING",
"message": "Request submitted successfully."
}


• HTTP Status Codes:

• 201 Created: Request successfully created.

• 400 Bad Request: Invalid data provided.


1.2. View Request Status

• Endpoint: GET /api/requests/{id}/status

• Purpose: Allows the customer to check the status of their request.

• Response Payload:


{
"requestId": 456,
"status": "ASSIGNED", // Can be PENDING, ASSIGNED, COLLECTED, PAID
"collector": {
"id": 789,
"name": "John Doe"
},
"message": "Your request has been assigned to a collector."
}


• HTTP Status Codes:

• 200 OK: Request status retrieved successfully.

• 404 Not Found: Request not found.


2. Collector API (Collector Flow)

2.1. View Assigned Requests

• Endpoint: GET /api/collector/requests

• Purpose: Collector can view all assigned requests.

• Response Payload:


[
{
"requestId": 456,
"customerId": 123,
"location": "123 Main St, City",
"date": "2024-10-19",
"status": "ASSIGNED"
},
{
"requestId": 457,
"customerId": 124,
"location": "456 Elm St, City",
"date": "2024-10-20",
"status": "ASSIGNED"
}
]


• HTTP Status Codes:

• 200 OK: Requests retrieved successfully.

• 404 Not Found: No requests assigned to the collector.


2.2. Update Collection Status

• Endpoint: PUT /api/collector/requests/{id}/status

• Purpose: Allows the collector to update the status of the request after collection.

• Request Payload:


{
"status": "COLLECTED",
"weight": 120.5,
"pricePerKg": 2.5,
"totalAmount": 301.25
}


• Response Payload (on success):


{
"requestId": 456,
"status": "COLLECTED",
"totalAmount": 301.25,
"message": "Collection details updated successfully."
}


• HTTP Status Codes:

• 200 OK: Status updated successfully.

• 400 Bad Request: Invalid data provided.

• 404 Not Found: Request not found.


3. Admin API (Admin Flow)

3.1. View All Requests

• Endpoint: GET /api/requests

• Purpose: Admin can view all customer requests.

• Response Payload:


[
{
"requestId": 456,
"customerId": 123,
"status": "PENDING",
"date": "2024-10-19",
"location": "123 Main St"
},
{
"requestId": 457,
"customerId": 124,
"status": "ASSIGNED",
"date": "2024-10-20",
"location": "456 Elm St"
}
]


• HTTP Status Codes:

• 200 OK: Requests retrieved successfully.


3.2. Assign Collector to Request

• Endpoint: POST /api/requests/{id}/assign

• Purpose: Admin assigns a collector to a customer request.

• Request Payload:


{
"collectorId": 789,
"routePlan": "Optimal route for 3 locations"
}


• Response Payload (on success):


{
"requestId": 456,
"status": "ASSIGNED",
"collectorId": 789,
"message": "Collector assigned successfully."
}


• HTTP Status Codes:

• 200 OK: Collector assigned successfully.

• 404 Not Found: Request or collector not found.


3.3. Process Payments

• Endpoint: POST /api/payments/process

• Purpose: Admin processes payment for collected waste.

• Request Payload:


{
"requestId": 456,
"customerId": 123,
"totalAmount": 301.25,
"paymentSlip": "payment_slip_456.jpg"
}


• Response Payload (on success):


{
"requestId": 456,
"status": "PAID",
"totalAmount": 301.25,
"paymentSlip": "payment_slip_456.jpg",
"message": "Payment processed successfully."
}


• HTTP Status Codes:

• 200 OK: Payment processed successfully.

• 400 Bad Request: Invalid data provided.


4. Notification API

4.1. Send Notification

• Endpoint: POST /api/notifications/send

• Purpose: Admin can send notifications to users (Customers, Collectors).

• Request Payload:


{
"recipientId": 123,
"message": "Your waste collection request has been assigned to a collector."
}


• Response Payload (on success):


{
"notificationId": 789,
"status": "SENT",
"message": "Notification sent successfully."
}


• HTTP Status Codes:

• 200 OK: Notification sent successfully.

• 400 Bad Request: Invalid data provided.


API Design Overview:

• Customer APIs:

• Submit Request: POST /api/requests

• View Request Status: GET /api/requests/{id}/status

• View Payment History: GET /api/payments/history

• Collector APIs:

• View Assigned Requests: GET /api/collector/requests

• Update Collection Status: PUT /api/collector/requests/{id}/status

• Admin APIs:

• View All Requests: GET /api/requests

• Assign Collector: POST /api/requests/{id}/assign

• Process Payments: POST /api/payments/process

• Send Notifications: POST /api/notifications/send
```

---

## 5. User Interface

#### 5.2.1 การออกแบบสำหรับลูกค้า (Customers)  

| Design ID | UI Design                                                                                 |
|-----------|--------------------------------------------------------------------------------------------|
| DES1.1    | ![UI Design](https://www.symphosoft.com/wmgt/des/des11.jpg)                                |
| DES1.2    | ![UI Design](https://www.symphosoft.com/wmgt/des/des12.jpg)                                |
| DES1.3    | ![UI Design](https://www.symphosoft.com/wmgt/des/des13.jpg)                                |
| DES1.4    | ![UI Design](https://www.symphosoft.com/wmgt/des/des14.jpg)                                |  


#### 5.2.2 การออกแบบสำหรับผู้เก็บขยะ (Collectors)  

| Design ID | UI Design                                                                                 |
|-----------|--------------------------------------------------------------------------------------------|
| DES2.1    | ![UI Design](https://www.symphosoft.com/wmgt/des/des21.jpg)                                |
| DES2.2    | ![UI Design](https://www.symphosoft.com/wmgt/des/des22.jpg)                                |
| DES2.3    | ![UI Design](https://www.symphosoft.com/wmgt/des/des23.jpg)                                |
| DES2.4    | ![UI Design](https://www.symphosoft.com/wmgt/des/des24.jpg)                                |  

#### 5.2.3 การออกแบบสำหรับผู้ดูแลระบบ (Administrators)  

| Design ID | UI Design                                                                                 |
|-----------|--------------------------------------------------------------------------------------------|
| DES3.1    | ![UI Design](https://www.symphosoft.com/wmgt/des/des31.jpg)                                |
| DES3.2    | ![UI Design](https://www.symphosoft.com/wmgt/des/des32.jpg)                                |
| DES3.3    | ![UI Design](https://www.symphosoft.com/wmgt/des/des33.jpg)                                |
| DES3.4    | ![UI Design](https://www.symphosoft.com/wmgt/des/des34.jpg)                                |  

