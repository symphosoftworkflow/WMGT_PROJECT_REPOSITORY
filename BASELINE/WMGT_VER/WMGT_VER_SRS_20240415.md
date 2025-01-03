<img src="https://www.symphosoft.com/logo/symphosoftLogo.png" alt="Symphosoft Logo" width="200"/>

# เอกสาร บันทึกการตรวจอบตามข้อกำหนดของมาตรฐาน (VERIFICATION RESULT)

**ชื่อระบบงาน[TH]**: ระบบจัดการการจัดเก็บขยะรีไซเคิล  
**ชื่อระบบงาน[EN]**: Recycle Waste Collecting Management System  

---

**วันที่**:  15 เมษายน พ.ศ. 2567  
**ผู้ได้รับการตรวจสอบ**:  

| ชื่อ             | ตำแหน่ง    | หน้าที่                                  |
|------------------|------------|------------------------------------------|
| นายวีระ เนียมโภคะ | TL, AN     | วางแผนระบบ, วิเคราะห์และออกแบบฟังก์ชัน |  
  

**ผู้ตรวจสอบ**:  นางสาวปวริศา จันทรสถาพร (PM)  


***  <img src="https://www.symphosoft.com/signature_pawarisa.png"  width="400"/>         ***      
 ______________________________________________________________________________  [Signature]  

---

### เอกสาร สรุปความต้องการของระบบงาน (SOFTWARE REQUIREMENT SPECIFICATION)  


| ลำดับ | รายการ                                                                                                     | verified |
|-------|-------------------------------------------------------------------------------------------------------------|----------|
| 1     | บทนำ (Introduction)                                                                                        | [x]      |
| 2     | ความต้องการของระบบ (System Requirements)                                                                  | [x]      |
| 2.1   | ภาพรวมความต้องการของระบบ (System Requirement Overview)                                                   | [x]      |
|       | ระบบนี้ออกแบบมาเพื่อให้ลูกค้า ผู้เก็บขยะ และผู้ดูแลระบบ สามารถจัดการคำร้องขอเก็บขยะ ตรวจสอบสถานะ และชำระเงินได้อย่างรวดเร็วและง่ายดาย | [x]      |
| 2.2   | ความสามารถของระบบ (Requirements Functionality)                                                            | [x]      |
| 2.2.1 | ความต้องการจากลูกค้า (Customers):                                                                          | [x]      |
|       | - REQ1.1 ลูกค้าสามารถส่งคำร้องขอเก็บขยะโดยระบุข้อมูลที่จำเป็น เช่น สถานที่ วันที่และเวลา และรูปถ่ายของขยะ   | [x]      |
|       | - REQ1.2 ลูกค้าสามารถตรวจสอบสถานะคำร้อง เช่น "มอบหมายให้ผู้เก็บขยะ", "เก็บแล้ว", และ "จ่ายเงินแล้ว"         | [x]      |
|       | - REQ1.3 ลูกค้าสามารถดูประวัติการชำระเงินที่ได้รับจากการขายวัสดุรีไซเคิล                                   | [x]      |
|       | - REQ1.4 ลูกค้าสามารถตรวจสอบราคาวัสดุรีไซเคิลที่อัปเดตทุกวัน                                              | [x]      |
| 2.2.2 | ความต้องการจากผู้เก็บขยะ (Collectors):                                                                     | [x]      |
|       | - REQ2.1 ผู้เก็บขยะสามารถดูคำร้องที่ได้รับมอบหมายจากผู้ดูแลระบบ                                             | [x]      |
|       | - REQ2.2 ผู้เก็บขยะสามารถยอมรับหรือปฏิเสธคำร้องที่ได้รับมอบหมาย                                             | [x]      |
|       | - REQ2.3 ผู้เก็บขยะสามารถจัดการเส้นทางการเก็บขยะเพื่อเพิ่มประสิทธิภาพ                                       | [x]      |
|       | - REQ2.4 ผู้เก็บขยะสามารถอัปเดตสถานะการเก็บขยะ เช่น น้ำหนัก ราคา และยอดรวม                                  | [x]      |
| 2.2.3 | ความต้องการจากผู้ดูแลระบบ (Administrators):                                                                | [x]      |
|       | - REQ3.1 ผู้ดูแลระบบสามารถตรวจสอบและมอบหมายคำร้องของลูกค้าให้กับผู้เก็บขยะที่เหมาะสม                        | [x]      |
|       | - REQ3.2 ผู้ดูแลระบบสามารถตรวจสอบสถานะการเก็บขยะในเวลาจริง                                                  | [x]      |
|       | - REQ3.3 ผู้ดูแลระบบสามารถจัดการและอัปเดตข้อมูลการชำระเงินของลูกค้า                                         | [x]      |
|       | - REQ3.4 ผู้ดูแลระบบสามารถกำหนดและอัปเดตราคาวัสดุรีไซเคิลประจำวัน                                          | [x]      |
| 2.3   | ส่วนต่อประสานภายนอก (External Interfaces):                                                                 | [x]      |
|       | - ระบบเชื่อมต่อกับ **Payment Gateway** เพื่อให้บริการชำระเงินแก่ลูกค้า                                       | [x]      |
|       | - ใช้ **Mapping API** เพื่อช่วยในการวางแผนเส้นทางและแสดงจุดเก็บขยะ                                          | [x]      |
| 3     | ความต้องการทางซอฟต์แวร์ (Software Requirements)                                                           | [x]      |
| 3.1   | ภาพรวมความต้องการทางซอฟต์แวร์ (Software Requirement Overview)                                            | [x]      |
| 3.2   | ความสามารถของระบบ (Requirements Functionality)                                                            | [x]      |
| 3.3   | ส่วนต่อประสานภายนอก (External Interfaces)                                                                | [x]      |
| 4     | ความต้องการที่ไม่ใช่การทำงานของระบบ (Non-functional Requirements)                                         | [x]      |
| 4.1   | ส่วนต่อประสานผู้ใช้ (User Interface)                                                                      | [x]      |
| 4.2   | การใช้งานง่าย (Usability and Ease of Use)                                                                 | [x]      |
| 4.3   | ประสิทธิภาพ (Efficiency)                                                                                  | [x]      |
| 4.4   | ความน่าเชื่อถือ (Reliability)                                                                             | [x]      |  

---

**หมายเหตุ**:  
- ใช้เครื่องหมายในคอลัมน์ที่เหมาะสมเพื่อแสดงสถานะของแต่ละความต้องการ เช่น ติ๊ก "x" ในคอลัมน์ "verified" เมื่อตรวจสอบความถูกต้องแล้ว  
