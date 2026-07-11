# Get Windows Product Key (ดึงคีย์ลิขสิทธิ์ Windows แท้)

คำสั่ง PowerShell สำหรับดึงรหัส Product Key (คีย์ลิขสิทธิ์แท้ 25 หลัก) ที่ผูกอยู่กับเมนบอร์ด (OEM Key) ออกมาแสดง เพื่อใช้สำหรับการลงเครื่องใหม่หรือสำรองข้อมูล

## คำสั่ง PowerShell
เปิด PowerShell แล้วคัดลอกคำสั่งด้านล่างนี้ไปวางแล้วกด **Enter**:

```powershell
(Get-WmiObject -Query 'select * from SoftwareLicensingService').OA3xOriginalProductKey
```

---

## 💡 ข้อมูลเพิ่มเติม
* คำสั่งนี้จะดึงคีย์ประเภท **OEM (Original Equipment Manufacturer)** ซึ่งเป็นลิขสิทธิ์แท้ที่ติดมากับตัวเครื่องโน้ตบุ๊กหรือคอมพิวเตอร์แบรนด์ต่าง ๆ ตั้งแต่ตอนซื้อ
* หากคุณใช้ Windows ที่เป็นแบบ Volume License หรือคีย์ที่ไม่ได้ผูกกับเมนบอร์ด หน้าจออาจจะว่างเปล่าหลังจากรันคำสั่งนี้
