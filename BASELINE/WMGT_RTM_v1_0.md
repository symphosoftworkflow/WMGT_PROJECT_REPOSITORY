<img src="https://www.symphosoft.com/logo/symphosoftLogo.png" alt="Symphosoft Logo" width="200"/>

# Traceability Record Document  
**ระบบจัดการการเก็บขยะรีไซเคิล (Recycle Waste Collecting Management System)**  
  
**ชื่อระบบงาน[TH]**: ระบบจัดการการจัดเก็บขยะรีไซเคิล  
**ชื่อระบบงาน[EN]**: Recycle Waste Collecting Management System  
**เวอร์ชัน**: 1.0  
**จัดทำโดย**: นายวีระ เนียมโภคะ (TL,AN) 
**วันที่อนุมัติเอกสาร**: [31 พฤษภาคม พ.ศ. 2567]  

---

## ประวัติการจัดทำเอกสาร

| ลำดับ | เวอร์ชัน | รายละเอียดการดำเนินการ | ผู้ดำเนินการ | วันที่ดำเนินการ |
|-------|----------|-------------------------|--------------|-----------------|
| 1     | 0.1      | จัดทำ Traceability Record | นายวีระ เนียมโภคะ| [28 พฤษภาคม พ.ศ. 2567]        |
| 2     | 1.0      | อนุมัติ Traceability Record | นางสาวปวริศา จันทรสถาพร | [31 พฤษภาคม พ.ศ. 2567]        |

---

| เลขที่ความต้องการ | สรุปสาระสำคัญความต้องการของระบบ                                                                                                                                 | Software Design           | Software Components | Unit Test | Test Cases |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|---------------------|-----------|------------|
| REQ1.1             | ลูกค้าสามารถส่งคำร้องขอเก็บขยะโดยระบุข้อมูลที่จำเป็น เช่น สถานที่ วันที่และเวลา และรูปถ่ายของขยะ                                                                  | DES1.1                    | [SC1.1](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID1.1](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ1.2             | ลูกค้าสามารถตรวจสอบสถานะคำร้อง เช่น "มอบหมายให้ผู้เก็บขยะ", "เก็บแล้ว", และ "จ่ายเงินแล้ว"                                                                       | DES1.2                    | [SC1.2](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID1.2](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ1.3             | ลูกค้าสามารถดูประวัติการชำระเงินที่ได้รับจากการขายวัสดุรีไซเคิล                                                                                                   | DES1.3                    | [SC1.3](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID1.3](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ1.4             | ลูกค้าสามารถตรวจสอบราคาวัสดุรีไซเคิลที่อัปเดตทุกวัน                                                                                                               | DES1.4                    | [SC1.4](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID1.4](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ2.1             | ผู้เก็บขยะสามารถดูคำร้องที่ได้รับมอบหมายจากผู้ดูแลระบบ                                                                                                             | DES2.1                    | [SC2.1](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID2.1](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ2.2             | ผู้เก็บขยะสามารถยอมรับหรือปฏิเสธคำร้องที่ได้รับมอบหมาย                                                                                                            | DES2.2                    | [SC2.2](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID2.2](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ2.3             | ผู้เก็บขยะสามารถจัดการเส้นทางการเก็บขยะเพื่อเพิ่มประสิทธิภาพ                                                                                                     | DES2.3                    | [SC2.3](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID2.3](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ2.4             | ผู้เก็บขยะสามารถอัปเดตสถานะการเก็บขยะ เช่น น้ำหนัก ราคา และยอดรวม                                                                                                | DES2.4                    | [SC2.4](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID2.4](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ3.1             | ผู้ดูแลระบบสามารถตรวจสอบและมอบหมายคำร้องของลูกค้าให้กับผู้เก็บขยะที่เหมาะสม                                                                                        | DES3.1                    | [SC3.1](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID3.1](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ3.2             | ผู้ดูแลระบบสามารถตรวจสอบสถานะการเก็บขยะในเวลาจริง                                                                                                                 | DES3.2                    | [SC3.2](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID3.2](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ3.3             | ผู้ดูแลระบบสามารถจัดการและอัปเดตข้อมูลการชำระเงินของลูกค้า                                                                                                        | DES3.3                    | [SC3.3](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID3.3](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |
| REQ3.4             | ผู้ดูแลระบบสามารถกำหนดและอัปเดตราคาวัสดุรีไซเคิลประจำวัน                                                                                                         | DES3.4                    | [SC3.4](https://github.com/symphosoftworkflow/PROJECTID0001_RECYCLE_WASTE_MGT/tree/main/app) | pass      | [TCID3.4](https://symphosoftworkflow.github.io/WMGT_PROJECT_REPOSITORY/BASELINE/WMGT_TP_v1_0) |