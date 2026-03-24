# ข้อมูลพจนานุกรม (Data Dictionary) - Vehicle Loan Default Prediction

ตารางนี้รวบรวมคำอธิบายของคุณสมบัติ (Features) ต่างๆ ในชุดข้อมูล โดยระบุถึงที่มาของข้อมูลและความพร้อมใช้งานในช่วงเวลาที่มีการประเมิน (Scoring) เพื่อให้เห็นภาพรวมของข้อมูลที่ใช้ในการทำนายการผิดนัดชำระหนี้

| Variable Name | Label | Description | Area | Value | Source |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `UNIQUEID` | **UniqueID** | รหัสอ้างอิงเฉพาะของสัญญาเงินกู้ | การสมัคร (Application) | ตัวเลขรันลำดับ (ID) | **มี** (ระบบสร้างให้ทันที) |
| `LOAN_DEFAULT` | **loan_default** | สถานะการผิดนัดชำระหนี้ (เป้าหมายที่ต้องการทำนาย) | หลังเบิกจ่าย (Post-Disbursal) | 0 (ปกติ), 1 (ผิดนัดชำระ) | **ไม่มี** (เป็นสิ่งที่ต้องทำนาย) |
| `DISBURSED_AMOUNT` | **disbursed_amount** | ยอดเงินกู้ที่อนุมัติและโอนให้ลูกค้าจริง | การเบิกจ่าย (Disbursal) | หลักหมื่น - หลักแสน (ตามราคารถ) | **มี** (ทราบยอดที่จะอนุมัติ) |
| `ASSET_COST` | **asset_cost** | ราคารถที่นำมาขอสินเชื่อ | การสมัคร (Application) | หลักหมื่น - หลักแสน | **มี** (ทราบจากใบเสนอราคา/ราคาประเมิน) |
| `LTV` | **ltv** | อัตราส่วนวงเงินกู้ต่อมูลค่าทรัพย์สิน (Loan to Value) | การอนุมัติ (Approval) | 0 - 100 (มักอยู่ช่วง 60-95%) | **มี** (คำนวณจากยอดกู้เทียบราคารถ) |
| `BRANCH_ID` | **branch_id** | รหัสสาขาที่ทำสัญญา | การสมัคร (Application) | รหัส ID สาขา | **มี** |
| `SUPPLIER_ID` | **supplier_id** | รหัสตัวแทนจำหน่าย (Dealer) | การสมัคร (Application) | รหัส ID ตัวแทนจำหน่าย | **มี** |
| `MANUFACTURER_ID` | **manufacturer_id** | รหัสผู้ผลิตรถยนต์ | การสมัคร (Application) | รหัส ID ผู้ผลิต | **มี** |
| `CURRENT_PINCODE_ID` | **Current_pincode** | รหัสไปรษณีย์ที่อยู่ปัจจุบันของลูกค้า | การสมัคร (Application) | รหัสไปรษณีย์ 5-6 หลัก | **มี** |
| `DATE_OF_BIRTH` | **Date.of.Birth** | วันเกิดของลูกค้า (ใช้คำนวณอายุ) | การสมัคร (Application) | อายุควรอยู่ระหว่าง 18 - 70 ปี | **มี** |
| `EMPLOYMENT_TYPE` | **Employment.Type** | ประเภทอาชีพ (Salaried/Self Employed) | การสมัคร (Application) | Salaried หรือ Self Employed | **มี** |
| `DISBURSAL_DATE` | **DisbursalDate** | วันที่ทำการโอนเงินกู้ให้ลูกค้า | การเบิกจ่าย (Disbursal) | วันที่ปัจจุบันหรือย้อนหลัง | **มี** (ใช้วันที่ที่คาดว่าจะโอน) |
| `STATE_ID` | **State_ID** | รหัสรัฐที่ทำการกู้เงิน | การสมัคร (Application) | รหัส ID รัฐ | **มี** |
| `EMPLOYEE_CODE_ID` | **Employee_code_ID** | รหัสพนักงานที่ดูแลเคสนี้ | การสมัคร/อนุมัติ | รหัส ID พนักงาน | **มี** |
| `MOBILENO_AVL_FLAG` | **MobileNo_Avl_Flag** | ลูกค้าให้เบอร์โทรศัพท์มือถือหรือไม่ | การสมัคร (Application) | 0 หรือ 1 | **มี** |
| `AADHAR_FLAG` | **Aadhar_flag** | ใช้บัตร Aadhar (ID อินเดีย) ยืนยันตัวตนไหม | การสมัคร (Application) | 0 หรือ 1 | **มี** |
| `PAN_FLAG` | **Pan_flag** | ใช้บัตร PAN (รหัสภาษี) ยืนยันตัวตนไหม | การสมัคร (Application) | 0 หรือ 1 | **มี** |
| `VOTERID_FLAG` | **VoterID_flag** | ใช้บัตรเลือกตั้งยืนยันตัวตนหรือไม่ | การสมัคร (Application) | 0 หรือ 1 | **มี** |
| `DRIVING_FLAG` | **Driving_flag** | มีการยื่นใบขับขี่หรือไม่ | การสมัคร (Application) | 0 หรือ 1 | **มี** |
| `PASSPORT_FLAG` | **Passport_flag** | มีการยื่นพาสปอร์ตหรือไม่ | การสมัคร (Application) | 0 หรือ 1 | **มี** |
| `PERFORM_CNS_SCORE` | **PERFORM_CNS.SCORE** | คะแนนเครดิตจากบูโร (Credit Score) | ก่อนอนุมัติ (Pre-Approval) | 0 (ไม่มีประวัติ) หรือ 300-900 | **มี** (ดึงข้อมูลจากบูโรได้) |
| `PERFORM_CNS_SCORE_DESCRIPTION` | **PERFORM_CNS.SCORE.DESCRIPTION** | คำอธิบายระดับคะแนนเครดิต | ก่อนอนุมัติ (Pre-Approval) | เช่น "Very Low Risk", "No History" | **มี** |
| `PRI_NO_OF_ACCTS` | **PRI.NO.OF.ACCTS** | จำนวนบัญชีสินเชื่อส่วนบุคคลทั้งหมดที่เคยมี | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `PRI_ACTIVE_ACCTS` | **PRI.ACTIVE.ACCTS** | จำนวนบัญชีสินเชื่อส่วนบุคคลที่ยังเปิดอยู่ | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `PRI_OVERDUE_ACCTS` | **PRI.OVERDUE.ACCTS** | จำนวนบัญชีที่ค้างชำระในปัจจุบัน | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `PRI_CURRENT_BALANCE` | **PRI.CURRENT.BALANCE** | ยอดหนี้คงเหลือรวมของสินเชื่อส่วนบุคคล | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `PRI_SANCTIONED_AMOUNT` | **PRI.SANCTIONED.AMOUNT** | วงเงินรวมที่เคยได้รับอนุมัติ (ส่วนบุคคล) | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `PRI_DISBURSED_AMOUNT` | **PRI.DISBURSED.AMOUNT** | ยอดเงินรวมที่เคยได้รับโอนจริง (ส่วนบุคคล) | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `SEC_NO_OF_ACCTS` | **SEC.NO.OF.ACCTS** | จำนวนบัญชีที่ลูกค้าเป็นผู้กู้ร่วม/ค้ำประกัน | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `SEC_ACTIVE_ACCTS` | **SEC.ACTIVE.ACCTS** | จำนวนบัญชีร่วมที่ยังเปิดอยู่ | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `SEC_OVERDUE_ACCTS` | **SEC.OVERDUE.ACCTS** | จำนวนบัญชีร่วมที่ค้างชำระ | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `SEC_CURRENT_BALANCE` | **SEC.CURRENT.BALANCE** | ยอดหนี้คงเหลือรวมของบัญชีร่วม | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `SEC_SANCTIONED_AMOUNT` | **SEC.SANCTIONED.AMOUNT** | วงเงินรวมที่ได้รับอนุมัติในบัญชีร่วม | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `SEC_DISBURSED_AMOUNT` | **SEC.DISBURSED.AMOUNT** | ยอดเงินรวมที่ได้รับโอนในบัญชีร่วม | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `PRIMARY_INSTAL_AMT` | **PRIMARY.INSTAL.AMT** | ยอดผ่อนชำระต่อเดือนของสินเชื่อส่วนบุคคลเดิม | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `SEC_INSTAL_AMT` | **SEC.INSTAL.AMT** | ยอดผ่อนชำระต่อเดือนของสินเชื่อร่วมเดิม | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `NEW_ACCTS_IN_LAST_SIX_MONTHS` | **NEW.ACCTS.IN.LAST.SIX.MONTHS** | จำนวนบัญชีใหม่ที่เปิดในช่วง 6 เดือนล่าสุด | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `DELINQUENT_ACCTS_IN_LAST_SIX_MONTHS` | **DELINQUENT.ACCTS.IN.LAST.SIX.MONTHS** | จำนวนบัญชีที่มีการค้างชำระใน 6 เดือนล่าสุด | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |
| `AVERAGE_ACCT_AGE` | **AVERAGE.ACCT.AGE** | อายุเฉลี่ยของบัญชีสินเชื่อทั้งหมด | ก่อนอนุมัติ (Pre-Approval) | ระยะเวลา (เช่น 1yr 2mon) | **มี** |
| `CREDIT_HISTORY_LENGTH` | **CREDIT_HISTORY.LENGTH** | ระยะเวลานับตั้งแต่มีสินเชื่อใบแรก | ก่อนอนุมัติ (Pre-Approval) | ระยะเวลา (เช่น 3yr 5mon) | **มี** |
| `NO_OF_INQUIRIES` | **NO.OF_INQUIRIES** | จำนวนครั้งที่ลูกค้าถูกเช็คเครดิตล่าสุด | ก่อนอนุมัติ (Pre-Approval) | 0 ขึ้นไป | **มี** |

### สรุปภาพรวม
ข้อมูลส่วนใหญ่เป็นข้อมูลที่ได้จาก **ใบสมัคร (Application Data)** และ **ข้อมูลจากบูโร (Bureau Data)** ซึ่งมีอยู่จริง ณ วันที่ต้องการประเมินลูกค้าใหม่ (Scoring) ยกเว้นเพียง `loan_default` ซึ่งเป็นสถานะที่จะเกิดขึ้นในอนาคตหลังจากที่ลูกค้าได้รับเงินไปแล้วเท่านั้น
