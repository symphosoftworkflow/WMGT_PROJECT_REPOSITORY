<img src="https://www.symphosoft.com/logo/symphosoftLogo.png" alt="Symphosoft Logo" width="200"/>

# เอกสาร บันทึกการตรวจอบตามข้อกำหนดของมาตรฐาน (VERIFICATION RESULT)

**ชื่อระบบงาน[TH]**: ระบบจัดการการจัดเก็บขยะรีไซเคิล  
**ชื่อระบบงาน[EN]**: Recycle Waste Collecting Management System  

---

**วันที่**:  31 พฤษภาคม พ.ศ. 2567  
**ผู้ได้รับการตรวจสอบ**:  

| ชื่อ             | ตำแหน่ง  | หน้าที่                                  |
|------------------|-----------|------------------------------------------|
| นายวีระ เนียมโภคะ | TL, AN    | วางแผนระบบ, วิเคราะห์และออกแบบฟังก์ชัน |  


  
  
**ผู้ตรวจสอบ**:  นางสาวปวริศา จันทรสถาพร (PM)  


***  <img src="https://www.symphosoft.com/signature_pawarisa.png"  width="400"/>         ***      
 ______________________________________________________________________________  [Signature]  

---

### เอกสาร การออกแบบระบบ (SYMSTEM SOFTWARE DESIGN)  

| ลำดับ | รายการ                                                                                                     | verified |
|-------|-------------------------------------------------------------------------------------------------------------|----------|
| 1     | ภาพรวมการออกแบบระบบ (System and Software Design Overview)                                                 | [x]      |
| 2     | การออกแบบระบบ (System Design)                                                                              | [x]      |
| 2.1   | แนวคิดการออกแบบสถาปัตยกรรมและมาตรฐาน (Architecture Concept Design and Standard)                         | [x]      |
| 2.2   | รายละเอียดการออกแบบระบบ (System Detail Design)                                                            | [x]      |
| 3     | การออกแบบซอฟต์แวร์ (Software Design)                                                                      | [x]      |
| 3.1   | แนวคิดการออกแบบสถาปัตยกรรมและมาตรฐาน (Architecture Concept Design and Standard)                         | [x]      |
| 3.2   | รายละเอียดการออกแบบซอฟต์แวร์ (Software Detail Design)                                                    | [x]      |
| 3.2.1 | การออกแบบสำหรับลูกค้า (Customers)                                                                         | [x]      |
| 3.2.2 | การออกแบบสำหรับผู้เก็บขยะ (Collectors)                                                                   | [x]      |
| 3.2.3 | การออกแบบสำหรับผู้ดูแลระบบ (Administrators)                                                              | [x]      |
| 3.3   | รายละเอียดส่วนติดต่อ (Interface Detail Design)                                                           | [x]      |
| 3.4   | การออกแบบข้อมูล (Data Element Design)                                                                     | [x]      |
| 4     | แผนภาพประกอบ (Diagrams)                                                                                   | [x]      |
| 4.1   | แผนภาพ Component (Component Diagram)                                                                      | [x]      |
| 4.2   | แผนภาพ Class (Class Diagram)                                                                              | [x]      |
| 4.3   | แผนภาพ Sequence (Sequence Diagram)                                                                        | [x]      |
| 4.4   | แผนภาพ Deployment (Deployment Diagram)                                                                    | [x]      |
| 4.5   | แผนภาพ Use Case (Use Case Diagram)                                                                        | [x]      |
| 4.6   | แผนภาพการออกแบบ API (API Design Diagram)                                                                 | [x]      |
| 4.7   | แผนภาพการไหลของผู้ใช้ (User Flow Diagram)                                                                | [x]      |
| 4.8   | แผนภาพ Enhanced Entity-Relationship (EER Model)                                                           | [x]      |
| 4.9   | Data Dictionary                                                                                            | [x]      |
| 5     | API Payload Specification                                                                                  | [x]      |
| 5.1   | Customer APIs                                                                                              | [x]      |
| 5.1.1 | Submit Request: POST /api/requests                                                                         | [x]      |
| 5.1.2 | View Request Status: GET /api/requests/{id}/status                                                         | [x]      |
| 5.1.3 | View Payment History: GET /api/payments/history                                                            | [x]      |
| 5.2   | Collector APIs                                                                                             | [x]      |
| 5.2.1 | View Assigned Requests: GET /api/collector/requests                                                        | [x]      |
| 5.2.2 | Update Collection Status: PUT /api/collector/requests/{id}/status                                          | [x]      |
| 5.3   | Admin APIs                                                                                                 | [x]      |
| 5.3.1 | View All Requests: GET /api/requests                                                                       | [x]      |
| 5.3.2 | Assign Collector: POST /api/requests/{id}/assign                                                           | [x]      |
| 5.3.3 | Process Payments: POST /api/payments/process                                                               | [x]      |
| 5.3.4 | Send Notifications: POST /api/notifications/send                                                           | [x]      |
| 5.4   | Notification API                                                                                           | [x]      |
| 5.4.1 | Send Notification: POST /api/notifications/send                                                            | [x]      |
| 6     | User Interface                                                                                             | [x]      |
| 6.1   | การออกแบบสำหรับลูกค้า (Customers)                                                                         | [x]      |
| 6.2   | การออกแบบสำหรับผู้เก็บขยะ (Collectors)                                                                   | [x]      |
| 6.3   | การออกแบบสำหรับผู้ดูแลระบบ (Administrators)                                                              | [x]      |  


---

**หมายเหตุ**:  
- ใช้เครื่องหมายในคอลัมน์ที่เหมาะสมเพื่อแสดงสถานะของแต่ละความต้องการ เช่น ติ๊ก "x" ในคอลัมน์ "verified" เมื่อตรวจสอบความถูกต้องแล้ว 
